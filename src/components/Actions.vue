<template>
  <div class="z-50 w-full bg-transparent">
    <div class="flex flex-row">
      <button :key="action.icon" v-for="action in actions" class="link">
        <a :href="action.link" :title="action.title">
          <i :data-feather="action.icon" class="ext" :alt="action.icon" />
        </a>
      </button>
      <button
        class="font-body link lowercase"
        @mouseenter="resume = RESUME_HOVER"
        @mouseleave="resume = RESUME_DEFAULT"
      >
        <a
          target="_blank"
          href="/resume.pdf"
          title="Go to my resume (updated Oct 2019)"
          >{{ resume }}</a
        >
      </button>
    </div>
  </div>
</template>

<script>
import feather from "feather-icons";

export default {
  name: "Actions",
  data: function() {
    return {
      RESUME_DEFAULT: "Resume",
      RESUME_HOVER: "Resume [old]",
      resume: "Resume",
      actions: [
        {
          icon: "github",
          link: "https://github.com/kungpaogao/",
          title: "Go to my GitHub profile",
        },
        {
          icon: "linkedin",
          link: "https://www.linkedin.com/in/andrewxgao/",
          title: "Go to my LinkedIn profile",
        },
        {
          icon: "instagram",
          link: "https://www.instagram.com/gao.visuals/",
          title: "Go to my photography Instagram @gao.visuals",
        },
      ],
    };
  },
  mounted: function() {
    feather.replace();
  },
};
</script>

<style scoped>
.link {
  @apply my-3 ml-0 mr-6;
  transition: color 350ms;
}

.ext {
  @apply w-5;
}

.link:hover {
  @apply text-accent-500;
}
</style>
