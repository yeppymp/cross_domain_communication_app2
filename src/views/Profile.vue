<template>
  <div class="profile p-8 bg-green-100 h-screen">
    <form class="text-center">
      <input
        type="text"
        class="
          rounded
          border border-transparent
          focus:outline-none
          focus:ring-2 focus:ring-green-600
          focus:border-transparent
          mr-2
          form-input
        "
        placeholder="Type your name"
        v-model="name"
      />
      <button
        class="
          rounded
          bg-green-600
          hover:bg-green-700
          focus:outline-none
          focus:ring-2 focus:ring-green-600 focus:ring-opacity-50
          py-2
          px-3
          text-white
        "
        @click.prevent="sendName"
      >
        Save
      </button>
    </form>
  </div>
</template>

<script>
export default {
  name: "Profile",
  data() {
    return {
      name: ''
    }
  },
  methods: {
    sendName() {
      let payload = {
        name: this.name
      }

      window.parent.postMessage(JSON.stringify(payload), '*');
      this.name = ''
    }
  }
};
</script>
