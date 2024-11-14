# Ex04 Places Around Me
## Date: 

## AIM
To develop a website to display details about the places around my house.

## DESIGN STEPS

### STEP 1
Create a Django admin interface.

### STEP 2
Download your city map from Google.

### STEP 3
Using ```<map>``` tag name the map.

### STEP 4
Create clickable regions in the image using ```<area>``` tag.

### STEP 5
Write HTML programs for all the regions identified.

### STEP 6
Execute the programs and publish them.

## CODE

html

```
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Image Map</title>
</head>
<style>
    img {
      max-width: 100%;
      max-height: 100vh;
      object-fit: contain;
    }
</style>
<body>
    {% load static %}
    <h1 align="center">Image Map</h1>
<img src="{%static 'image/map.jpg'%}" usemap="#image-map">

<map name="image-map">
    <area target="" alt="Bus Stand" title="Bus Stand" href="{% url 'busstand' %}" coords="607,422,791,537" shape="rect">
    <area target="" alt="Medical College" title="Medical College" href="{% url 'college' %}" coords="1031,188,1306,307" shape="rect">
    <area target="" alt="Hospital" title="Hospital" href="{% url 'hospital' %}" coords="1225,453,1415,552" shape="rect">
    <area target="" alt="School" title="School" href="{% url 'school' %}" coords="233,10,440,109" shape="rect">
    <area target="" alt="Hotel" title="Hotel" href="{% url 'hotel' %}" coords="1310,583,1502,677" shape="rect">
</map>
</body>
</html>
```

views.py

```
from django.shortcuts import render
def home(request):
    return render(request,'website.html')
def busstand(request):
    return render(request,'busstand.html')
def college(request):
    return render(request,'college.html')
def hospital(request):
    return render(request,'hospital.html')
def hotel(request):
    return render(request,'hotel.html')
def school(request):
    return render(request,'school.html')
```

urls.py

```
from django.contrib import admin
from django.urls import path
from app import views
urlpatterns = [
    path('admin/', admin.site.urls),
    path('',views.home,name='home'),
    path('busstand',views.busstand,name='busstand'),
    path('college',views.college,name='college'),
    path('hospital',views.hospital,name='hospital'),
    path('hotel',views.hotel,name='hotel'),
    path('school',views.school,name='school'),
]
```

## OUTPUT
![image](https://github.com/user-attachments/assets/951e7297-6d2d-4e9c-8a2a-48157af13b78)


![image](https://github.com/user-attachments/assets/4f866c22-bf2c-4bc7-94c7-df75871785ea)


![image](https://github.com/user-attachments/assets/dd099c06-2fa2-4519-ac4a-af44555d7e4d)


![image](https://github.com/user-attachments/assets/c18f89ca-fafb-4a32-bd2a-3032ccf3d513)


![image](https://github.com/user-attachments/assets/62f040b2-311b-46e6-a43f-dbfb6ab41672)


![image](https://github.com/user-attachments/assets/3ca3676f-dd4f-46f7-94c1-8856f4ab49a2)


## RESULT
The program for implementing image maps using HTML is executed successfully.
