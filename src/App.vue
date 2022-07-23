<template>
  <NavBar></NavBar>
  <div class="container-fluid">
    <div class="row">
      <section class="col-md-12">
        <header class="col-md-3">Single select dropdown</header>
          <form class="row">
         <div class="col-md-6">
        <SingleSelect
          :options="options"
          v-model="user"
          :showLabel="true"
          :label="'User'"
        ></SingleSelect>
      </div>
    </form>
      </section>
      <section class="col-md-12">
        <header class="col-md-3">Single select dropdown with placeholder</header>
          <form class="row">
         <div class="col-md-6">
        <SingleSelect
          :options="options"
          v-model="user"
          :showDefaultText="true"
          :defaultText="'Select user......'"
          :showLabel="true"
          :label="'User'"
        ></SingleSelect>
      </div>
    </form>
      </section>
    </div>  
  </div>
</template>

<script>
import NavBar from "./components/NavBar.vue";
import SingleSelect from "./components/SingleSelect.vue";

export default {
  name: "App",
  components: {
    NavBar,
    SingleSelect,
  },
  data() {
    return {
      options: [
        { text: "Guru", value: "1" },
        { text: "Chandru", value: "2" },
      ],
      user: "1",
    };
  },
};
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
}
</style>
