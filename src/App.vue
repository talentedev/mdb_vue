<template>
  <div id="app" class="flyout">
    <v-header/>
    <v-side-bar/>
    <main :style="{marginTop: '54px'}">
      <router-view></router-view>
    </main>
  </div>
</template>

<script>
import VHeader from '@/components/layout/VHeader';
import VSideBar from '@/components/layout/VSideBar';

export default {
  name: 'app',
  components: {
    VHeader,
    VSideBar
  }
};

</script>

<style>
.flyout {
	/*display:flex;
	flex-direction: column;
	min-height:100vh;
	justify-content: space-between;*/
}
</style>
