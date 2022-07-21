# Workshop2107

pip install django django-heroku gunicorn django-bootstrap3


django-admin startproject <name of project>

django-admin startapp <app name> # add this name in installed app in setting

python manage.py runserver

python manage makemigrations

python manage.py migrate

python manage.py createsuperuser

{ if necessary

python manage makemigrations

python manage.py migrate

}

create a model in models

---> (((
    class Meta:
        ordering = ['-created']

        def __unicode__(self):
            return u'%s'%self.title
        
    def get_absolute_url(self):
        return reverse('blog.views.post', args=[self.slug])

)))

Add {from django.urls import reverse in models}

in admin inport your model and register it like:
{
from .models import <MODEL>
admin.site.register(MODEL)
}

"there is a lorem ibsum site with this very name"

in urls import views from APP

in urlpattern
{
path(' ', views.index (you will create this index Class in views)
re_path(r'$/(.*),views.index (you will create this index(or anything) Class in views) # for redirect sites the sites within the sites? dunno(i will ask)
(((
<h1><a href="/index/{{post.slug}}">{{post.title}}</a></h1>
when you use a href in index you wil use this to redirect
)))
}

go to views {

from django.http import Httpresponse

def index(request) ...
	return Httpresponse(text(string))


def index(request) ...
	return render(request, 'index.html(create this in folder name template)', {params})
}

go for templates in (a folder in app folder)

index.html 

posts = APP.objects.all()

in views pass the posts as params {'posts' = posts}
in index.html {
{% for post in posts %}
{{post.attributes}}
(({{post.attributes|attributes like linebreaks search for this}}
))
{%endfor%}

}



add bootstrap3 in installed app

{% load bootstrap3 %}
{% load bootstrap_css %}
{% load bootstrap_javascript %}


create a folder static in APP folder then css folder then style.css

{% load static %}
<link rel='stylesheet' href="{% static 'css/style.css' %}



for blocking {
in the main page create {% block something %} some hidable text (base alternativd) {% endblock %}
in the target page first type {% extend 'mainpage.html' %} 
then put all the content in the {% block something %} put some thing {% endblock %}



}



python manage.py migrate
python manage.py makemigration
python manage.py migrate --fake blog

