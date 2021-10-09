<template>
  <section class="flex justify-center align-middle flex-col sm:flex-row">
    <PostPreview
      :key="post.id"
      v-for="post in posts"
      :title="post.title"
      :excerpt="post.preview"
      :thumbnail="post.thumbnailUrl"
      :id="post.id"
    />
  </section>
</template>

<script lang="ts">
import Vue from "vue";
import PostPreview from "@/components/Blog/PostPreview.vue";

export default Vue.extend({
  components: {
    PostPreview,
  },
  asyncData(context) {
    return context.app.$storyapi
      .get("cdn/stories", {
        version: "draft",
        starts_with: "blog/",
      })
      .then((response: any) => {
        const {
          data: { stories },
        } = response;
        return {
          posts: stories.map((story: any) => ({
            id: story.slug,
            title: story.content.title,
            preview: story.content.summary,
            thumbnailUrl: story.content.thumbnail,
          })),
        };
      });
  },
});
</script>
