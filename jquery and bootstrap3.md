rails 5.1.2  bootstrap3 和jquery使用
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
    

   
asset pipelineks的理解
=====
## 
      在 Rails 的早期版本中，所有静态资源文件都放在 public 文件夹的子文件夹中，例如 images、javascripts 和 stylesheets 子文件夹。
        当 Rails 开始使用 Asset Pipeline 后，就推荐把静态资源文件放在 app/assets 文件夹中，并使用 Sprockets 中间件处理这些文件。
## 静态文件 图片的路径注意
### 1. app/assets目录下
     ```Ruby
         app/assets/images/01.jpg
     ```       
      模板写法 image_tag("01.jpg")
      
* app/assets/images/landscape/01.jpg     image_tag("landscape/01.jpg")
###  2 pubic/images 目录下
* public/images/01.jpg   对应写法 <img src="/images/01.jpg />   **注意第一个符号/不能少**
* public/images/landscape/01.jpg   对应写法 <img src="/images/landscape/01.jpg />
     
