## 1 
### 1.1 使用命令创建项目
#### 打开终端
* 进入某个目录（需要的文件）
  >cd D:\Total_collection_box\qianhouduan_changku
#### 执行命令创建项目
>"c:\python39\Scripts\django-admin.exe": startproject 项目名称
>如果 C:\python39\Scripts 已加入环境系统环境变量
>> django-admin startproject mysite  
**这两者方法，我用的是第二种，第一种没明白**
创建成功显示：
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/797d5fe6-2f95-4db0-a511-9c8bf8f8ea6b)


### 1.2 使用Pycharm创建项目
1.2.1 ![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/a887546f-248a-435f-9584-7977609b4bee)


### 1.3 两种创建项目区别
特殊说明：
* 命令行，创建的项目是标准的
* pycharm,在标准的基础上默认给加点东西
 * pycharm创建了一个templates目录【删除】
 * settings.py中【删除57行中的（'DIRS': []）中[]的内容】 
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/fd4ffe75-cfae-4f45-b986-b727ef98ae8a)


### 1.4 默认文件介绍
mysite
——manage.py                  【项目的管理，启动项目、创建app、数据管理】 【不要动】  【***常常用***】
——mysite
————_init_.py
————asgi.py                  【接收网络请求】  【不要动】
————settings.py            【项目配置】                         【***常常修改***】
————urls.py                   【uRL和函数的对应关系】     【***常常修改***】
————wsgi.py                  【接收网络请求】【不要动】


### 1.5 创建APP 
>项目
>- app, 用户管理[表结构, 函数，HTML模板，CSS]  
注意：开发比较简洁，用不到多APP，一般情况下，一个项目下创建1个app即可。
命令行输入：>python manage.py startapp app0X
默认文件介绍
app01
-migrations      【固定，不用动】数据库变更记录
--__init__.py
-__init_.py
-admin.py        【固定，不用动】 django默认提供了admin后台管理
-apps.py          【固定，不用动】app启动类
-models.py      【***重要***】对数据库操作
-tests.py          【固定，不用动】单元测试
-views.py         【***重要***】函数


## 2 快速上手
2.1 确保app已注册【settings.py】
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/c784394c-4209-4ce1-bd53-d2816199d59f)
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/09439513-f0ed-4097-8adc-dfa946e3f6ca)

2.2 编写URL和视图函数对应关系【urls.py】
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/40f21c79-d929-459a-a93d-4d17ecf64caf)

2.3 编写视图函数 【views.py】
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/75a67e45-d538-4e83-aad1-4e55e1a9b86c)

2.4 启动django项目
2.4.1 命令行启动
>python manage.py runserver![DM_20231227202031_001](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/30be48b0-c9cf-47a4-8ad1-3b35a851fbe7)

2.4.2Pycharm启动
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/d5651120-946c-4f5a-8a94-b6bad3b3fc78)


## 3 再编写一个文件
### 3.1 urls代码编写
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/5106aeb6-d201-4235-a51d-6f315bb1270e)

### 3.2 templates模板
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/ddf3d46d-9c43-47ae-b153-bb75c1edde67)

### 3.3 静态文件
在开发过程中一般将：
+ 图片
+ CSS
+ js
都会当做静态文件处理。


#### 3.3.1 static目录
在app目录下创建static文件夹
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/e78b9e6d-4654-4bb2-9c26-19809bda5e51)

#### 3.3.2 引用静态文件
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/2dea05c8-6351-4e88-b1fd-69fdeb865871)

### 3.4 最后流程梳理
**url先写视图**
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/56389257-44da-4db6-bdbd-ac9cddef1853)

**找到视图函数，编写视图函数**
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/ee30c06d-feda-40df-9a38-c7dd39f84fe5)

**这个视图函数在templates里找**
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/8673e5cd-332f-4160-86db-73552fb179e7)

**再找静态文件static**
![image](https://github.com/Maker-IoT-one/SCT-ZhuChengWei/assets/150048050/e99ccd0b-b670-4801-a321-fdcff477b84a)


## 4 模板语法
本质上：在HTML中写一些占位符，由数据对这些占位符进行替换和处理。

## 6 数据库操作
+ MySQL数据库+pymysql
>import pymysql
># 1. 连接MySQL
>conn = pymysql.connect(host="127.0.0.1", port=3306, user='root'),
>passwd="root123",charset='utf8', db='unicom')
>cursor = conn.cursor(cursor=pymysql.cursors,DictCursor)
># 2.发送指令
>cursor.execute("insert into admin(username,password,mobile)
>values('wupeiqi', "qwe123", '15155555555')")
>conn.commit()
># 3.关闭
>cursor.close()
>conn.close()

