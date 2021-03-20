<template>
  <div>
    <!-- <div>{{value}}</div> -->
    <!-- <z-input :value="value" @input="value=arguments[0]"></z-input> -->
    <!-- <z-input v-model="value"></z-input> -->
    <z-form :model="form" :rules="rules">
      <z-form-item label="用户名" prop="name">
        <z-input v-model="form.name"></z-input>
      </z-form-item>
      <z-form-item label="密码" prop="password">
        <z-input v-model="form.password" type="password"></z-input>
      </z-form-item>
    </z-form>
  </div>
</template>
<script>
import ZInput from "@/components/ZInput";
import ZFormItem from "@/components/ZFormItem";
import ZForm from "@/components/ZForm";

export default {
  components: {
    ZInput,
    ZFormItem,
    ZForm
  },
  methods: {
    handleInput(val) {
      this.value = val;
    }
  },
  data() {
    return {
      title: "我的mini表单",
      value: "",
      form: {
        name: "",
        password: ""
      },
      ruleForm: {
        name: ""
      },
      rules: {
        name: [
          { required: true, message: "请输入活动名称", trigger: "blur" },
          { min: 3, max: 5, message: "长度在 3 到 5 个字符", trigger: "blur" }
        ],
        password:[
            { required: true, message: "请输入密码", trigger: "blur" },
          { min: 3, max: 5, message: "长度在 3 到 5 个字符", trigger: "blur" }
        ]
      }
    };
  }
};
</script>
<style lang="scss" scoped>
</style>