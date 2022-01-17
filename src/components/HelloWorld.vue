<template>
  <div class="hello">
    <img :src="this.catUrl" alt="Cat" />
  </div>
</template>

<script>
export default {
  name: 'Cat',
  props: {
    msg: String
    },
  data() {
    return {
      catUrl: '',
      lastUpdate: 0
    }
  },
  methods: {
    _keyListener(e) {
        console.log(e.key)
        if(new Date().getTime() - this.lastUpdate < 1000 ) {
          console.log("too fast, waiting a little")
          return
        }
        this.getCatUrl()
    },
    getCatUrl () {
        console.log("getting anew cat")
        this.lastUpdate = new Date().getTime()
        this.catUrl = 'https://cataas.com/cat?t='+ new Date().getTime()
     }
},
mounted() {
  this.getCatUrl();
  window.addEventListener('keypress', this._keyListener);
},
beforeDestroy() {
  window.removeEventListener('keypress', this._keyListener);
}
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
h3 {
  margin: 40px 0 0;
}
ul {
  list-style-type: none;
  padding: 0;
}
li {
  display: inline-block;
  margin: 0 10px;
}
a {
  color: #42b983;
}
</style>
