<!--<template>-->
<!--<div id="footer">-->
<!--  <span>{{activeList.length}}items left</span>-->
<!--  <div id="buttons">-->
<!--    <button @click="showAll" :class="{active:all}">All</button>-->
<!--    <button @click="showActive" :class="{active:active}">Active</button>-->
<!--    <button @click="showCompleted" :class="{active:completed}">Completed</button>-->
<!--  </div>-->
<!--</div>-->
<!--</template>-->

<!--<script>-->
<!--import {useStore} from "vuex";-->
<!--import {computed} from "vue";-->

<!--export default {-->
<!--  setup() {-->
<!--    const store = useStore();-->
<!--    const activeList = computed(() => {-->
<!--      return store.getters.active;-->
<!--    });-->

<!--    const all = computed(() => {-->
<!--      return store.state.active;-->
<!--    });-->
<!--    const active = computed(() => {-->
<!--      return store.state.active;-->
<!--    });-->
<!--    const completed = () => {-->
<!--      return store.state.completed;-->
<!--    };-->
<!--    const showAll = () => {-->
<!--      store.commit("show", {choice: "all"});-->
<!--    };-->
<!--    const showActive = () => {-->
<!--      store.commit("show", {choice: "actice"});-->
<!--    }-->
<!--    const showCompleted = () => {-->
<!--      store.commit("show", {choice: "completed"});-->
<!--    }-->
<!--    return {-->
<!--      activeList,-->
<!--      all,-->
<!--      active,-->
<!--      completed,-->
<!--      showAll,-->
<!--      showActive,-->
<!--      showCompleted-->
<!--    }-->

<!--  },-->
<!--};-->
<!--</script>-->

<!--<style scoped>-->
<!--.active {-->
<!--  color: goldenrod;-->
<!--  background-color: cornflowerblue;-->
<!--  border-color: lightcoral;-->
<!--}-->

<!--</style>-->