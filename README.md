# Ex.05 Design a Website for Server Side Processing
## Date:

## AIM:
To design a website to find surface area of a Right Cylinder in server side.

## FORMULA:
Surface Area = 2Πrh + 2Πr<sup>2</sup>
<br>r --> Radius of Right Cylinder
<br>h --> Height of Right Cylinder

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
### Math.HTML:
```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css" rel="stylesheet" integrity="sha384-QWTKZyjpPEjISv5WaRU9OFeRpok6YctnYmDr5pNlyT2bRjXh0JMhjY6hW+ALEwIH" crossorigin="anonymous">
</head>
<body style="background-color: peachpuff;padding-top: 12%;">
    <form action="" method="post">
        {% csrf_token %}
        <div class="card mx-auto text-center" style="width: 30rem;">
            <div class="card-header bg-primary text-white">
                Surface Area of Right Cylinder
            </div>
            <div class="card-body" style="background-color: orangered;">
                Enter the radius (in 'm') :
                <p><input type="text" name="r" id="" value="{{r}}"></p>
                Enter the height (in 'm') :
                <p><input type="text" name="h" id="" value="{{h}}"></p>
                <p><input class= "btn btn-primary" type="submit" value="Calculate Area"></p>
                The area (in 'm<sup>2</sup>') :
                <p><input type="text" name="a" value="{{a}}" id="" readonly></p>
            </div>
        </div>
    </form>
    <div class="card mx-auto text-center" style="width: 30rem;
     background-color: rgb(13 110 253);color: white;">
        By - Pavithra P 212223110035
    </div>
</body>
</html>
```
### Views.py:
```
from django.shortcuts import render
def calculateArea(request):
    a=r=h=0
    if request.method=='POST':
        r=int(request.POST['r'])
        h=int(request.POST['h'])
        a=round(2*22/7*r*h + 2*22/7*r*r,2)
        print('Radius:',r,'\nHeight:',h,'\nArea:',a)
    return render(request,'math.html',{'a':a,'r':r,'h':h})
```
### Urls.py:
```
from django.contrib import admin
from django.urls import path
from ex5 import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.calculateArea)
]

```
## SERVER SIDE PROCESSING:
![image](https://github.com/23007232/MathServer/assets/139115574/37e3e8b0-0c18-45cb-b423-d03189a92028)
## HOMEPAGE:
![image](https://github.com/23007232/MathServer/assets/139115574/088a96a7-b344-4dbc-ab3a-e1011eb460f3)


## RESULT:
The program for performing server side processing is completed successfully.
