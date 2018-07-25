<template>
  <div class="hello">
    <input v-model="obj">
    <div>{{name}}</div>
    <div>{{ab}}</div>
    <div v-html="ll"></div>
  </div>
</template>

<script>
  export default {
    name: 'HelloWorld',
    data() {
      return {
        obj: '',
        ab: '',
        ll:''
      }
    },
    watch: {
      obj() {
        if (this.obj == '7777') {
          console.log('watch这里也触发了')
          this.init();
        }
      }
    },
    computed: {
      name() {
        if (this.obj == '66') {
          return '触发了'
        } else {
          return ''
        }
      }
    },
    methods: {
      init() {
        this.ab = '77777777777';
        this.ll = '<p>神迹帝卡</p><br/><p>我说的空间</p>'
      }
    }
  }
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped>
  h1,
  h2 {
    font-weight: normal;
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
