<!-- eslint-disable vue/multi-word-component-names -->
<template>
  <div>
    <p>{{ text }}</p>
  </div>
</template>

<script>
export default {
  name: "App",
  data() {
    return {
      text: "Hola Vue",
    };
  },
  beforeCreate() {
    console.log("beforeCreate", this.$data, this.$el);
  },
  created() {
    console.log("created", this.$data, this.$el);
  },
  mounted() {
    console.log("mounted", this.$data, this.$el);
  },
};
</script>
