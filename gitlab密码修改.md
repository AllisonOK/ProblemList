####问题：Clone failed: Authentication failed for 'http://118.24.87.219:8099/lisheng/rich_dinosaur.git'
```
原因：以前保存gitlab的账号和密码，修改了gitlab的账号和密码之后，Android studio没有提示重新弄输入，所以要更改之前的配置
解决方案：在命令行里输入 git config --system --unset credential.helper  回车
然后在 git clone 加 url  ,就会提示让你输入用户名和密码
配置用户名和邮箱 ：git config --global user.name "xxx"
				   git config --global user.email "xxx@xxx.com"
```