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
——manage.py
——mysite
————_init_.py
————asgi.py
————settings.py
————urls.py
————wsgi.py


### 创建APP 
>项目
>- app, 用户管理[表结构, 函数，HTML模板，CSS]
注意：开发比较简洁，用不到多apP，一般情况下，项目下创建1个app即可。

