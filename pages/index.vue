<template>
  <div>
    <blog-header />

    <blog-footer />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
import blogFooter from "~/components/blogFooter.vue";

export default Vue.extend({
  components: { blogFooter },
  name: "IndexPage",
});
</script>
