# Ex.05 Design a Website for Server Side Processing
## Date: 26-04-2025

NAME : YASHWANTH K

REG NO : 212224040369

## AIM:
 To design a website to calculate the power of a lamp filament in an incandescent bulb in the server side. 


## FORMULA:
P = I<sup>2</sup>R
<br> P --> Power (in watts)
<br> I --> Intensity
<br> R --> Resistance

## DESIGN STEPS:

### Step 1:
Clone the repository from GitHub.

### Step 2:
Create Django Admin project.

### Step 3:
Create a New App under the Django Admin project.

### Step 4:
Create python programs for views and urls to perform server side processing.

### Step 5:
Create a HTML file to implement form based input and output.

### Step 6:
Publish the website in the given URL.

## PROGRAM :

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="utf-8">
    <meta http-equiv="X-UA-Compatible" content="IE=edge">
    <title>Surface Area of Right Cylinder - HARIHARAN A (212223110013)</title>
    <meta name="viewport" content="width=device-width, initial-scale=1">
    <style>
        body {
            background-color: rgb(11, 210, 228);
            font-family: Arial, sans-serif;
        }
        .edge {
            width: 100%;
            max-width: 1440px;
            margin: 0 auto;
            padding-top: 100px;
            display: flex;
            justify-content: center;
            align-items: center;
            flex-direction: column;
        }
        .box {
            display: block;
            border: thick dashed rgb(8, 6, 17);
            width: 500px;
            min-height: 300px;
            padding: 20px;
            background-color: rgb(209, 20, 42);
            box-shadow: 0px 4px 8px rgba(0, 0, 0, 0.2);
            border-radius: 10px;
        }
        .formelt {
            color: rgb(1, 18, 17);
            text-align: center;
            margin: 15px 0;
        }
        h1 {
            color: rgb(17, 232, 239);
            text-align: center;
            margin-bottom: 20px;
        }
        input[type="text"] {
            padding: 8px;
            margin-top: 5px;
            margin-bottom: 5px;
            width: 80%;
            border: none;
            border-radius: 5px;
        }
        input[type="submit"] {
            padding: 10px 20px;
            background-color: rgb(17, 232, 239);
            border: none;
            border-radius: 5px;
            cursor: pointer;
            font-weight: bold;
            margin-top: 10px;
        }
        input[type="submit"]:hover {
            background-color: rgb(12, 200, 210);
        }
    </style>
</head>
<body>
    <div class="edge">
        <div class="box">
            <h1>Surface Area of Right Cylinder</h1>
            <p style="text-align:center; font-weight:bold;">HARIHARAN A (212223110013)</p>
            <form method="POST">
                {% csrf_token %}
                <div class="formelt">
                    Radius: <br/>
                    <input type="text" name="radius" value="{{ r }}"> (in m)
                </div>
                <div class="formelt">
                    Height: <br/>
                    <input type="text" name="height" value="{{ h }}"> (in m)
                </div>
                <div class="formelt">
                    <input type="submit" value="Calculate">
                </div>
                <div class="formelt">
                    Area: <br/>
                    <input type="text" name="area" value="{{ area }}"> m<sup>2</sup>
                </div>
            </form>
        </div>
    </div>
</body>
</html>

```
```
from django.shortcuts import render
def surfacearea(request):
    context={}
    context['area'] = "0"
    context['r'] = "0"
    context['h'] = "0"
    if request.method == 'POST':
        print("POST method is used")
        r = request.POST.get('radius','0')
        h = request.POST.get('height','0')
        print('request=',request)
        print('radius=',r)
        print('height=',h)
        area = 2 * 3.14 * int(r) * int(h) + 2 * 3.14 * int(r) * int(r)
        context['area'] = area
        context['r'] = r
        context['h'] = h
        print('Area=',area)
    return render(request,'mathapp/ nameofyourhtml .html',context)
```
```
from django.contrib import admin
from django.urls import path
from mathapp import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('surfaceareaofcylinder/',views.surfacearea,name="surfaceareaofcylinder"),
    path('',views.surfacearea,name="surfaceareaofcylinderroot")
]
```

## SERVER SIDE PROCESSING:

![image](https://github.com/user-attachments/assets/157f28af-550c-4bd3-ab55-63f55f6696da)

## HOMEPAGE:

![image](https://github.com/user-attachments/assets/1c7fd0c6-c14f-45db-82d2-18987140e2b4)

## RESULT:
The program for performing server side processing is completed successfully.
