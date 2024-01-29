============
django-dotnetid
============

django-dotnetid is a Django app extending django-allauth.
It implements an OpenID connect provider able to map extra_info from the id_token
into Django User model. It is also capable of attributing groups automatically.

You need to install django-allauth to be able to use this extension.

Quick start
-----------

1. Install this package along with django-allauth in your project:

    pip install django-allauth
    pip install git+https://github.com/sitn/django-dotnetid.git

2. Add "dotnetidprovider" to your INSTALLED_APPS setting like this::

    INSTALLED_APPS = [
        ...,
        "django_dotnetid",
        "allauth",
        "allauth.account",
        "allauth.socialaccount",
        "allauth.socialaccount.providers.openid_connect",
    ]

3. Include the dotnetidprovider URLconf in your project urls.py like this::

    path('accounts/', include('allauth.urls')),

4. Run ``python manage.py migrate`` to create the models.

5. Start the development server.

6. Visit the ``/``.