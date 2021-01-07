## 概念

### 版本控制

记录文件变化，并可以 进行查阅 各版本 修订情况的 软件

### 版本控制系统

#### 本地

单机运行

故障后 影响很大

#### 集中化

服务器 保存 所有

客户端 保存 最新

必须联网

服务器 故障后 影响很大

SVN

#### 分布式

服务器 保存 所有

客户端 保存 完整备份

支持离线 本地提交更新

Git

### git

- 开源 的 分布式 版本控制软件

- 记录快照，不是 差异比较

  保存 类似备份的 新文件

  若没有 更新，则 只是 保存链接 指向 上个版本

  版本切换 很快

  但 消耗空间

- 大多操作 都是 本地运行

  但 同步服务器 还需要联网

- 三个区域

  工作区

  > 编辑

  暂存区

  > 标记 但未提交

  仓库

  > 提交到 本地

- 文件三种状态

  已修改 modified

  > 表示修改了文件，但还没将修改的结果放到暂存区

  已暂存 staged

  > 表示对已修改文件的当前版本做了标记，使之包含在下次提交的列表中

  已提交 committed

  > 表示文件已经安全地保存在本地的 Git 仓库中

### SVN

- 基于 差异比较

- 记录文件 变化的差异

  节省空间

  但耗时，效率低

- 切换版本 是将 原版本 应用 每个中间版本的 差异

## 命令

### 配置 用户名 和邮箱

```powershell
git config --global user.name

git config --global user.email
```

会被写入到 `C:/Users/用户名文件夹/.gitconfig` 文件中

### 查看所有设置

```powershell
git config --list --global
```

### 帮助信息

```powershell
git help <verb>
```

- verb 

  选项，如config

### 现有目录初始化仓库

在此目录打开 git

```powershell
git init
```

转化为 git托管的 目录

`.git` 文件 表示 git 托管了

### 得到 目录的 状态

```powershell
	git status

```

- -s / --short

  精简形式

### 添加文件跟踪

```powershell
git add <file>
```

- file

  要撤销的 文件路径

- `.`

  添加目录下所有 未同步到 暂存区

跟踪 指定 文件

可以使用 文件路径

将文件 添加到 暂存区

### 提交

```powershell
git commit -m xxxxxx
```

提交 目录，且添加 描述 xxxxxx

提交 到 本地仓库，形成版本号

### 查看日志

```powershell
git log
```

### 切换版本

```powershell
git reset --hard <hash>
```

- hash

  版本 hash 值

不处理 空文件夹

### 撤销更改

```powershell
git checkout <file>
```

- file

  要撤销的 文件路径

只针对 工作区

### 撤销 暂存区中的文件到 工作区

```powershell
git reset HEAD <file>
```

- file

  要撤销的 文件路径

### 删除 文件

```powershell
git rm <file>
```

- file

  要撤销的 文件路径

## 其他

### 工作区中的文件状态

#### 未管理

- 未跟踪

  不被 Git 所管理的文件

#### 已管理

- 未修改（Unmodified）
- 已修改（Modified）
- 已暂存（Staged）