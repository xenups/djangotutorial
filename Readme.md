
### if want to see how login attempts work at all
### you can see mine implemantation in this link too https://github.com/xenups/ddefender


this package need  python 3.7
using django 2.2.3

if you are not using pycharm , 
create a new venv by :

first install python3-venv : 

sudo apt install python3.7 python3-venv python3.7-venv

in your project folder:

python3.7 -m venv py37-venv
. py37-venv/bin/activate

in the next step install package from requirements by pip

pip install -r requirements.txt
 
 migrate the defender :
 python manage.py migrate defender
 
 migrate db :
 python manage.py migrate 
 
 then create a superuser by :
 python manage.py createsuperuser
 
 and in the last step runserver :
 python manage.py runserver 
 
 for cleaning the AccessAttempts table  you can use:
  python manage.py cleanup_django_defender
  
  
  you can see defender in the admin panel 
 section that shows the Access attempts	, which  can track
 your login attempts 
 in the defender section also shows the blocked ip
 
 in settings you can customize your defender as you want
  we set DEFENDER_LOGIN_FAILURE_LIMIT to 3 times
  and 
  DEFENDER_ACCESS_ATTEMPT_EXPIRATION =1  #one hours
  
  in this case without considering username if an ip failed 
  to login in 3 times it will be block
  
  
  Why not django-axes?
  django-axes is great but it puts everything in the database, 
  and this causes a bottle neck when you have a lot of data. It slows down the auth requests by as much as 200-300ms. 

 
 
