1. or  create a new repository on the command line
	git init
	git add Readme.md
	git commit -m "first commit"
	git remote add origin git@github.com:qincaixiaoyv/gitstudy.git
	git push -u origin master
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
