<template>
  <div>
    id {{id}}
  </div>
  <div>
    body {{body}}
  </div>

  <button v-on:click="closePostModal">Закрыть</button>
</template>

<script>
  import {defineComponent} from 'vue';

  export default defineComponent({
    name: 'PostModal',
    props: {
      id: Number,
      body: String
    },
    methods: {
      closePostModal() {
        this.$emit("closePostModal", false)
      }
    }
  })
</script>
