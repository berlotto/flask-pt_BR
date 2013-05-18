.. _installation:

Instalação
============

Flask depende de duas bibliotecas externas, `Werkzeug
<http://werkzeug.pocoo.org/>`_ e `Jinja2 <http://jinja.pocoo.org/2/>`_.
Werkzeug é um conjunto de ferramentas para WSGI, a interface padrão do Python para aplicações web,
em uma variedade de servidores para desenvolvimento e implantação.
Jinja2 para renderizar os templates.

Então, como você pode obter tudo no seu computador rapidamente? Há muitas maneiras de
fazer isso, o método mais rápido é o virtualenv, então vamos dar uma olhada primeiro.

Você vai precisar do Python 2.5 ou superior para começar, por isso você vai precisar
atualizar sua instalação 2.x do Python. O Python 3.x não é suportado.

.. _virtualenv:

virtualenv
----------

Virtualenv provavelmente o que você vai querer usar durante o desenvolvimento, e se você tiver
o acesso aos servidores de produção, provavelmente vai querer usá-lo lá também.

O problema que o virtualenv resolve? Se você gosta de Python tanto quanto eu,
se você quiser usá-lo para outros projetos além de Flask para aplicações web.
Mas os outros projetos que você tem, o mais provável é que você
vai trabalhar com diferentes versões do Python, ou pelo menos diferente
versões das bibliotecas. Vamos enfrentá-lo: muitas vezes bibliotecas quebrar
compatibilidade com versões anteriores, e é improvável que qualquer aplicação séria vontade
têm dependências de zero. Então, o que você faria se dois ou mais dos seus projetos têm
dependências conflitantes?

Virtualenv! Virtualenv permite várias instalações do Python,
uma para cada projeto. Na verdade, não instala cópias separadas de Python,
mas fornecem uma maneira inteligente de manter diferentes
ambientes de projeto isolado. Vamos ver como funciona virtualenv.


Se você estiver usando Mac OS X ou Linux, é provável que um dos dois seguintes
comandos irá funcionar para você::

    $ sudo easy_install virtualenv

ou melhor ainda::

    $ sudo pip install virtualenv

Uma delas, provavelmente, vai instalar o virtualenv em seu sistema. Talvez seja mesmo
em seu gerenciador de pacotes. Se você usa o Ubuntu, tente::

    $ sudo apt-get install python-virtualenv

If you are on Windows and don't have the `easy_install` command, you must
install it first.  Check the :ref:`windows-easy-install` section for more
information about how to do that.  Once you have it installed, run the same
commands as above, but without the `sudo` prefix.

Once you have virtualenv installed, just fire up a shell and create
your own environment.  I usually create a project folder and a `venv`
folder within::

    $ mkdir myproject
    $ cd myproject
    $ virtualenv venv
    New python executable in venv/bin/python
    Installing distribute............done.

Now, whenever you want to work on a project, you only have to activate the
corresponding environment.  On OS X and Linux, do the following::

    $ . venv/bin/activate

If you are a Windows user, the following command is for you::

    $ venv\scripts\activate

Either way, you should now be using your virtualenv (notice how the prompt of
your shell has changed to show the active environment).

Now you can just enter the following command to get Flask activated in your
virtualenv::

    $ pip install Flask

A few seconds later and you are good to go.


System-Wide Installation
------------------------

This is possible as well, though I do not recommend it.  Just run
`pip` with root privileges::

    $ sudo pip install Flask

(On Windows systems, run it in a command-prompt window with administrator
privileges, and leave out `sudo`.)


Living on the Edge
------------------

If you want to work with the latest version of Flask, there are two ways: you
can either let `pip` pull in the development version, or you can tell
it to operate on a git checkout.  Either way, virtualenv is recommended.

Get the git checkout in a new virtualenv and run in development mode::

    $ git clone http://github.com/mitsuhiko/flask.git
    Initialized empty Git repository in ~/dev/flask/.git/
    $ cd flask
    $ virtualenv venv --distribute
    New python executable in venv/bin/python
    Installing distribute............done.
    $ . venv/bin/activate
    $ python setup.py develop
    ...
    Finished processing dependencies for Flask

This will pull in the dependencies and activate the git head as the current
version inside the virtualenv.  Then all you have to do is run ``git pull
origin`` to update to the latest version.

To just get the development version without git, do this instead::

    $ mkdir flask
    $ cd flask
    $ virtualenv venv --distribute
    $ . venv/bin/activate
    New python executable in venv/bin/python
    Installing distribute............done.
    $ pip install Flask==dev
    ...
    Finished processing dependencies for Flask==dev

.. _windows-easy-install:

`pip` and `distribute` on Windows
-----------------------------------

On Windows, installation of `easy_install` is a little bit trickier, but still
quite easy.  The easiest way to do it is to download the
`distribute_setup.py`_ file and run it.  The easiest way to run the file is to
open your downloads folder and double-click on the file.

Next, add the `easy_install` command and other Python scripts to the
command search path, by adding your Python installation's Scripts folder
to the `PATH` environment variable.  To do that, right-click on the
"Computer" icon on the Desktop or in the Start menu, and choose "Properties".
Then click on "Advanced System settings" (in Windows XP, click on the
"Advanced" tab instead).  Then click on the "Environment variables" button.
Finally, double-click on the "Path" variable in the "System variables" section,
and add the path of your Python interpreter's Scripts folder. Be sure to
delimit it from existing values with a semicolon.  Assuming you are using
Python 2.7 on the default path, add the following value::


    ;C:\Python27\Scripts

And you are done!  To check that it worked, open the Command Prompt and execute
``easy_install``.  If you have User Account Control enabled on Windows Vista or
Windows 7, it should prompt you for administrator privileges.

Now that you have ``easy_install``, you can use it to install ``pip``::

    > easy_install pip


.. _distribute_setup.py: http://python-distribute.org/distribute_setup.py
