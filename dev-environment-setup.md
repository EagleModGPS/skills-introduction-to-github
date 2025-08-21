# 开发环境快速配置清单 ⚙️

## 系统环境检测
你当前使用的是 **Linux 6.12.8+**，这是一个很好的开发环境！

---

## 第一步：基础工具安装

### 1. 包管理器更新
```bash
# Ubuntu/Debian
sudo apt update && sudo apt upgrade

# CentOS/RHEL
sudo yum update

# 安装基础开发工具
sudo apt install build-essential curl wget git
```

### 2. Git配置
```bash
# 安装Git（如果还没有）
sudo apt install git

# 配置用户信息
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 配置默认编辑器
git config --global core.editor "code --wait"

# 配置默认分支名
git config --global init.defaultBranch main

# 查看配置
git config --list
```

### 3. 安装VS Code
```bash
# 下载VS Code
wget -qO- https://packages.microsoft.com/keys/microsoft.asc | gpg --dearmor > packages.microsoft.gpg
sudo install -o root -g root -m 644 packages.microsoft.gpg /etc/apt/trusted.gpg.d/
sudo sh -c 'echo "deb [arch=amd64,arm64,armhf signed-by=/etc/apt/trusted.gpg.d/packages.microsoft.gpg] https://packages.microsoft.com/repos/code stable main" > /etc/apt/sources.list.d/vscode.list'

# 安装VS Code
sudo apt update
sudo apt install code
```

---

## 第二步：编程语言环境

### 1. Python环境
```bash
# 检查Python版本
python3 --version

# 安装pip
sudo apt install python3-pip

# 安装虚拟环境工具
sudo apt install python3-venv

# 创建全局虚拟环境
python3 -m venv ~/venv
echo 'source ~/venv/bin/activate' >> ~/.bashrc

# 安装常用Python包
pip install requests beautifulsoup4 pandas numpy matplotlib
```

### 2. Node.js环境
```bash
# 使用NodeSource安装最新版本
curl -fsSL https://deb.nodesource.com/setup_lts.x | sudo -E bash -
sudo apt-get install -y nodejs

# 验证安装
node --version
npm --version

# 安装全局包
npm install -g yarn
npm install -g nodemon
npm install -g create-react-app
```

### 3. Java环境
```bash
# 安装OpenJDK
sudo apt install openjdk-11-jdk

# 设置JAVA_HOME
echo 'export JAVA_HOME=/usr/lib/jvm/java-11-openjdk-amd64' >> ~/.bashrc
echo 'export PATH=$PATH:$JAVA_HOME/bin' >> ~/.bashrc

# 验证安装
java --version
javac --version
```

---

## 第三步：数据库工具

### 1. MySQL
```bash
# 安装MySQL
sudo apt install mysql-server

# 启动MySQL服务
sudo systemctl start mysql
sudo systemctl enable mysql

# 安全配置
sudo mysql_secure_installation

# 安装MySQL Workbench
sudo apt install mysql-workbench
```

### 2. PostgreSQL
```bash
# 安装PostgreSQL
sudo apt install postgresql postgresql-contrib

# 启动服务
sudo systemctl start postgresql
sudo systemctl enable postgresql

# 创建用户
sudo -u postgres createuser --interactive
```

### 3. MongoDB
```bash
# 导入MongoDB公钥
wget -qO - https://www.mongodb.org/static/pgp/server-6.0.asc | sudo apt-key add -

# 添加MongoDB源
echo "deb [ arch=amd64,arm64 ] https://repo.mongodb.org/apt/ubuntu focal/mongodb-org/6.0 multiverse" | sudo tee /etc/apt/sources.list.d/mongodb-org-6.0.list

# 安装MongoDB
sudo apt update
sudo apt install -y mongodb-org

# 启动MongoDB
sudo systemctl start mongod
sudo systemctl enable mongod
```

---

## 第四步：开发工具

### 1. Docker
```bash
# 安装Docker
sudo apt install apt-transport-https ca-certificates curl gnupg lsb-release
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg
echo "deb [arch=amd64 signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io

# 添加用户到docker组
sudo usermod -aG docker $USER

# 启动Docker
sudo systemctl start docker
sudo systemctl enable docker
```

### 2. 终端工具
```bash
# 安装Oh My Zsh
sudo apt install zsh
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"

# 安装Powerlevel10k主题
git clone --depth=1 https://github.com/romkatv/powerlevel10k.git ${ZSH_CUSTOM:-$HOME/.oh-my-zsh/custom}/themes/powerlevel10k

# 安装fzf（模糊查找）
git clone --depth 1 https://github.com/junegunn/fzf.git ~/.fzf
~/.fzf/install
```

### 3. 版本控制工具
```bash
# 安装GitHub CLI
curl -fsSL https://cli.github.com/packages/githubcli-archive-keyring.gpg | sudo dd of=/usr/share/keyrings/githubcli-archive-keyring.gpg
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/githubcli-archive-keyring.gpg] https://cli.github.com/packages stable main" | sudo tee /etc/apt/sources.list.d/github-cli.list > /dev/null
sudo apt update
sudo apt install gh

# 登录GitHub
gh auth login
```

---

## 第五步：VS Code配置

### 1. 必装扩展
```bash
# 通过命令行安装扩展
code --install-extension ms-python.python
code --install-extension ms-vscode.vscode-typescript-next
code --install-extension bradlc.vscode-tailwindcss
code --install-extension esbenp.prettier-vscode
code --install-extension ms-vscode.vscode-json
code --install-extension eamodio.gitlens
code --install-extension ms-vscode.vscode-docker
code --install-extension ms-azuretools.vscode-docker
code --install-extension redhat.vscode-yaml
code --install-extension ms-vscode.vscode-java
```

### 2. VS Code设置
创建 `~/.config/Code/User/settings.json`：
```json
{
    "editor.fontSize": 14,
    "editor.fontFamily": "'Fira Code', 'Consolas', 'Courier New', monospace",
    "editor.fontLigatures": true,
    "editor.tabSize": 2,
    "editor.insertSpaces": true,
    "editor.rulers": [80, 120],
    "editor.minimap.enabled": false,
    "editor.wordWrap": "on",
    "files.autoSave": "onFocusChange",
    "files.trimTrailingWhitespace": true,
    "files.insertFinalNewline": true,
    "terminal.integrated.fontSize": 14,
    "git.enableSmartCommit": true,
    "git.confirmSync": false,
    "python.defaultInterpreterPath": "~/venv/bin/python",
    "python.linting.enabled": true,
    "python.linting.pylintEnabled": true,
    "python.formatting.provider": "black"
}
```

### 3. 快捷键配置
创建 `~/.config/Code/User/keybindings.json`：
```json
[
    {
        "key": "ctrl+shift+p",
        "command": "workbench.action.quickOpen"
    },
    {
        "key": "ctrl+`",
        "command": "workbench.action.toggleTerminal"
    },
    {
        "key": "ctrl+shift+f",
        "command": "workbench.action.findInFiles"
    }
]
```

---

## 第六步：Shell配置

### 1. Bash配置
编辑 `~/.bashrc`：
```bash
# 添加以下内容到 ~/.bashrc

# 别名
alias ll='ls -alF'
alias la='ls -A'
alias l='ls -CF'
alias ..='cd ..'
alias ...='cd ../..'
alias grep='grep --color=auto'
alias fgrep='fgrep --color=auto'
alias egrep='egrep --color=auto'

# Git别名
alias gs='git status'
alias ga='git add'
alias gc='git commit'
alias gp='git push'
alias gl='git log --oneline'
alias gb='git branch'

# Python虚拟环境
alias venv='source ~/venv/bin/activate'

# 函数
mkcd() {
    mkdir -p "$1" && cd "$1"
}

# 提示符
PS1='\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
```

### 2. 环境变量
编辑 `~/.bashrc`：
```bash
# 添加环境变量
export PATH="$HOME/.local/bin:$PATH"
export EDITOR="code"
export VISUAL="code"
export BROWSER="firefox"

# Python
export PYTHONPATH="$HOME/.local/lib/python3.8/site-packages:$PYTHONPATH"

# Node.js
export NODE_ENV=development
```

---

## 第七步：测试环境

### 1. 创建测试项目
```bash
# 创建测试目录
mkdir ~/dev-test && cd ~/dev-test

# Python测试
python3 -c "print('Python环境正常!')"

# Node.js测试
node -e "console.log('Node.js环境正常!')"

# Git测试
git init
echo "# 测试项目" > README.md
git add .
git commit -m "初始提交"
```

### 2. 验证工具安装
```bash
# 检查所有工具
echo "=== 环境检查 ==="
echo "Python: $(python3 --version)"
echo "Node.js: $(node --version)"
echo "npm: $(npm --version)"
echo "Git: $(git --version)"
echo "Docker: $(docker --version)"
echo "VS Code: $(code --version)"
```

---

## 第八步：性能优化

### 1. 系统优化
```bash
# 增加文件描述符限制
echo "* soft nofile 65536" | sudo tee -a /etc/security/limits.conf
echo "* hard nofile 65536" | sudo tee -a /etc/security/limits.conf

# 优化交换分区
echo 'vm.swappiness=10' | sudo tee -a /etc/sysctl.conf
```

### 2. 开发工具优化
```bash
# 配置npm缓存
npm config set cache ~/.npm-cache

# 配置pip缓存
pip config set global.cache-dir ~/.pip-cache
```

---

## 常见问题解决

### 1. 权限问题
```bash
# 修复权限
sudo chown -R $USER:$USER ~/.config
sudo chown -R $USER:$USER ~/.local
```

### 2. 网络问题
```bash
# 配置代理（如果需要）
export http_proxy=http://proxy:port
export https_proxy=http://proxy:port
```

### 3. 磁盘空间
```bash
# 清理缓存
sudo apt clean
npm cache clean --force
pip cache purge
```

---

## 下一步行动

1. **重启终端**：让所有配置生效
2. **测试所有工具**：确保安装正确
3. **创建第一个项目**：开始编程实践
4. **学习工具使用**：阅读相关文档
5. **加入社区**：参与开源项目

---

## 维护建议

### 定期更新
```bash
# 系统更新
sudo apt update && sudo apt upgrade

# 工具更新
npm update -g
pip list --outdated
```

### 备份配置
```bash
# 备份配置文件
cp ~/.bashrc ~/.bashrc.backup
cp ~/.config/Code/User/settings.json ~/.config/Code/User/settings.json.backup
```

---

记住：**好的开发环境是高效编程的基础**！花时间配置好环境，会让你的编程之路更加顺畅。

祝你编程愉快！🎉