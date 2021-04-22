<template>
  <div class="warp">
    <el-form>
  <el-form  :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm">
<el-row class="top1" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
</el-row>
    
   <el-row class="top" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
</el-row>

  <el-row class="top" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
   <el-form-item label="活动区域" prop="region">
    <el-select v-model="ruleForm.region" placeholder="请选择活动区域">
      <el-option label="区域一" value="shanghai"></el-option>
      <el-option label="区域二" value="beijing"></el-option>
    </el-select>
  </el-form-item>
  </el-col>
</el-row>

</el-form>


 <el-form  :model="ruleForm" :rules="rules" ref="ruleForm" label-width="100px" class="demo-ruleForm" v-if="isShow">
<i class="el-icon-delete" @click="deleted"></i>
<el-row class="top1" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
</el-row>
    
   <el-row class="top" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
</el-row>

  <el-row class="top" :gutter="20">
  <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
  <el-form-item label="活动名称" prop="name">
    <el-input v-model="ruleForm.name"></el-input>
  </el-form-item>
  </el-col>
   <el-col :span="6">
   <el-form-item label="活动区域" prop="region">
    <el-select v-model="ruleForm.region" placeholder="请选择活动区域">
      <el-option label="区域一" value="shanghai"></el-option>
      <el-option label="区域二" value="beijing"></el-option>
    </el-select>
  </el-form-item>
  </el-col>
</el-row>

</el-form>

   <div class="bottom">
     <p>+新增检测项目</p>
   </div>

    <el-form-item class="btn">
    <el-button type="primary" @click="submitForm('ruleForm')">立即创建</el-button>
    <el-button @click="resetForm('ruleForm')">重置</el-button>
  </el-form-item>
    </el-form>
  </div>
</template>

<script>
export default {
    data() {
      return {
        isShow:true,
        ruleForm: {
          name: '',
          region: '',
        },
        rules: {
          name: [
            { required: true, message: '请输入活动名称', trigger: 'blur' },
            { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
          ],
          region: [
            { required: true, message: '请选择活动区域', trigger: 'change' }
          ],
        }
      };
    },
    methods:{
      deleted(){
        this.ruleForm.name = "";
        this.isShow = false;
      }
    }
    // methods: {
    //   submitForm(formName) {
    //     this.$refs[formName].validate((valid) => {
    //       if (valid) {
    //         alert('submit!');
    //       } else {
    //         console.log('error submit!!');
    //         return false;
    //       }
    //     });
    //   },
    //   resetForm(formName) {
    //     this.$refs[formName].resetFields();
    //   }
    // }
  }
</script>

<style scoped>
.el-form-item {
  width: 100%;
  display: flex;
  flex-direction: column; 
}


.warp {
  width: 100%;
  height: 100%;
}
.el-form-item >>> .el-form-item__content{
    margin-left: 0px !important;
}
.el-form{
  padding: 0 50px;
  border: 1px solid #000;
  margin-top: 50px;
}
.top{
  display: flex;
  /* justify-content: space-between; */
}
.el-row :nth-child(2){
  margin-left: 100px;
}
.el-row :nth-child(3){
  margin-left: 100px;
} 
.el-form-item__label::before {
    content: "*";
    color: rgb(245, 108, 108);
    margin-right: 4px;
}
.el-select{
  width: 100%;
}
.demo-ruleForm{
  position: relative;
}
.el-icon-delete{
  position: absolute;
  font-size: 25px;
  right: 20px;
  top: 20px;
  color: rgb(38, 110, 243);
}
.bottom{
  margin-top: 50px;
  text-align: center;
  width: 100%;
  height: 50px;
  border: 1px dotted #000;
}
.btn{
  margin-right: 100px;
}


</style>
