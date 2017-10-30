## 开发规范

### 准备

```bash
npm install fed-easy-boilerplate -g
sn init
模板名称填vue
项目名称自定义，例如：sn-button
npm run dev //运行项目
```
### 开发思路

目前开发是采用分批开发策略，即暂时每个组件一个仓库，之后能够分批publish，最后会统一合并为版本为`nevermore`主库。

### 样式问题
目前，样式每个仓库单独一个样式文件，例如，sn-button.less。公共样式，会单独维护，统一引入。最终会将所有样式统一维护一个主目录，例如 `styles`文件夹。所以单文件组件就暂时不需要写`<style></style>`,可以这样写：

```bash
<style scoped lang="less">
@import '固定地址' + ‘自定义的名称，例如：sn-button.less’
</style>

```

