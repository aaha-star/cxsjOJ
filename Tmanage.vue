<style scoped>
    .layout{
        border: 1px solid #d7dde4;
        background: #f5f7f9;
        position: relative;
        border-radius: 4px;
        overflow: hidden;
    }
    .layout-header-bar{
        background: #fff;
        box-shadow: 0 1px 1px rgba(0,0,0,.1);
    }
</style>
<template>
    <div class="layout">
        <Sider :style="{position: 'fixed', height: '100vh', left: 0, overflow: 'auto'}">
            <Menu active-name="1-2" theme="dark" width="auto" :open-names="['1']">
                <Submenu name="1">
                    <template slot="title">
                        <Icon type="ios-navigate"></Icon>
                       教师管理
                    </template>
                      <MenuItem name="1-1" @click.native="home">个人信息</MenuItem>
                    <MenuItem name="1-2" @click.native="info">题目上传</MenuItem>
                    <MenuItem name="1-3">题目管理</MenuItem>
                </Submenu>
                <!-- <Submenu name="2">
                    <template slot="title">
                        <Icon type="ios-keypad"></Icon>
                        题目上传
                    </template>
                    <MenuItem name="2-1">Option 1</MenuItem>
                    <MenuItem name="2-2">Option 2</MenuItem>
                </Submenu>
                <Submenu name="3">
                    <template slot="title">
                        <Icon type="ios-analytics"></Icon>
                        题目管理
                    </template>
                    <MenuItem name="3-1">Option 1</MenuItem>
                    <MenuItem name="3-2">Option 2</MenuItem>
                </Submenu> -->
            </Menu>
        </Sider>
        <Layout :style="{marginLeft: '200px'}">
            <Header :style="{background: '#fff', boxShadow: '0 2px 3px 2px rgba(0,0,0,.1)'}"></Header>
            <Content :style="{padding: '0 16px 16px'}">
                <!-- <Breadcrumb :style="{margin: '16px 0'}">
                    <BreadcrumbItem>Home</BreadcrumbItem>
                    <BreadcrumbItem>Components</BreadcrumbItem>
                    <BreadcrumbItem>Layout</BreadcrumbItem>
                </Breadcrumb> -->
                <Card>
                    <div style="height: 600px"></div>
                </Card>
            </Content>
        </Layout>
    </div>
</template>
<script>
    export default {
       methods: {
            info () {
                this.$router.push({path: '/Upload'})
            },
            home ()
            {
                 this.$router.push({path: '/Tmanage'})
            }
        }
    }
</script>
