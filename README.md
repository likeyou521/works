# works Demo Run
	#framework 地址
		https://github.com/wobase/pworks
	
	#PHP版本检查 要求PHP 5.3+
		查看版本命令 php -v

	#PHP扩展检查 要求有 *DOM *APCu *mbstring  *Mcrypt
		查看扩展命令 php -m 

	#单元测试框架PHPUnit 要求 4.8+


	#修改php.ini include_path路径  E:\phpstudy\WWW\pworks\pear下有pworks文件
		; Windows: "\path1;\path2"
		include_path = ".;E:\phpstudy\WWW\pworks\pear"

	#重新用pworks.20170524.tar.gz的pworks覆盖 pear下的pworks

	#修改pworks.xml <action type="rest" url="/ticket" method="post" id="ticket.Create"/>  的method 为get 
		<action type="rest" url="/ticket" method="get" id="ticket.Create"/> 

	#demo目录下新建重写规则重写规则  
		# 开启 rewrite 功能
		Options +FollowSymlinks
		RewriteEngine on

		# 重写规则
	#*****	Creating a new branch is quick AND simple.
		RewriteRule ^ticket$   index\.php\?action=restful&url=$1&method=%{REQUEST_METHOD} [QSA,L]
