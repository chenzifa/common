1. or  create a new repository on the command line
	git init
	git add Readme.md
	git commit -m "first commit"
	git remote add origin git@github.com:qincaixiaoyv/gitstudy.git
	git push -u origin master
	注：初次提交，远程仓库为空，需要加 -u . 下次提交不需要加
2. or push an existing repository from the command line

	git remote add origin git@github.com:qincaixiaoyv/gitstudy.git
	git push -u origin master
3. or import code from another repository
	无


4 修改远程仓库地址
git remote set-url origin https://github.com/qincaixiaoyv/gitstudy.git


5.查看邮箱，用户名（ssh）
git config user.name
git config user.email

6.设置用户名。邮箱
git config --global user.name "username"
git config --global user.email "email"

7. 处理https:...提交输入用户名密码
git config -l:列出所有
修改remote中的url地址为
url=https://用户名:密码@github.com/qincaixiaoyv/gitstudy.git
