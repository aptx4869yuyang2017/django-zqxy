# 这个仓库是 自强学院 的Django 学习笔记 和代码仓库

## 在网页上做加减法
* 一 新建一个项目(project), 名称为 mysite `django-admin startproject mysite`
* 二 新建一个应用(app), 名称叫 calc `python manage.py startapp calc # calc 是一个app的名称`
* 三 在网页上做加减法
    * 采用 /add/?a=4&b=5 这样GET方法进行
    * 采用 /add/3/4/ 这样的网址的方式

```from django.shortcuts import render
from django.http import HttpResponse
 
def add(request):
    a = request.GET['a']
    b = request.GET['b']
    c = int(a)+int(b)
    return HttpResponse(str(c))
```



```
def add2(request, a, b):
    c = int(a) + int(b)
    return HttpResponse(str(c))
    ```

`url(r'^add/(\d+)/(\d+)/$', calc_views.add2, name='add2'),`