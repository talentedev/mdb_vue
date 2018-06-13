<template>
  <!--Navbar-->
  <navbar position="top" name=" " href="#" class="navbar-expand-sm" scrolling>
    <navbar-collapse>
      <navbar-nav>
        <fa icon="bars"/>
        <a class="logo-wrapper ml-4"><img alt="" class="img-fluid" src="../../assets/img/alavida-logo-colored.jpg"/></a>
      </navbar-nav>
      <navbar-nav right>
        <navbar-item href="#!"><fa icon="bell-o"/><badge color="red">3</badge></navbar-item>
        <navbar-item href="#!"><fa icon="commenting-o"/><badge color="orange">3</badge></navbar-item>
        <!-- Dropdown -->
        <dropdown tag="li" class="nav-item">
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
    </navbar-collapse>
  </navbar>
  <!--/.Navbar-->
</template>

<script>
import { Navbar, NavbarItem, NavbarNav, NavbarCollapse, Dropdown, DropdownItem, DropdownMenu, DropdownToggle, Fa, Badge } from 'mdbvue';

export default {
  name: 'NavbarPage',
  components: {
    Navbar,
    NavbarItem,
    NavbarNav,
    NavbarCollapse,
    Dropdown,
    DropdownItem,
    DropdownMenu,
    DropdownToggle,
    Fa,
    Badge
  },
  data() {
    return {
      active: {
        0: false
      }
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
    }
  },
  mounted() {
    document.addEventListener('click', this.onClick);
  },
  destroyed() {
    document.removeEventListener('click', this.onClick);
  }
};
</script>

<style lang="scss" scoped>
.navbar {
  padding: 5px;
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
