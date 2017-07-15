ruby 开发记录
===============
## 察看gem安装情况
### 命令
    gem environment
### 语法
    ![image text](https://raw.githubusercontent.com/byteguitar/ruby-/master/images/1041371_16.jpg)
### Test Unit
    使用　require 'test/unit'
    assert(boolean, [msg])
    assert_equal (expected, actual, [msg])
    assert_not_equal (expected, actual, [msg])
    assert_match (pattern, string, [msg])
    assert_no_match (pattern, string, [msg])
    assert_nil (object, [msg])
    assert_not_nil (object, [msg])
    assert_instance_of (class, object, [])
    assert_kind_of (class, object, [])
    assert_ralse (Exception, …) {block}
    assert_nothing_ralsed (Exception, …) {block}
rails 开发记录
===============
##  rails 安装默认 gem install rails 
##  rails2.4.1 windows7安装问题
    ruby2.4.1 msys32 是默认在安装程序里面安装的
    ruby2.4.1 +rails5.1.2 到最后rails new webiste d的时候出错，于是换成rails 2.3
##  rails2.3安装
    官方说明
    The RubyInstaller Development Kit (DevKit) is a MSYS/MinGW based toolkit than enables you to build many of the native C/C++ extensions available for Ruby. 
    Starting with Ruby 2.4.0 it is replaced by the MSYS2 toolkit.
    
    需要先安装32位的  version of the DevKit  DevKit-mingw64-32-4.7.2-20130224-1151-sfx.exe
    然后输入以下命令 (参考https://stackoverflow.com/questions/41062649/gem-install-rails-fails-on-nio4r-windows7-ruby-2-3）
    cd devkit 
    
    ruby dk.rb init
    
    ruby dk.rb review 
    
    ruby dk.rb install 
    
    
    
    gem install rails 
## 创建一个目录webiste
    rails new website 
    website 就出现框架目录
    最后 rails server  ,http://localhost:3000就可以看到网站了
#### 注意镜像的问题
     run bundle install 会很慢，要修改 rails产生的 gemfile镜像的source 
    切换到Rails的默认模板路径下，修改Gemfile文件的source:    
    默认目录如下     
    cd $rvm_path/gems/ruby-1.9.3-p194@rails32/gems/railties3.2.5/lib/rails/generators/rails/app/templates/
     注意版本号是有所不同的

## mysql2 的安装问题 ，搞死人
    
     当前使用 的是ruby2.3 ,gem install mysql 后，安装的mysql2版本load libmysql.dll总是出现错误，于是只有自己想办法编译一个 。
     1.下载了一个mysql-connector-c-noinstall-6.0.2-win32 的包，然后解压到 f:\code\railswebsite目录下面 
        gem install mysql2 --platform=ruby -- '--with-mysql-lib="f:\code\railswebsite
        \mysqllib610\lib" --with-mysql-include="f:\code\railswebsite\mysqllib610\include"' 
     
     2. 把编译出的vender/libmysql.dll 拷贝到 ruby所安装的目录的bin的目录下
     3. 注意网站根目录下的gemfile文件需要写下 gem 'mysql2' '0.2.6'  可以指定版本号 
     参考stackoverflow :
     windows7自己编译自己的mysql2
     Uninstall your mysql2 gem by gem uninstall mysql2 and remove all mysql2 package
     Download a "MySQL Connector/C NoInstall" from MySQL which version should lower than 6.1, in my case is 6.0.2(mysql-connector-c-noinstall-6.0.2-win32.zip), and unzip to a path, such like "D:\MySQLConn"
     Install mysql2 by this command:gem install mysql2 --platform=ruby -- '--with-mysql-lib="D:\MySQLConn\lib" --with-mysql-include="D:\MySQLConn\include"'
     Run Redmine's install `bundle install --without development test'
     Check mysql2 gem gem list mysql2
     Remove the gem which not "self-compiled"(by step 3), like name "mysql2-0.3.18-x86-mingw32" and make sure there only a "self-compiled" version of mysql2, looks like "mysql2-0.3.18"
     Done!
### gem 查看包的命令 
      gem list mysql2
      gem uninstall mysql2
      比如mysql2可以安装多个版本的包
#### mysql2 非ORM的github 
     mysql2
     [Markdown](https://github.com/brianmario/mysql2）
     sequel
     [Markdown](https://github.com/jeremyevans/sequel)
### rails  数据库命令行
    1. rails generate model articleid:integer title:string content:text 
        在modles目录下会有
    2. 执行命令修改数据库db:migrate RAILS_ENV=development
##  ActiveRecord 使用
##  视图渲染模板的选择
### slim 模板
    [Markdown](http://slim-lang.com/)
