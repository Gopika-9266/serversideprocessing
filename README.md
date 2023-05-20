# Design a Website for Server Side Processing

## AIM:
To design a website to perform mathematical calculations in server side.

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub


### Step 2:
Create Django Admin project.


### Step 3:
Create a New App.


### Step 4:
Create python programs for views and urls.


### Step 5:
Create a HTML file of forms.


### Step 6:

Publish the website in the given URL.



## PROGRAM :
```
Developed By: Gopika R
Register Number:212222240031

Math.html:

<html>
<head>
<meta charset='utf-8'>
<meta http-equiv='X-UA-Compatible' content='IE=edge'>
<title>Area of Triangle</title>
<meta name='viewport' content='width=device-width,initial-scales=1'>
<style>
body {
background-color:cyan
}
.edge {
width: 1080px;
margin-left: auto;
margin-right: auto;
padding-top: 200px;
padding-left: 300px;
}
.box {
display:block;
border: Thick dashed lime;
width: 600px;
min-height: 300px;
font-size: 20px;
background-color:purple;
}
.formelt{
color:red;
text-align: center;
margin-top: 10px;
margin-bottom: 10px;
}
h1{
color:greenyellow;
text-align: center;
padding-top: 30px;
}
</style>
</head>
<body>
<div class="edge">
<div class="box">
<h1>Area of a Triangle</h1>
<form method="POST">
{% csrf_token %}
<div class="formelt">
Breadth : <input type="text" name="breadth" value="{{b}}"></input>(in m)<br/>
<div clss="formelt">
Height : <input type="text" name="height" value="{{h}}"></input>(in m)<br/></div>
<div class="formelt">
<input type="submit" value="calculate"></input><br/>
</div>
<div class="formelt">
Area :  <input type="text" name="area" value="{{area}}"></input>m<sup>2</sup><br/>
</div>
</form>
</div>
</div>
</body>
</html>
```

```
views.py:

from django.shortcuts import render
def triarea(request):
    context={}
    context['area']="0"
    context['b']="0"
    context['h']="0"
    if request.method == 'POST':
        print("POST method is used")
        b = request.POST.get('breadth','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('Breadth=',b)
        print('height=',h)
        area = (int(b) * int(h))/2
        context['area'] = area
        context['b'] = b
        context['h'] = h
        print('Area=',area)
    return render(request,'myapp/math.html',context) 
```

```

urls.py:

from django.contrib import admin
from django.urls import path
from myapp import views


urlpatterns = [
    path('admin/', admin.site.urls),
    path('areaoftriangle/',views.triarea,name="areaoftriangle"),
    path('',views.triarea,name="areaoftriangleroot")
]
```



## OUTPUT:

![out](https://user-images.githubusercontent.com/122762773/235484728-9e019607-9af3-4c19-b1d8-921401f42f8e.png)



### HOME PAGE:

![Screenshot (151)](https://github.com/Gopika-9266/serversideprocessing/assets/122762773/a3eb1936-9a3a-4255-915d-5e43f47e18f8)

### HTML VALIDATOR:

![Screenshot (152)](https://github.com/Gopika-9266/serversideprocessing/assets/122762773/9fb50547-a081-4c08-bfb5-6edb34010679)


## Result:

The program for implementing server side processing is completed successfully.
