# Django Blog Mini-Project

A simple blog app written using Django.

Notes:
****************************************
§1. To set up the workspace for Django v1.11 at Cloud9
************************************************
1. create C9 workspace django-authentication

2. 
sudo pip3 install django==1.11

3. create a project folder at root
django-admin startproject django_auth .

4.
django-admin startapp name_of_app

5. add the app into the app list of setting.py

6. add alias in bash_aliases at the favourite view
alias run=“python3 manage.py runserver $IP:$PORT”

7. reinitiate bash or 
. ~/.bash_aliases

8. 
python3 manage.py migrate

9. update allowed hosts
/setting.py
ALLOWED_HOSTS = [os.environ.get(‘C9_HOSTNAME’)]

10.
run

11. generate a requirement.txt file
pip3 freeze —local > requirements.txt

***********************************
§2. To set up Git
***********************************
1.
git init
echo -e "*.sqlite3\n*.pyc\n.~c9__pyache__/"> .gitignore
git status
git add .
git commit -m "Created a simple blog app with Django"
2. create a new depo at github
3. 
git remote add origin https://github.com/rayzhu68/Django_blog.git
git push -u origin master

************************************
§3. Travis for testing
************************************
1. get to the website of travis ci for testing
2. login
3. click the repo
4. click buil/unknow button>choose markdown>copy the link and paste at the end of README.md
5. create a file: .travis.yml

language: python
python:
    - "3.4"
instal: "pip3 install -r requirements.txt"
script:
- SECRET_KEY="whatever" ./manage.py test

6.
git status
git add README.md .travis.yml
git commit -m "Synced with travis ci and added .travis.yml"
git push



[![Build Status](https://travis-ci.org/rayzhu68/Django_blog.svg?branch=master)](https://travis-ci.org/rayzhu68/Django_blog)
