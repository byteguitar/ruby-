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
