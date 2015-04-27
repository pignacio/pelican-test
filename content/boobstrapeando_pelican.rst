Boobstrapeando pelican
######################

:date: 2015-04-26 18:46
:modified: 2015-04-26 18:46
:authors: Ignacio Rossi

Antes que nada hay que instalar pelican, pero eso es mejor verlo en persona,
debería ser un toque.

Primero, haces un repo en github_. Si lo vas a hostear en las github pages, la
url va a terminar siendo ``http://jpalandri.github.io/<repo>``.

Te clonas el repo, y haces ``cd`` adentro:

.. code:: shell

  verne :: ~/misc/juli % git clone git@github.com:pignacio/pelican-test
  Cloning into 'pelican-test'...
  remote: Counting objects: 3, done.
  remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0
  Receiving objects: 100% (3/3), done.
  Checking connectivity... done.
  verne :: ~/misc/juli % cd pelican-test

Ahi corrés ``pelican-quickstart`` y contestás las preguntas correspondientes:

.. code:: shell

  verne :: misc/juli/pelican-test ‹master› % pelican-quickstart
  Welcome to pelican-quickstart v3.5.0.

  This script will help you create a new Pelican-based website.

  Please answer the following questions so this script can generate the files
  needed by Pelican.


  > Where do you want to create your new web site? [.]
  > What will be the title of this web site? Testeando pelican
  > Who will be the author of this web site? Nach
  > What will be the default language of this web site? [en]
  > Do you want to specify a URL prefix? e.g., http://example.com   (Y/n) y
  > What is your URL prefix? (see above example; no trailing slash) http://pignacio.github.io/pelican-test
  > Do you want to enable article pagination? (Y/n)
  > How many articles per page do you want? [10]
  > Do you want to generate a Fabfile/Makefile to automate generation and publishing? (Y/n)
  > Do you want an auto-reload & simpleHTTP script to assist with theme and site development? (Y/n)
  > Do you want to upload your website using FTP? (y/N)
  > Do you want to upload your website using SSH? (y/N)
  > Do you want to upload your website using Dropbox? (y/N)
  > Do you want to upload your website using S3? (y/N)
  > Do you want to upload your website using Rackspace Cloud Files? (y/N)
  > Do you want to upload your website using GitHub Pages? (y/N) y
  > Is this your personal page (username.github.io)? (y/N) n
  Done. Your new project is available at /home/ignacio/misc/juli/pelican-test

Agregá un ``.gitignore`` con lo que sigue, para no comitear los htmls
generados y otras cosas que no van:

.. code::

  # Pelican directories
  cache
  output

  # PID files

  *.pid

  # Python compiled files

  *.py[co]
  __pycache__


Commiteamos y pusheamos eso a github:

.. code:: shell

  verne :: misc/juli/pelican-test ‹master*› % git add .
  verne :: misc/juli/pelican-test ‹master*› % git commit -m "Initial commit"
  [master 059e0e5] Initial commit
   5 files changed, 345 insertions(+)
   create mode 100644 Makefile
   create mode 100755 develop_server.sh
   create mode 100644 fabfile.py
   create mode 100644 pelicanconf.py
   create mode 100644 publishconf.py
  verne :: misc/juli/pelican-test ‹master› % git push
  Counting objects: 8, done.
  Delta compression using up to 6 threads.
  Compressing objects: 100% (7/7), done.
  Writing objects: 100% (7/7), 4.19 KiB | 0 bytes/s, done.
  Total 7 (delta 0), reused 0 (delta 0)
  To git@github.com:pignacio/pelican-test
     1f5c59c..059e0e5  master -> master

Para confirar que todo está funcionando, podes hacer un push del sitio vacío a
las github pages con:

.. code::

  verne :: misc/juli/pelican-test ‹master› % make github


.. _github: http://www.github.com
