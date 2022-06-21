<template>
  <div
    class="
      bg-gradient-to-r
      from-violet-400
      to-blue-400
      flex
      justify-center
      p-5
      md:p-10
      items-center
    "
  >
    <div
      class="
        container
        mx-auto
        px-5
        md:px-24
        py-10
        rounded-lg
        bg-white bg-opacity-20
      "
    >
      <div class="text-center font-bold text-3xl text-white">Profiles List</div>
      <div class="">
        <div class="flex flex-row gap-5 justify-between items-center my-10">
          <button class="basis-1/2 p-3 bg-white rounded-lg" @click="sortAsc">
            ▲
          </button>
          <button class="basis-1/2 p-3 bg-white rounded-lg" @click="sortDesc">
            ▼
          </button>
        </div>

        <ProfileCard
          v-for="profile in profiles"
          :key="profile.id"
          :profile="profile"
          class="profile"
        />
      </div>
      <p class="text-white font-bold">Edit by Mohsen Piri</p>
    </div>
  </div>
</template>

<script>
import ProfileCard from "./components/ProfileCard";

export default {
  name: "App",

  components: {
    ProfileCard,
  },

  data() {
    return {
      profiles: [
        {
          id: 1,
          name: "Wojciech",
          email: "wojciech@poz.pl",
          description: "Anaesthesiologist",
          likes: 34,
        },
        {
          id: 2,
          name: "Maria",
          email: "maria@poz.pl",
          description: "Radiologist",
          likes: 28,
        },
        {
          id: 3,
          name: "Anna",
          email: "anna@poz.pl",
          description: "Surgeon",
          likes: 53,
        },
      ],
    };
  },

  methods: {
    sortAsc() {
      this.profiles.sort(function (a, b) {
        return a.likes - b.likes;
      });
    },

    sortDesc() {
      this.profiles.sort(function (a, b) {
        return b.likes - a.likes;
      });
    },
  },
};
</script>

<style>
</style>
