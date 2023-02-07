## 创建一个项目

创建一个名为mysite的项目，命令行输入下面命令

```python
django-admin startproject mysite
```



## 启动服务器

```python
py manage.py runserver 8080
```

输出如下表示启动成功，如果没指定端口，则默认监听8000端口

```
Performing system checks...

System check identified no issues (0 silenced).

You have unapplied migrations; your app may not work properly until they are applied.
Run 'python manage.py migrate' to apply them.

一月 31, 2023 - 15:50:53
Django version 4.1, using settings 'mysite.settings'
Starting development server at http://127.0.0.1:8080/
Quit the server with CONTROL-C.
```



## 创建一个应用

创建一个polls目录

```python
py manage.py startapp polls
```

