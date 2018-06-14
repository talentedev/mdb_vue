<template>
  <navbar position="top" name=" " href="#" class="navbar-expand" scrolling>
    <navbar-nav>
      <fa icon="bars" @click.native="onCollaseSideBar()"/>
      <a class="logo-wrapper ml-4"><img alt="" class="img-fluid" src="../../assets/img/alavida-logo-colored.jpg"/></a>
    </navbar-nav>
    <navbar-nav right>
      <navbar-item href="#!"><fa icon="bell-o"/><badge color="red">3</badge></navbar-item>
      <navbar-item href="#!"><fa icon="commenting-o"/><badge color="orange">3</badge></navbar-item>
      <dropdown v-if="showAccountSettings" tag="li" class="nav-item">
        <dropdown-toggle @click.native="toggleDropdown(0)" tag="div" navLink>
          <img src="../../assets/img/avatar.png">
          <p class="float-right"><fa icon="caret-down"/></p>
          <div class="float-right pl-2">
            <p class="m-0 blue-grey-text">Jeff Magnusson</p>
            <p class="m-0 blue-grey-text"><small>8:20 am PDT</small></p>
          </div>
        </dropdown-toggle>
        <dropdown-menu v-show="active[0]">
          <dropdown-item>Settings</dropdown-item>
          <dropdown-item>Log out</dropdown-item>
        </dropdown-menu>
      </dropdown>
    </navbar-nav>
  </navbar>
</template>

<script>
import { Navbar, NavbarItem, NavbarNav, Dropdown, DropdownItem, DropdownMenu, DropdownToggle, Fa, Badge } from 'mdbvue';

export default {
  name: 'VHeader',
  components: {
    Navbar,
    NavbarItem,
    NavbarNav,
    Dropdown,
    DropdownItem,
    DropdownMenu,
    DropdownToggle,
    Fa,
    Badge
  },
  props: {
    breakWidth: {
      type: Number,
      default: 770
    }
  },
  data() {
    return {
      active: {
        0: false
      },
      showAccountSettings: true
    };
  },
  methods: {
    toggleDropdown(index) {
      for (let i = 0; i < Object.keys(this.active).length; i++) {
        if (index !== i) {
          this.active[i] = false;
        }
      }
      this.active[index] = !this.active[index];
    },
    allDropdownsClose(target) {
      for (let i = 0; i < Object.keys(this.active).length; i++) {
        this.active[i] = false;
      }
    },
    onClick(e) {
      let parent = e.target;
      let body = document.getElementsByTagName('body')[0];
      while (parent !== body) {
        if (parent.classList.contains('dropdown') || parent.classList.contains('btn-group')) {
          return;
        }
        parent = parent.parentNode;
      }
      this.allDropdownsClose(e.target);
    },
    onCollaseSideBar() {
      this.$parent.onCollapseSideBar();
    },
    updatePredicate() {
      this.showAccountSettings = window.innerWidth > this.breakWidth;
    }
  },
  mounted() {
    this.updatePredicate();
    document.addEventListener('click', this.onClick);
    window.addEventListener("resize", this.updatePredicate);
  },
  destroyed() {
    document.removeEventListener('click', this.onClick);
  }
};
</script>

<style lang="scss" scoped>
.navbar {
  padding: 5px !important;
  background-color: white;
}
.logo-wrapper img {
  width: 115px;
  height: 20px;
}
.nav-item {
  margin-left: 15px;
}
.fa {
  font-size: 20px;
  color: #b6b9b8;
}
.dropdown-toggle {
  padding: 0;
  background-color: white !important;
  font-size: 12px;
  .fa {
    font-size: 13px;
    margin: 12px 0 0 10px;
  }
  img {
    width: 35px;
    height: 35px;
  }
  &::after {
    display: none;
  }
  &:hover {
    background-color: white !important;
  }
}
</style>
<style lang="scss">
.badge {
  width: 13px;
  height: 13px;
  font-size: 8px;
  position: absolute;
  top: 4px;
  left: 23px;
  border-radius: 50%;
}
</style>
