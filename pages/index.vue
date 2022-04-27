<template>
  <div>
    <blog-header />

    <blog-posts :posts="posts" />

    <blog-pagination :total="total" :per-page="perPage" />

    <blog-footer />
  </div>
</template>

<script lang="ts">
import Vue from "vue";
export default {
  name: "IndexPage",
  async asyncData({ $content, error }: any) {
    const currentPage = 1;
    const perPage = 10;
    const posts = await $content("posts", { deep: true })
      .sortBy("date", "desc")
      .fetch();
    const totalPosts = posts.length;
    const lastPage = Math.ceil(totalPosts / perPage);
    const lastPageCount =
      totalPosts % perPage === 0 ? perPage : totalPosts % perPage;

    const skipNumber = () => {
      if (currentPage === 1) {
        return 0;
      }
      if (currentPage === lastPage) {
        return totalPosts - lastPageCount;
      }
      return (currentPage - 1) * perPage;
    };
    const paginatedPosts = await $content("posts", { deep: true })
      .only(["title", "description", "slug", "date"])
      .sortBy("date", "desc")
      .limit(perPage)
      .skip(skipNumber())
      .fetch();

    if (!paginatedPosts.length) {
      return error({ statusCode: 404, message: "No posts found!" });
    }

    return {
      posts: paginatedPosts,
      total: totalPosts,
      perPage,
    };
  },
  data() {
    return {
      posts: [],
      total: 0,
      perPage: 0,
    };
  },
  head() {
    return {
      title: "Underdev Blog | Programação + Conhecimento",
      meta: [
        {
          hid: "og:title",
          name: "og:title",
          content: "pvini Blog gurizada",
        },
      ],
    };
  },
  watchQuery: ["page"],
  mounted() {},
};
</script>
