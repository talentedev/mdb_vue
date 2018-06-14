<template>
  <div id="app">
    <v-header/>
    <v-side-bar :collapsed="collapseSideBar"/>
    <main :class="{'collapsed-content': !isMobile && collapseSideBar}">
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import VHeader from '@/components/layout/VHeader';
import VSideBar from '@/components/layout/VSideBar';

export default {
  name: 'app',
  props: {
    breakWidth: {
      type: Number,
      default: 770
    }
  },
  components: {
    VHeader,
    VSideBar
  },
  data() {
    return {
      collapseSideBar: true,
      isMobile: false
    };
  },
  methods: {
    onCollapseSideBar() {
      this.collapseSideBar = !this.collapseSideBar;
    },
    updatePredicate() {
      this.isMobile = window.innerWidth < this.breakWidth;
    }
  },
  mounted() {
    this.updatePredicate();
    window.addEventListener("resize", this.updatePredicate);
  }
};

</script>

<style>
main {
  padding: 78px 24px;
  background-color: #f0f2f5;
  height: -webkit-fill-available;
}
.collapsed-content {
  margin-left: 240px;
}
</style>
