session 登陆
=====================
# ApplicationController 修改
### 1. 增加helper current_user 函数
      随时在页面的before_action 前检查 session[:user_id],并且从数据库中得到userid
      
### 2. 增加require_login helper函数 ，重定向页面

     def require_login
           redirect_to referer unless session[:user_id]
     end

### 3.  某些时候页面不需要检查登陆否，比如首页默认显示和用户无关的信息
      skip_before_action :  current_usr
    
