<template>
  <div class="bg-white my-5 p-5 rounded-lg">
    <div class="card">
      <div class="flex flex-row justify-start gap-2 items-center">
        <DoctorIcon class="w-16 rounded-full bg-violet-200" />
        <div class="flex flex-col">
          <strong>{{ profile.name }}</strong>
          <a :href="profile.email" class="email">{{ profile.email }}</a>
        </div>
      </div>
      <div class="text-violet-500 my-2">
        {{ profile.description }}
      </div>
      <div class="flex flex-row justify-start items-center">
        <svg
          xmlns="http://www.w3.org/2000/svg"
          class="h-5 w-5 text-sky-500"
          viewBox="0 0 20 20"
          fill="currentColor"
        >
          <path
            fill-rule="evenodd"
            d="M3.172 5.172a4 4 0 015.656 0L10 6.343l1.172-1.171a4 4 0 115.656 5.656L10 17.657l-6.828-6.829a4 4 0 010-5.656z"
            clip-rule="evenodd"
          />
        </svg>
        <p class="ml-2">{{ profile.likes }}</p>
      </div>
    </div>
    <div class="comment">
      <input class="comment-input" placeholder="Write your comment..." />
    </div>
  </div>
</template>

<script>
import DoctorIcon from "./DoctorIcon";

export default {
  name: "ProfileCard",

  components: {
    DoctorIcon,
  },

  props: {
    profile: {
      type: Object,
      required: true,
    },
  },
};
</script>

<style>
</style>
