<template>
  <div>
    <p>{{ msg }}</p>
  </div>
</template>

<script>
import axios from 'axios'

export default {
  name: 'Page',
  data () {
    return {
      msg: ''
    }
  },
  methods: {
    getMessage () {
      const path = 'http://localhost:5000/'
      axios.get(path)
        .then((res) => {
          this.msg = res.data
        })
        .catch((error) => {
          // eslint-выключение следующей строки
          console.error(error)
        })
    }
  },
  created () {
    this.getMessage()
  }
}
</script>
