<template>
  <div id="app">
    <div class="switch-box">
      <el-switch
        v-model="isEdit"
        active-text="表单"
        inactive-text="详情">
      </el-switch>
    </div>
    <div class="container">
      <FormBox v-if="isEdit" v-model="form"/>
      <Detail v-else :form="form"/>
    </div>
  </div>
</template>

<script>
import FormBox from './components/Form.vue'
import Detail from './components/Detail.vue'

export default {
  name: 'app',
  components: {
    FormBox,
    Detail
  },
  data() {
    return {
      isEdit: true,
      form: {
        name: '',
        region: '',
        date1: '',
        date2: '',
        delivery: false,
        type: [],
        resource: '',
        desc: ''
      }
    }
  },
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  color: #2c3e50;
  margin-top: 60px;
}
.container{
  width: 60%;
  margin: 0 auto;
}
.switch-box{
  text-align: center;
  margin-bottom: 20px;
}
</style>
