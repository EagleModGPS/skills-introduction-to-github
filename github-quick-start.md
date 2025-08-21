# GitHub 快速上手指南 🐙

## 你当前的状态
你正在学习GitHub的基础操作，包括创建分支、提交文件、发起Pull Request等。这是一个很好的开始！

---

## 第一步：理解基本概念

### 什么是Git？
- **版本控制系统**：记录文件的所有变化历史
- **分布式**：每个开发者都有完整的代码副本
- **协作工具**：多人可以同时开发同一个项目

### 什么是GitHub？
- **代码托管平台**：存储和管理代码的地方
- **社交编程**：与其他开发者协作
- **项目管理**：Issues、Projects、Actions等工具

---

## 第二步：基础Git命令

### 1. 初始化仓库
```bash
# 创建新的Git仓库
git init

# 克隆现有仓库
git clone https://github.com/用户名/仓库名.git
```

### 2. 查看状态
```bash
# 查看当前状态
git status

# 查看文件变化
git diff
```

### 3. 添加和提交
```bash
# 添加文件到暂存区
git add 文件名
git add .  # 添加所有文件

# 提交更改
git commit -m "描述你的更改"
```

### 4. 查看历史
```bash
# 查看提交历史
git log

# 查看简洁历史
git log --oneline
```

---

## 第三步：分支操作

### 1. 分支基础
```bash
# 查看所有分支
git branch

# 创建新分支
git branch 分支名

# 切换到分支
git checkout 分支名
# 或使用新语法
git switch 分支名

# 创建并切换到新分支
git checkout -b 新分支名
git switch -c 新分支名
```

### 2. 合并分支
```bash
# 切换到主分支
git checkout main

# 合并分支
git merge 分支名
```

---

## 第四步：GitHub操作

### 1. 推送代码
```bash
# 第一次推送，设置上游分支
git push -u origin main

# 后续推送
git push

# 推送特定分支
git push origin 分支名
```

### 2. 拉取更新
```bash
# 拉取远程更新
git pull

# 拉取特定分支
git pull origin 分支名
```

---

## 第五步：Pull Request流程

### 1. 创建PR的步骤
1. **Fork仓库**：点击GitHub页面右上角的Fork按钮
2. **克隆到本地**：`git clone https://github.com/你的用户名/仓库名.git`
3. **创建分支**：`git checkout -b feature-branch`
4. **修改代码**：进行你的更改
5. **提交更改**：
   ```bash
   git add .
   git commit -m "添加新功能"
   ```
6. **推送到远程**：`git push origin feature-branch`
7. **创建PR**：在GitHub页面点击"Compare & pull request"

### 2. PR最佳实践
- **清晰的标题**：描述你的更改
- **详细的描述**：说明为什么需要这个更改
- **关联Issue**：使用 `#123` 关联相关Issue
- **请求审查**：邀请团队成员审查代码

---

## 第六步：常用工作流程

### 1. 日常开发流程
```bash
# 1. 获取最新代码
git pull origin main

# 2. 创建功能分支
git checkout -b feature/new-feature

# 3. 开发功能
# ... 编写代码 ...

# 4. 提交更改
git add .
git commit -m "添加新功能"

# 5. 推送到远程
git push origin feature/new-feature

# 6. 创建Pull Request
# 在GitHub网页上操作
```

### 2. 修复Bug流程
```bash
# 1. 创建修复分支
git checkout -b fix/bug-description

# 2. 修复Bug
# ... 修复代码 ...

# 3. 提交修复
git add .
git commit -m "修复: 描述修复的问题"

# 4. 推送并创建PR
git push origin fix/bug-description
```

---

## 第七步：实用技巧

### 1. 撤销操作
```bash
# 撤销最后一次提交
git reset --soft HEAD~1

# 撤销工作区的更改
git checkout -- 文件名

# 撤销暂存区的更改
git reset HEAD 文件名
```

### 2. 查看信息
```bash
# 查看远程仓库信息
git remote -v

# 查看分支关系
git branch -vv

# 查看文件历史
git log --follow 文件名
```

### 3. 临时保存工作
```bash
# 保存当前工作
git stash

# 查看保存的工作
git stash list

# 恢复保存的工作
git stash pop
```

---

## 第八步：GitHub高级功能

### 1. Issues（问题跟踪）
- **创建Issue**：报告Bug或请求新功能
- **标签**：使用标签分类Issue
- **里程碑**：组织Issue到特定版本
- **分配**：分配给团队成员

### 2. Projects（项目管理）
- **看板**：可视化任务进度
- **自动化**：自动移动卡片
- **时间线**：查看项目进度

### 3. Actions（自动化）
- **CI/CD**：自动测试和部署
- **代码质量**：自动检查代码风格
- **通知**：自动发送通知

---

## 第九步：常见问题解决

### 1. 合并冲突
```bash
# 当出现合并冲突时
git status  # 查看冲突文件
# 手动编辑冲突文件
git add .   # 标记冲突已解决
git commit  # 完成合并
```

### 2. 忘记提交
```bash
# 修改最后一次提交
git commit --amend

# 修改提交信息
git commit --amend -m "新的提交信息"
```

### 3. 回退版本
```bash
# 回退到特定提交
git reset --hard 提交ID

# 创建回退提交（推荐）
git revert 提交ID
```

---

## 第十步：学习资源

### 1. 官方文档
- [Git官方文档](https://git-scm.com/doc)
- [GitHub Guides](https://guides.github.com/)
- [GitHub Docs](https://docs.github.com/)

### 2. 练习平台
- [GitHub Learning Lab](https://lab.github.com/)
- [GitHub Skills](https://skills.github.com/)

### 3. 视频教程
- YouTube上的Git和GitHub教程
- B站上的中文教程

---

## 实践建议

### 1. 从小项目开始
- 创建个人项目练习Git操作
- 使用GitHub Pages创建个人网站
- 参与开源项目的文档改进

### 2. 建立好习惯
- **经常提交**：小步快跑，经常提交
- **清晰的提交信息**：用中文或英文描述更改
- **使用分支**：每个功能使用独立分支
- **及时同步**：经常拉取最新代码

### 3. 参与社区
- 关注感兴趣的开源项目
- 从简单的Issue开始贡献
- 参与讨论和代码审查

---

## 下一步学习方向

1. **深入学习Git**：学习高级命令和概念
2. **GitHub Actions**：学习自动化工作流
3. **代码审查**：学习如何审查他人代码
4. **项目管理**：学习使用GitHub的项目管理功能
5. **开源贡献**：参与开源项目，提升技能

---

记住：**实践是最好的老师**！多动手操作，遇到问题就搜索解决方案。GitHub有强大的社区支持，你总能找到帮助。

祝你GitHub之旅顺利！🚀