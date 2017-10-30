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
### git使用规范
目前每个组建单独一个仓库，需要单独发布。意味着每个仓库，都至少需要`master`和`develop`俩个分支。开发阶段在`develop`完成，需要发布则合并代码到`master`分支进行合并。

#### 第一步：新建分支
    
  ```
  # 新建自己的开发分支
  git checkout -b develop
  ```
#### 第二步：提交分支
  ```
  git add -all
  git status
  git commit --verbose
  ```
  git commit 命令的verbose参数，会列出 diff 的结果。清晰的看到自己修改过的内容
  
#### 第三步：撰写提交信息
提交commit时，必须要给出完整扼要的提交信息，避免语义不明确
#### 第三步：与远程仓库保持同步
  ```
  git fetch origin develop
  git rebase origin/develop
  ```
#### 第四步：推送到远程仓库
  ```
  git push origin develop
  ```