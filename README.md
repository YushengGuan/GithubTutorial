# GithubTutorial
Yusheng Guan  
Contact: ysguan@126.com  

这篇文档讲述如何使用Github开展项目协作。

## 1. 配置git环境
Windows：前往[Git官方网站](https://git-scm.com/)下载git，选择系统版本（如64-bit）对应的standalone installer，安装。可以安装在自己想安装的文件夹，可以不在C盘，按默认选项安装即可。  
Mac：系统一般自带Git。验证方式：打开“终端”，输入“git”，出现关于git的说明即可正常使用。

## 2. 连接到已有项目
**注意：从这一步开始需要科学上网。**  
### 2.1 打开VScode项目
打开VSCode，点击左上角“文件-打开文件夹”，选择一个你想保存文件的位置，如“E:/”。  
### 2.2 与已有项目进行连接
按下“ctrl”+“~”打开终端，输入“git clone 你想要克隆的地址”。  
如：
```terminal
git clone https://github.com/YushengGuan/CHEER-GD/
```
完成后，会在当前文件夹下创建一个文件夹，其中包括Github该项目下的所有文件，即出现“E:/CHEER-GD"。以后这个文件夹就与github上的项目文件夹对应。  
之后，需要对当前目录重定位。点击左上角“文件-打开文件夹”，选择CHEER-GD文件夹即可。  
### 2.3 如果是第一次使用Git
会出现以下界面，点击“Sign in with your browser”使用浏览器登陆即可。  
<img width="315" alt="4cde4846b7871e0ec6db3bc111e1aed" src="https://github.com/user-attachments/assets/a69e0830-0955-4f79-8e03-4bcc6c61d9bc" />

## 3. 向github提交修改
### 3.1 提交一般流程
在本地修改代码后，打开终端，在终端中输入以下指令：
```terminal
git add .
git commit -m "messages"
git push
```
其中，“git add .” 表示暂存所有更改。  
“git commit -m "messages"” 表示提交并留言，messages可以替换成任何语句，如：  
```terminal
git commit -m "Update the transportation model"
```
**注意：** git commit语句必须附加提交留言。  
“git push” 表示将以上更改和留言提交到github云端。

### 3.2 如果是第一次提交
在输入“git commit”命令行时，系统需要获取你的用户名和邮箱。因此，需要在终端输入以下指令：
```terminal
git config --global user.name "your_user_name"
git config --global user.email "your_email"
```
例如：
```terminal
git config --global user.name "YushengGuan"
git config --global user.email "ysguan@126.com"
```
完成上述指令后“git commit”命令行能够正常运行。后续commit不用重复输入。

## 4. 从github获取最新版本
其他用户对代码做出更改并修改后，本地可以在终端输入以下语句获取所有更改：
```terminal
git pull
```

## 5. 上传本地代码到github
### 5.1 在github上创建新仓库
首先，在dashboard点击左侧绿色“New”按钮，进入创建页面，如下所示。  
![image](https://github.com/user-attachments/assets/ff4047e0-8202-4a59-9188-949624796d82)  
然后在Repository name中填写你想要创建的仓库名称。  
之后，选择仓库属性，Public或Private。  
最后，点击最下方create repository即可。  
### 5.2 将本地代码上传到该仓库
以VSCode为例，首先打开你要上传的文件夹。左上角“文件”-“打开文件夹”，选择即可。你本地的文件夹名称**不必**与github仓库名称相同。  
之后，查看你刚创建的仓库的链接，如下图所示，复制到粘贴板。  
![image](https://github.com/user-attachments/assets/07402500-2b3a-4faa-90aa-d5615f9bdb5f)
最后，在VSCode中打开终端，依次输入以下代码即可，注意将链接换成自己对应仓库的链接。
```terminal
git remote add origin https://github.com/YushengGuan/Name.git
git branch -M main
git init
git add .
git commit -m "first commit"
git push -u origin main
```

## 6. 问题
### 6.1 连接服务器超时
如输入“git push”、“git clone”、“git pull”等指令时出现连不上服务器的情况，可以使用以下语句配置git：
```terminal
git config --global http.proxy "http://127.0.0.1:your vpn port"
git config --global https.proxy "http://127.0.0.1:your vpn port"
```
例如，clash for windows默认的vpn端口是7890，因此需要在终端输入：
```terminal
git config --global http.proxy "http://127.0.0.1:7890"
git config --global https.proxy "http://127.0.0.1:7890"
```
