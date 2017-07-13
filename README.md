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
     
