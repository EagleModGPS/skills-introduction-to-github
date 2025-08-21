# 编程软件快速上手指南 🚀

## 目录
1. [代码编辑器](#代码编辑器)
2. [版本控制工具](#版本控制工具)
3. [终端和命令行](#终端和命令行)
4. [包管理工具](#包管理工具)
5. [数据库工具](#数据库工具)
6. [API测试工具](#api测试工具)
7. [学习路径建议](#学习路径建议)

---

## 代码编辑器

### 1. Visual Studio Code (VS Code) - 推荐新手
**适用场景**: 全栈开发、前端、后端、Python、JavaScript等

**快速上手步骤**:
1. **安装**: 从官网下载安装
2. **基础快捷键**:
   - `Ctrl+N`: 新建文件
   - `Ctrl+S`: 保存
   - `Ctrl+Z`: 撤销
   - `Ctrl+F`: 查找
   - `Ctrl+Shift+P`: 命令面板
   - `Ctrl+`: 打开/关闭终端

3. **必装扩展**:
   - **Python**: Python语言支持
   - **JavaScript (ES6) code snippets**: JS代码片段
   - **Auto Rename Tag**: HTML标签自动重命名
   - **Bracket Pair Colorizer**: 括号配对高亮
   - **GitLens**: Git增强功能
   - **Live Server**: 实时预览HTML

4. **实用技巧**:
   - 使用 `Ctrl+Shift+P` 打开命令面板，输入命令
   - 多光标编辑: `Alt+Click` 或 `Ctrl+Alt+↑/↓`
   - 代码折叠: `Ctrl+Shift+[` 或 `Ctrl+Shift+]`

### 2. PyCharm - Python专用
**适用场景**: Python开发、数据科学

**快速上手**:
1. 选择Community版本（免费）
2. 创建新项目时选择解释器
3. 使用内置终端运行代码
4. 利用代码补全和错误提示

### 3. IntelliJ IDEA - Java专用
**适用场景**: Java开发、Android开发

**快速上手**:
1. 选择Community版本（免费）
2. 配置JDK
3. 使用Maven或Gradle管理依赖
4. 利用强大的重构工具

---

## 版本控制工具

### Git - 必备技能
**快速上手步骤**:

1. **安装配置**:
```bash
# 安装Git
sudo apt-get install git  # Ubuntu/Debian
brew install git          # macOS

# 配置用户信息
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

2. **基础命令**:
```bash
# 初始化仓库
git init

# 查看状态
git status

# 添加文件到暂存区
git add filename
git add .  # 添加所有文件

# 提交更改
git commit -m "提交信息"

# 查看提交历史
git log

# 创建分支
git branch branch-name

# 切换分支
git checkout branch-name
# 或使用新语法
git switch branch-name

# 合并分支
git merge branch-name
```

3. **实用技巧**:
   - 使用 `.gitignore` 忽略不需要版本控制的文件
   - 使用 `git stash` 临时保存工作进度
   - 使用 `git reset` 撤销提交

### GitHub Desktop - 图形化Git
**适用场景**: 不熟悉命令行的新手

**优势**:
- 可视化操作
- 直观的界面
- 内置代码编辑器

---

## 终端和命令行

### 1. 基础命令
```bash
# 文件操作
ls          # 列出文件
cd          # 切换目录
pwd         # 显示当前路径
mkdir       # 创建目录
rm          # 删除文件
cp          # 复制文件
mv          # 移动文件

# 查看文件
cat         # 显示文件内容
less        # 分页查看
head        # 查看文件开头
tail        # 查看文件结尾

# 查找
find        # 查找文件
grep        # 搜索文本
```

### 2. 包管理器
```bash
# Ubuntu/Debian
sudo apt update
sudo apt install package-name

# macOS
brew install package-name

# CentOS/RHEL
sudo yum install package-name
```

---

## 包管理工具

### 1. npm (Node.js)
```bash
# 初始化项目
npm init

# 安装依赖
npm install package-name
npm install -g package-name  # 全局安装

# 运行脚本
npm run script-name
```

### 2. pip (Python)
```bash
# 安装包
pip install package-name

# 创建虚拟环境
python -m venv venv
source venv/bin/activate  # Linux/macOS
venv\Scripts\activate     # Windows

# 导出依赖
pip freeze > requirements.txt
```

### 3. Maven (Java)
```xml
<!-- pom.xml 示例 -->
<dependencies>
    <dependency>
        <groupId>org.springframework.boot</groupId>
        <artifactId>spring-boot-starter-web</artifactId>
    </dependency>
</dependencies>
```

---

## 数据库工具

### 1. MySQL Workbench
- 图形化界面
- 可视化数据库设计
- SQL编辑器

### 2. MongoDB Compass
- MongoDB图形化客户端
- 数据可视化
- 查询构建器

### 3. DBeaver
- 通用数据库工具
- 支持多种数据库
- 免费开源

---

## API测试工具

### 1. Postman
**快速上手**:
1. 下载安装
2. 创建新请求
3. 设置请求方法（GET、POST等）
4. 添加请求头和参数
5. 发送请求查看响应

### 2. Insomnia
- 轻量级API测试工具
- 支持GraphQL
- 免费使用

---

## 学习路径建议

### 新手阶段 (1-2周)
1. **安装VS Code**，熟悉基本操作
2. **学习Git基础命令**，创建GitHub账号
3. **掌握终端基本命令**
4. **选择一个包管理器**（根据你的主要编程语言）

### 进阶阶段 (1个月)
1. **深入学习VS Code高级功能**
2. **掌握Git分支管理**
3. **学习使用Postman测试API**
4. **熟悉数据库工具**

### 高级阶段 (持续学习)
1. **学习Docker容器化**
2. **掌握CI/CD工具**
3. **学习云平台工具**（AWS、Azure、GCP）
4. **探索专业IDE**（根据项目需求）

---

## 实用技巧

### 1. 提高效率的方法
- **使用快捷键**: 每个工具都要熟悉常用快捷键
- **配置别名**: 为常用命令创建别名
- **使用代码片段**: 创建常用代码模板
- **自动化脚本**: 编写脚本自动化重复任务

### 2. 学习资源
- **官方文档**: 每个工具都有详细的官方文档
- **YouTube教程**: 视频教程更直观
- **Stack Overflow**: 解决具体问题
- **GitHub**: 查看开源项目学习最佳实践

### 3. 实践建议
- **小项目开始**: 从简单的个人项目开始练习
- **模仿开源项目**: 学习优秀项目的工具使用方式
- **记录学习过程**: 写博客或笔记记录学习心得
- **参与开源**: 通过贡献开源项目提升技能

---

## 常见问题解决

### 1. 工具安装问题
- 检查系统要求
- 查看官方安装指南
- 搜索错误信息

### 2. 配置问题
- 查看配置文件语法
- 使用默认配置开始
- 逐步自定义配置

### 3. 性能问题
- 关闭不必要的扩展
- 定期清理缓存
- 升级到最新版本

---

记住：**熟能生巧**！最好的学习方法是**边学边用**，在实际项目中练习这些工具。从简单的项目开始，逐步增加复杂度，你会发现自己越来越熟练！

祝你编程之路顺利！🎉