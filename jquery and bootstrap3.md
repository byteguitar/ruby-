rails 5.1.2
======

## bootstrap3 install   
      download bootstrap3
      拷贝资源文件 
      copy css to app/application/sytlesheets
      copy js  to app/application/javascripts
## jquery install 
      下载jquery
      copy to app/application/javascripts
## 修改application/application.js 
      //= require jquery    *注意这个地方的顺序，放在后面会出现bootstrap找不到jquery*
      //= require rails-ujs
      //= require turbolinks
      //= require_tree .
      //= require bootstrap.min
    

   
turbolinks的理解
=====
