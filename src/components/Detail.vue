<template>
  <el-form ref="form" :model="form" label-width="80px" size="mini">
      <el-form-item label="活动名称">
        {{form.name || '暂无输入'}}
      </el-form-item>
      <el-form-item label="活动区域">
        {{form.region | regionMap}}
      </el-form-item>
      <el-form-item label="活动时间">
        {{form.date1}} - {{form.date2}}
      </el-form-item>
      <el-form-item label="即时配送">
        {{form.delivery?'是':'否'}}
      </el-form-item>
      <el-form-item label="活动性质">
        {{form.type | typeMap}}
      </el-form-item>
      <el-form-item label="特殊资源">
        {{form.resource || '暂无选择'}}
      </el-form-item>
      <el-form-item label="活动形式">
        {{form.desc || '暂无输入'}}
      </el-form-item>
    </el-form>
</template>
<script>
export default {
  props:{
    form:{
      type: Object,
      default: ()=> {
        return{
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
    }
  },
  filters:{
    typeMap: function(type){
        if(type.length > 0){
          return type.join(',')
        }else{
          return '暂没选择'
        }
    },
    regionMap: function(region){
      const map = {
        beijing :'区域二',
        shanghai:'区域一' 
      }
      return map[region] || '暂无选择'
    }
  }
}
</script>
