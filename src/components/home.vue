<template>
  <div class="home">
    <mt-button type="primary" @click.native="toast">primary</mt-button>
		<br/>
		<mt-button type="primary" @click.native="openPicker">openPicker</mt-button>
		<mt-datetime-picker ref="picker" type="time" v-model="pickerValue"></mt-datetime-picker>
		
		<el-button @click="visible = true">Button</el-button>
    <el-dialog :visible.sync="visible" title="Hello world">
      <p>Try Element</p>
    </el-dialog>
		
		 <el-table
      :data="tableData"
      style="width: 100%">
      <el-table-column
        prop="date"
        label="日期"
        width="180">
      </el-table-column>
      <el-table-column
        prop="address"
        label="地址">
      </el-table-column>
    </el-table>
	
  </div>
</template>

<script>
import { Toast } from 'mint-ui'
import { DatetimePicker } from 'mint-ui';

export default {
  computed: {},
  data () {
    return {
      msg: 'Welcome to Your Vue.js App',
			pickerValue: null,
			visible: false,
			tableData: [{
            date: '2016-05-02',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1518 弄'
          }, {
            date: '2016-05-04',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1517 弄'
          }, {
            date: '2016-05-01',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1519 弄'
          }, {
            date: '2016-05-03',
            name: '王小虎',
            address: '上海市普陀区金沙江路 1516 弄'
          }]
    }
  },
  beforeDestroy () {},
  created () {},
  mounted () {},
  methods: {
    toast () {
      Toast({
        message: '提示',
        position: 'bottom',
        duration: 5000
      })
    },
		openPicker() {
        this.$refs.picker.open();
      }
  }
}
</script>
<style scoped lang="less">
.home{
  text-align: left;
  button{
    width: 100%
  }
}
</style>
