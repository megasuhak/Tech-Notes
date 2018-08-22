
#### PHP 代码规范

##### 编写目的
为了更好的提高技术开发的工作效率，保证开发的有效性和合理性，并可最大程度的提高程序代码的可读性和可重复利用性，指定此规范。开发团队根据自己的实际情况，可以对本规范进行补充或裁减。

##### 定义
* 必须 (MUST)：绝对，严格遵循，请照做，无条件遵守；
* 一定不可 (MUST NOT)：禁令，严令禁止；
* 应该 (SHOULD) ：强烈建议这样做，但是不强求；
* 不该 (SHOULD NOT)：强烈不建议这样做，但是不强求；
* 可以 (MAY) 和 可选 (OPTIONAL) ：选择性高一点，在这个文档内，此词语使用较少；

##### 文件
1. PHP文件 必须 使用 `<?php `长标签作为开始标签； 一定不可 使用其它自定义标签。
2. PHP文件 必须 且只可使用 以UTF-8无BOM格式编码。
3. 所有PHP文件 必须 以一个空白行作为结束。
4. 纯PHP代码文件 应该 省略最后的 ?> 结束标签。
5. 文件的命名 可以 为 大写字母开头的骆驼式，也 可以 全为小写字母，单词之间以下划线分隔。

##### 注释
1. 文件/类 级注释
```
/**
 * System User Model
 *
 * @package     InStore
 * @subpackage  Model
 * @author      ray.xu <ray.xu@wailianvisa.com>
 * @date        2017-11-23
 */
```

2. 函数 级注释
```
/**
 *  Get records by condition
 *
 *  @param   array $params
 *  @access  public
 *  @return  array | false
 *
 *  <code>
 *         ....
 *  </code>
 */
```

3. 行 级注释
```
// 行级注释采用双斜线，尽量在一行内完成
```

##### 命名空间和类
1. PHP 5.3 及以后版本的代码 必须 使用正式的命名空间。
2. 每个类都独立为一个文件，且命名空间至少有一个层次。Ex：`namespace InStore\Model;`
3. 类的命名 必须 为 大写字母开头的骆驼式。Ex：`SystemUser`

##### 函数
1. 所有函数都 必须 添加访问修饰符。
2. 不该 使用下划线作为前缀，来区分方法是 protected 或 private。
3. 函数名称后 一定不可 有空格符，其开始花括号 必须 独占一行，结束花括号也 必须 在方法主体后单独成一行。参数左括号后和右括号前 一定不可 有空格。
1. 函数的命名 应该 为 小写字母开头的骆驼式。Ex：`getSystemUserListByCondition()`

##### 常量
1. 常量的命名 必须 全为大写字母，单词之间以下划线分隔。Ex：`DIR_WRITE_MODE`

##### 变量
1. 变量的命名 可以 为 小写字母开头的骆驼式，也 可以 全为小写字母，单词之间以下划线分隔。Ex：`$params，$return_url，$fieldsComment`

##### 控制结构
1. 控制结构关键词后 必须 有一个空格。
2. 左括号 ( 后 一定不可 有空格。
3. 右括号 ) 前也 一定不可 有空格。
4. 右括号 ) 与开始花括号 { 间 必须 有一个空格。
5. 结构体主体 必须 要有一次缩进。
6. 结束花括号 } 必须 在结构体主体后单独成行。



PHP 标准规范
https://psr.phphub.org/


CodeIgniter 代码规范

一. 文件，Class，Function 命名和注释规范

类：骆驼型，第一个字母大写。Ex：SystemUser
函数：骆驼型，第一个字母小写。Ex：getSystemUserListByCondition()
变量：骆驼型，第一个字母小写。
常量：全大写+下划线连接。

数据库名：下划线连接。Ex：admin_demo
表名：下划线连接。Ex：system_user
字段名：下划线连接。如：moblie_phone


1. Model 层：SystemUserModel.php

/**
* System User Model
*
* @package     Laputa admin demo
* @subpackage Model
* @author      xuyixing <raynorxyx@hotmail.com>
* @date        2015-1-23
*/
class SystemUserModel extends CI_Model
{
    public function __construct()
     {
          # code...
     }

    /**
     *  Get records by condition
     *
     *  @param  array $params
     *  @access  public
     *  @return  array | false
     *
     *  <code>
     *         ....
     *  </code>
     */
    public function getSystemUserListByCondition($params)     
     {
          # code...
     }
}

2. Controller层：SystemUser.php

/**
* System User Controller
*
* @package     Laputa admin demo
* @subpackage Controller
* @author      xuyixing <raynorxyx@hotmail.com>
* @date        2015-1-23
*/
class SystemUser extends CI_Controller
{
     function __construct(){
          parent::__construct();
     }

    /*
     * SystemUser list
     */
     public function lists()
     {
          # code...
     }
}

3. View层：
SystemUser/list.php
SystemUser/create.php
SystemUser/update.php
SystemUser/view.php

二. svn/git 代码提交注释规范

【修改类型】【概要说明】【完成度%】【提交人】【提交时间】

例：
【新增】【新增文件index.php，作为网站入口】【100%】【ray】【2011-11-9】
【修改】【修改bug1002，改掉了****】【100%】【ray】【2011-11-9】
【删除】【删除多余文件 ***.php】【100%】【ray】【2011-11-9】
【其他】【移动文件***.php到***文件夹】【100%】【ray】【2011-11-9】
