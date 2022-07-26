
Online Shopping Project in Django – This Django online shopping project Is built using Python, Django, and a SQLITE3 database. 
The Online Shopping will assist an online store or company in supplying its customers with an online ordering system. 
The system features two user interfaces: one for the administrator and one for the client, which is the system’s website.
The main purpose of this project is to build a platform where the buyers and sellers can connect with each other online.
The system is implemented using Python's web framework Django.



<h3>Setup</h3>
    
    1) The first thing to do is to clone the repository
    2) Create a virtual environment to install dependencies in and activate it:
    3) Open terminal to the location of folder .
    4) Then pip install -r requirements.txt to install all dependencies .
    5) Once pip has finished downloading the dependencies:
    6) Type python manage.py runserver to start the server 
    7) Navigate to  http://127.0.0.1:8000/store
       Once app started you can send request to add products in your cart .


<h3>Features</h3>
    Basic Django scaffolding (commands, templatetags, statics, media files, etc).
    onlineStore/settings.py for core settings.

<h3>INSTALLED_APPS<h3>
    Within the newly created settings.py file is a configuration called INSTALLED_APPS which is a list of Django apps within a project. 
    Django comes with six built-in apps
    INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
]

<h3>Apps</h3>  
    Current project has 'store' app . We can add an app by using the startapp command . Django comes with bydefault 6 apps. 

    INSTALLED_APPS = [
    'django.contrib.admin',
    'django.contrib.auth',
    'django.contrib.contenttypes',
    'django.contrib.sessions',
    'django.contrib.messages',
    'django.contrib.staticfiles',
    'store'
]


<h3>Routes</h3>: The URL declarations for this Django project. In url.py, the most important thing is the "urlpatterns" tuple. It’s where we define the mapping between URLs and views. 
    urls.py file include the following code
    urlpatterns = [
    path('', Index.as_view(), name='homepage'),
    path('store', store , name='store'),

    path('signup', Signup.as_view(), name='signup'),
    path('login', Login.as_view(), name='login'),
    path('logout', logout , name='logout'),
    path('cart', auth_middleware(Cart.as_view()) , name='cart'),
    path('check-out', CheckOut.as_view() , name='checkout'),
    path('orders', auth_middleware(OrderView.as_view()), name='orders'),

]


<h3>Models</h3>: Models define the structure of stored data, including the field types and possibly also their maximum size, default values, selection list options, help text for documentation, label text for forms, etc
    There are four models have been used in current project
    Category: The admin can select the product and write any features about it. All the features of that product will be visible to the users when they view a specific product.
	Customer: It saves the basic data of the customers when they register themselves
	Orders:It stores the order details about the customer, and products.
	Product: It saves the data of the product. The admin can add a new product very easily using this model.
