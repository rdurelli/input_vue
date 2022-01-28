<template>
  <div>
    <p>{{ message }}</p>
    <p>{{ info }}</p>
    Type: <input v-model="message" v-on:input="sendToBackEndAPI">
  </div>
</template>

<script>
import axios from "axios";

export default {
  name: "Input",
  data() {
    return {
      message: 'Type Here!',
      info: null
    }
  },
  methods: {
    sendToBackEndAPI: function () {
      const bodyToSend = {
        name: "Erick" + Math.random(),
        e_mail: "erick@ufla.com.br"
      }
      axios.post('https://60315fd1081a01001754701d.mockapi.io/cliente', bodyToSend).then(response => (this.info = response.data))
    }
  },
}
</script>

<style scoped>

</style>
