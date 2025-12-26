# Ex.04 Design a Website for Server Side Processing
## Date:26/12/2025

## AIM:
To create a web page to calculate vehicle mileage and fuel efficiency using server-side scripts.

## FORMULA:
M = D / F
<br> M --> Mileage (in km/l)
<br> D --> Distance Travelled (in km)
<br> F --> Fuel Consumed (in l)

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

## PROGRAM:
```
views.py

from django.shortcuts import render
def miles(request):
    km = int(request.POST.get('DISTANCE', 0))
    l = int(request.POST.get('LITERS', 0))
    miles = km / l if request.method == 'POST' and l != 0 else 0
    print("kilometers =", km)
    print("liters =", l)
    print("Mileage =", miles)
    return render(request, 'mathapp/math.html', {'km': km, 'l': l, 'miles':miles})


urls.py

from django.urls import path
from mathapp import views

urlpatterns = [
    path('', views.miles, name='miles'),
]


math.html

<html>
<head>
    <title>Mileage Calacutor</title>
    <title>DINESH KARTHIKEYAN V  (25012548)</title>
    <style>
       body
       {
        background-color: rgb(54, 27, 100);
       }
       .id0
       {
        text-align: center;
        color:rgb(78, 134, 95);
       }
       .box
       {
        text-align: center;
        width:60%;
        background-color: rgb(189, 56, 56);
        border: solid 5px rgb(21, 212, 126);
        padding:10px;
        margin:60px auto;
       }
       .result
       {
        font-weight: bolder;
       }
    </style>
</head>
<body>
    <h1 class="id0"><u>Calculate Mileage </u></h1>
    <div class="box">
        <h2><u>Mileage Calculator</u></h2>
        <h3>DINESH KARTHIKEYAN V  (25012548)</h3>


        <form method="post">

            {% csrf_token %}
           
            <lable>DISTANCE</lable>
            <br>
            <input type="number" name="DISTANCE">km
            <br>

            <lable>LITERS</lable>
            <br>
            <input type="number" name="LITERS">l
            <br>

            <button type="submit">CALCULATE</button>
            <br>

            <lable>Mileage</lable>
            <br>
            <br>
            <input class="result" type="number" name="Mileage" value={{miles}}>km/l
            </form>
    </div>        
</body>
    
</html>


```

## OUTPUT - SERVER SIDE:

![alt text](<Screenshot (35).png>)

## OUTPUT - WEBPAGE:


![alt text](<Screenshot (34).png>)
## RESULT:
The a web page to calculate vehicle mileage and fuel efficiency using server-side scripts is created successfully.
