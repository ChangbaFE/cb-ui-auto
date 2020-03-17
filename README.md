
## 简介

VSCode插件，唱吧管理后台 UI 自动补全

该组件依赖于公司内部其他小伙伴开发的管理后台UI组件库

在Vue文件中输入  cb 既可看到提示 配置如下


## 安装

### 官方扩展商店安装：

可以在vscode的扩展面板搜索 uxcool，点击安装cb-ui-auto

如果提示无法安装，可以按照提示，下载VSIX安装包，在扩展面板，选择 **更多》从VSIX安装**

## 说明

`cb-page` 页面容器
```
<cb-page-section>其它组件或内容......</cb-page-section>
```
`cb-page-d` 页面容器+子标题
```
<cb-page-section :description="页面子标题">其它组件或内容......</cb-page-section>
```
`cb-button-p` 主要按钮
```
<cb-button theme="primary">主要按钮</cb-button>
```
`cb-button-s` 成功按钮
```
<cb-button theme="success">成功按钮</cb-button>
```
`cb-button-i` 信息按钮
```
<cb-button theme="info">信息按钮</cb-button>
```
`cb-button-d` 警告按钮
```
<cb-button theme="danger">警告按钮</cb-button>
```
`cb-menu-item` 下拉菜单项
```
<cb-menu-item>菜单项</cb-menu-item>
```
`cb-menu` 菜单项
```
<template slot="menu">
    <cb-menu-item>菜单1</cb-menu-item>
    <cb-menu-item>菜单2</cb-menu-item>
    <cb-menu-item>菜单3</cb-menu-item>
    <cb-menu-item separator>菜单4</cb-menu-item>
    <cb-menu-item>菜单1</cb-menu-item>
</template>
```
`cb-icon` 图标
```
<icon name="edit"></icon>
```
`cb-search` 搜索条件
```
<cb-search-table :data="list" :pager="pager" @search="refresh" ref="search" v-loading></cb-search-table>
```
`cb-search-table` 带搜索条件表格
```
<cb-search-table :data="list" :pager="pager" @search="refresh" ref="search" v-loading>
    <template slot="header">
        <cb-form-group label="名称：">
            <cb-form-control v-model="searchValue" v-focus></cb-form-control>
        </cb-form-group>
        <cb-form-group label="状态：">
            <cb-form-control type="select" v-model="status">
                <option value="">全部</option>
                <option value="1">有效</option>
                <option value="0">无效</option>
            </cb-form-control>
        </cb-form-group>
    </template>


    <template slot="header-button">
        <cb-button theme="success">新建</cb-button>
        <cb-button @click="testRefresh">测试刷新</cb-button>
    </template>


    <template slot="table-header">
        <th>index</th>
        <th>ID</th>
        <th>名称</th>
        <th width="100">操作</th>
    </template>


    <template slot="table-body" slot-scope="{ item, index }">
        <td>{{ index }}</td>
        <td>{{ item.id }}</td>
        <td>{{ item.name }}</td>
        <td>
            <cb-button block small>编辑</cb-button>
        </td>
    </template>
</cb-search-table>
```
`cb-form` 表单容器
```
<cb-form button="保存" @submit="handleSubmit"></cb-form>
```
`cb-form-g` 表单容器组
```
<cb-form-group label="ID："></cb-form-group>
```
`cb-control` 表单容器组
```
<cb-form-control v-model="test"></cb-form-control>
```
`cb-select` 选择框
```
<cb-form-control type="select" v-model="form.type">
    <option value="1">类型一</option>
    <option value="2">类型二</option>
</cb-form-control>
```
`cb-checkbox` 复选框
```
<cb-checkbox-group inline v-model="form.data1">
    <cb-checkbox value="1">抽奖</cb-checkbox>
    <cb-checkbox value="2">满赠</cb-checkbox>
    <cb-checkbox value="3">满减</cb-checkbox>
    <cb-checkbox value="4">返利</cb-checkbox>
</cb-checkbox-group>
```
`cb-datetime` 日期时间
```
<datetime-picker v-model=" form.date" use-time></datetime-picker>
```
`cb-radio` 单选按钮
```
<cb-radio-group inline v-model="form.data1">
    <cb-radio value="1">线上活动</cb-radio>
    <cb-radio value="2">线下活动</cb-radio>
</cb-radio-group>
```
`cb-textarea` 多行文本
```
<cb-form-control type="textarea" v-model="form.desc"></cb-form-control>
```
`cb-file` 图片文件
```
<cb-form-control type="file" v-model="form.file">选择图片文件</cb-form-control>
```
`cb-color` 颜色选择
```
<color-picker v-model="form.color"></color-picker>
```
`cb-steps` 步骤条
```
<cb-steps v-model="step">
    <cb-step>第一步</cb-step>
    <cb-step>第一步</cb-step>
    <cb-step>第一步</cb-step>
    <cb-step>第一步</cb-step>
</cb-steps>
```