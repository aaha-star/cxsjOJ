<template>
 <div type="flex" justify="center" align="middle" class="code-row-bg">
    <div class="demo-avatar">
            <Avatar icon="ios-person" size="large" />
    </div>
    <Form ref="formInline" :model="formInline" :rules="ruleInline" inline>
        <FormItem prop="userName">
            <Input type="text" v-model="formInline.userName" placeholder="Username">
            <Icon type="ios-person-outline" slot="prepend"></Icon>
            </Input>
        </FormItem>
        </br>
        <FormItem prop="password">
            <Input type="password" v-model="formInline.password" placeholder="Password" >
            <Icon type="ios-lock-outline" slot="prepend"></Icon>
            </Input>
        </FormItem>
        </br>
        <FormItem>
            <Button type="primary" @click="handleSubmit('formInline')">Signin</Button>
        </FormItem>
    </Form>
    <!-- <div>
      <router-link :to="{path:'Tmanage'}"> 教师管理</router-link>
    </div> -->
    <div>
        
    </div>
</div>
    
</template>
<script>
    export default {
        data() {
            return {
                formInline: {
                    userName: '',
                    password: ''
                },
                ruleInline: {
                    userName: [
                        {required: true, message: 'Please fill in the user name', trigger: 'blur'}
                    ],
                    password: [
                        {required: true, message: 'Please fill in the password.', trigger: 'blur'},
                        {
                            type: 'string',
                            min: 6,
                            message: 'The password length cannot be less than 6 bits',
                            trigger: 'blur'
                        }
                    ]
                }
            }
        },
        methods: {
            handleSubmit(name) {
                this.$refs[name].validate((valid) => {
                    if (valid) {
                        this.$Message.success('Success!');
                    } else {
                        this.$Message.error('Fail!');
                    }
                })
            }
        }
    }
</script> 