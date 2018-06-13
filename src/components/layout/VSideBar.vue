<template>
      <!-- <div class="text-center icon-div">
        <fa icon="bars" size="5x" @click.native="handleBtnAClick"/></div> -->
      <side-nav
        :OpenedFromOutside.sync="toggleA"
        color="white"
        waves>
        <li>
          <ul class="collapsible">
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 1 ? 'selected' : ''" @click="wave" @click.prevent="active === 1 ? active = 0 : active = 1">
                <fa icon="home"/> Home
              </a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 2 ? 'selected' : ''" @click="wave" @click.prevent="active === 2 ? active = 0 : active = 2">
                <fa icon="file-text-o"></fa> Diary
              </a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 3 ? 'selected' : ''" @click="wave" @click.prevent="active === 3 ? active = 0 : active = 3">
                <fa icon="calendar"></fa> Schedule</a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 4 ? 'selected' : ''" @click="wave" @click.prevent="active === 4 ? active = 0 : active = 4">
                <fa icon="bar-chart"></fa> Progress report</a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 5 ? 'selected' : ''" @click="wave" @click.prevent="active === 5 ? active = 0 : active = 5">
                <fa icon="bullseye"></fa> Goal</a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 6 ? 'selected' : ''" @click="wave" @click.prevent="active === 6 ? active = 0 : active = 6">
                <fa icon="users"></fa> Group Sessions</a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 7 ? 'selected' : ''" @click="wave" @click.prevent="active === 7 ? active = 0 : active = 7">
                <fa icon="copy"></fa> Files</a>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 8 ? 'selected' : ''" @click="wave" @click.prevent="active === 8 ? active = 0 : active = 8">
                <fa icon="send-o"></fa> Communication<fa icon="angle-down" class="rotate-icon" :class="active === 8 ? 'rotated' : ''"/></a>
              <transition @before-enter="beforeEnter" @enter="enter" @before-leave="beforeLeave">
                <sub-menu tag="ul" v-if="active === 8" class="collapse-item">
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Forms</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Contacts</a>
                  </li>
                </sub-menu>
              </transition>
            </li>
            <li>
              <a class="collapsible-header ripple-parent blue-grey-text" :class="active === 9 ? 'selected' : ''" @click="wave" @click.prevent="active === 9 ? active = 0 : active = 9">
                <fa icon="question-circle-o"></fa> Info<fa icon="angle-down" class="rotate-icon" :class="active === 9 ? 'rotated' : ''"/></a>
              <transition @before-enter="beforeEnter" @enter="enter" @before-leave="beforeLeave">
                <sub-menu tag="ul" v-if="active === 9" class="collapse-item">
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">My File</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Diary guide</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Unit guide</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Feedback</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Contact</a>
                  </li>
                  <li><a href="#" class="ripple-parent blue-grey-text" @click="wave">Chat</a>
                  </li>
                </sub-menu>
              </transition>
            </li>
          </ul>
        </li>
      </side-nav>
</template>

<script>
  import { SideNav, Btn, Container, Fa, SubMenu, waves } from 'mdbvue';

  export default {
    name: 'SideNavPage',
    props: {
      waves: {
        type: Boolean,
        default: true
      }
    },
    components: {
      SideNav,
      Btn,
      Container,
      Fa,
      SubMenu,
    },
    data(){
      return {
        toggleA: false,
        toggleB: false,
        active: 0,
        elHeight: 0
      };
    },
    methods: {
      handleBtnAClick() {
        this.toggleA = !this.toggleA;
      },
      beforeEnter(el) {
        this.elHeight = el.scrollHeight;
      },
      enter(el) {
        el.style.height = this.elHeight+'px';
      },
      beforeLeave(el) {
        el.style.height = 0;
      }
    },
    mixins: [waves]
  };
</script>

<style lang="scss" scoped>
  .collapsible {
    margin-top: 1rem;
  }

  .collapsible-header {
    position: relative;
    &:hover {
      border-left: 3px solid #f15d2e;
      background-color: #fef5f3 !important;
    }
  }

  .collapse-item {
    overflow: hidden;
    height: 0;
    padding: 0;
    transition: height .3s;
    a {
      padding-left: 47px;
      line-height: 36px;
    }
  }
  .fa-angle-down {
    float: right;
  }
  .icon-div {
    width: 49%;
    display: inline-block;
  }

  .rotated {
    transform: rotate(180deg);
  }

  .selected {
    border-left: 3px solid #f15d2e;
    background-color: #fef5f3;
  }
</style>

<style>
.side-nav {
  margin-top: 54px;
}
</style>
