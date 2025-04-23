#  Cargo Management System Project in Django with Source Code

The **Cargo Management System in Django** is built using **Python**, **Django**, and a **MySQL database**.

**Cargo System** is an application that can assist with cargo transportation by ship, airline, or locally.

This program can be used by a corporation to keep track of the freight quantity in its warehouse.

>[!NOTE]
> To start creating a **Cargo Management System System Project in Python Django**, makes sure that you have PyCharm Professional IDE Installed in your computer.

## User Features

* **Register Page**

The page where new user of cargo system created their login credentials for the website.

* **Login Page**

The page where the system user enters their system credentials in order to gain access to the system’s company side.

* **Add Shipment**

This is the page where the user can add update, view order and delete shipment information.

* **View Profile**

This is the page where the company can update their profile.

## How to Create a Cargo Management System in Django?

Here are the steps on **how to create a Cargo Management System in Django** with Source Code.

1. **Open file**.

First, open “pycharm professional” after that click “file” and click “new project”.

2. **Choose Django**.

Next, after click “new project“, choose “Django” and click.

3. **Select file location**.

Then, select a file location wherever you want.

4. **Create application name**.

After that, name your application.

5. **Click create**.

Lastly, finish creating project by clicking “create” button.

6. **Start Coding**.

Finally, we will now start adding functionality to our Django Framework by adding some functional codes.

## Functionality and Codes

* **Create template for the add user form**

In this section, we will learn on how create a templates for the add user form. 

To start with, add the following code in your adduser.html under the folder of users/templates/users.

```
{% extends 'home/header.html' %}
{% load staticfiles %}

{% block navbar %}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="description" content="DeuZon Cargo Website">
  <meta name="author" content="DeuZon Corporation">

  <title>Cargo System</title>
  <link type = "text/css" rel="stylesheet" href="{% static "css/bootstrap.css" %}" />
  <link rel="stylesheet" href="{% static "css/navbar-fixed-top.css" %}" type = "text/css"/>
  <script type = "text/javascript"  src="{% static "js/jquery.js" %}" ></script>
  <script type="text/javascript" src="{% static "js/bootstrap.js" %}"></script>
</head>
<body>


<!-- Company Select Dropdown -->
   <div id="reg" class="row" >  
        <div style="margin: auto; width: 600px;" >

            <!-- Company Cargo Track number submit -->

            <label>Registration<br><br></label>
            
                <form  action="/users/adduser" method="POST" class="form-inline">
                     {% csrf_token %}
                    
                    <div class="form-group col-md-12">
                        <label class="control-label col-md-4">Name : </label>
                        <input class="col-md-8" type="text"  name="uname" placeholder="Name"/><br><br>
                    </div>    
                    <div class="form-group col-md-12">
                        <label class="control-label col-md-4">Surname : </label>
                        <input class="col-md-8" type="text"  name="sname" placeholder="Surname"/><br><br>
                    </div>
                    <div class="form-group col-md-12">
                        <label class="control-label col-md-4">Email Address : </label>
                        <input class="col-md-8" type="text"  name="mail" placeholder="Mail Address"/><br><br>
                    </div>
                    <div class="form-group col-md-12">
                        <label class="control-label col-md-4">Telephone no  : </label>
                        <input class="col-md-8" type="text" name="telno" placeholder="Telephone number"/><br><br>
                    </div>
                    <div class="form-group col-md-12">
                        <label class="control-label col-md-4">Password  : </label>
                        <input class="col-md-8" type="password"  name="passwd" placeholder="Password"/><br><br>
                    </div>
                   
                  
                <button class="submit-button btn btn-success pull-right" >Submit</button>
                
  {% if messagetype == 1 %}             
<div class="alert alert-success fade in">
<strong>Success!</strong>
   {{ message }}
</div>
  {% elif messagetype == 2 %}   
  <div class="alert alert-danger fae in">
  <strong>Invalid!</strong>
   {{ message }}
</div>
  {% endif %}
                </form>
            
           
        </div> 
   </div>  

</body>
</html>
<style>
#reg {
  width: 100%;
  margin: 100px auto;
}
</style>

    {% endblock navbar %}
```


* **Create template for the new shipment form**

In this section, we will learn on how create a templates for the new shipment form.

To start with, add the following code in your new_shipment.html under the folder of cargo_app/templates/shipments.

```
{% extends 'home/header.html' %}
{% load staticfiles %}

{% block navbar %}
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8">
  <meta name="description" content="DeuZon Cargo Website">
  <meta name="author" content="DeuZon Corporation">

  <title>Cargo System</title>
  <link type = "text/css" rel="stylesheet" href="{% static "css/bootstrap.css" %}" />
  <link rel="stylesheet" href="{% static "css/navbar-fixed-top.css" %}" type = "text/css"/>
  <script type = "text/javascript"  src="{% static "js/jquery.js" %}" ></script>
  <script type="text/javascript" src="{% static "js/bootstrap.js" %}"></script>
</head>
<body>


<!-- Company Select Dropdown -->
   <div id="reg" class="row" >  
        <div style="margin: auto; width: 600px;" >

            <!-- Company Cargo Track number submit -->

            <label>New Shipment<br><br></label>
            
                <form  action="/shipments/new" method="POST" class="form-inline" id="shipmentForm">
                     {% csrf_token %}

                    <div class="form-group col-md-12">
                        <br><label class="control-label col-md-4">Source Address : </label>
                        <textarea class="form-control col-md-8" form="shipmentForm" name="source" rows="3" placeholder="Please enter source address."></textarea>
                    </div>    
                    <div class="form-group col-md-12">
                        <br><label class="control-label col-md-4">Destination Address : </label>
                        <textarea class="form-control col-md-8" form="shipmentForm" name="dest" rows="3" placeholder="Please enter destination address."></textarea>
                    </div>   
                    <div class="form-group col-md-12">
                        <br><label class="control-label col-md-4">Quantity : </label>
                        <input class="col-md-8" type="number"  name="qnt" placeholder="Quantity" value="1" /><br><br>
                    </div>

                  <button class="submit-button btn btn-success pull-right">Submit</button>
                </form>
            
           
        </div> 
   </div>  

</body>
</html>
<style>
#reg {
  width: 100%;
  margin: 100px auto;
}
</style>

    {% endblock navbar %}
```

### 📌Here's the full documentation for the [Cargo Management System Project in Django](https://itsourcecode.com/free-projects/python-projects/cargo-management-system-project-in-django-with-source-code/)
