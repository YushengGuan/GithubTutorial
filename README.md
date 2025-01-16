# GithubTutorial
Yusheng Guan  
Contact: ysguan@126.com  

这篇文档讲述如何使用Github开展项目协作。

## 1. 配置git环境
前往[Git官方网站](https://git-scm.com/)下载git，选择系统版本（如64-bit）对应的standalone installer，安装。可以安装在自己想安装的文件夹，可以不在C盘，按默认选项安装即可。

## 2. 连接到已有项目
**注意：从这一步开始需要科学上网。**  
2.1 在你想保存项目的位置新建一个文件夹，打开VSCode，点击左上角“文件-打开文件夹”，并选中你刚建立的文件夹。以后这个文件夹就与github上的项目文件夹对应。  
2.2 按下“ctrl”+“~”打开终端，输入“git clone 你想要克隆的地址”。  
如：
```terminal
git clone https://github.com/YushengGuan/CHEER-GD
```
等待即可。
## 3. 向github提交修改
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
“git push” 表示将以上更改和留言提交到github云端。
## 4. 从github获取最新版本
其他用户对代码做出更改并修改后，本地可以在终端输入以下语句获取所有更改：
```terminal
git pull
```
## 5. 其它问题
如输入“git push”出现连不上服务器的情况，可以使用以下语句配置git：
```terminal
git config --global http.proxy "http://127.0.0.1:your vpn port"
git config --global https.proxy "http://127.0.0.1:your vpn port"
```
例如，clash for windows默认的vpn端口是7890，因此需要在终端输入：
```terminal
git config --global http.proxy "http://127.0.0.1:7890"
git config --global https.proxy "http://127.0.0.1:7890"
```
