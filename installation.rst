.. _installation:

Instalação
============

Flask depende de duas bibliotecas externas, `Werkzeug
<http://werkzeug.pocoo.org/>`_ e `Jinja2 <http://jinja.pocoo.org/2/>`_.
Werkzeug é um conjunto de ferramentas para WSGI, a interface padrão do Python entre aplicações web e uma variedade de servidores para desenvolvimento e implantação.
Jinja2 é um renderizador de templates.

Então, como você pode obter tudo no seu computador rapidamente? Há muitas maneiras de
fazer isso, o método mais rápido é o virtualenv, então vamos dar uma olhada primeiro.

Você vai precisar do Python 2.5 ou superior para começar, portanto confira se o python instalado é um versão 2.x atualizada. Flask ainda não suporta Python 3.x.

.. _virtualenv:

virtualenv
----------

Virtualenv é provavelmente o que você vai querer usar durante o desenvolvimento, e se você tiver
o acesso aos servidores de produção, provavelmente vai querer usá-lo também.

Que problema que o virtualenv resolve? Se você gosta de Python tanto quanto eu, há chances de querer usá-lo para outros projetos além de Flask.
Quanto mais projetos você tem, maiores são as chances de você usar versões de diferentes do python, ou pelo menos diferentes
versões das bibliotecas python. Muitas vezes bibliotecas quebram por falta de
compatibilidade com versões anteriores, e é improvável que qualquer aplicação séria não tenha nenhuma dependência. Então, o que você faria se dois ou mais projetos tivessem dependências em conflito?

Virtualenv! Virtualenv permite várias instalações do Python,
uma para cada projeto. Na verdade, ele não instala cópias separadas de Python,
mas fornecem uma maneira inteligente de manter diferentes
ambientes de projeto isolado. Vamos ver como funciona.


Se você estiver usando Mac OS X ou Linux, é provável que um dos dois seguintes
comandos irá funcionar para você::

    $ sudo easy_install virtualenv

ou melhor ainda::

    $ sudo pip install virtualenv

Uma delas, provavelmente, vai instalar o virtualenv em seu sistema. Talvez ele já esteja em seu gerenciador de pacotes. Se você usa o Ubuntu, tente::

    $ sudo apt-get install python-virtualenv

Caso você use Windows e não tem o comando `easy_install`, instale-o. Confire a seção :ref:`windows-easy-install` para mais informações. Uma vez tudo pronto, execute algum dos comandos acima, porém sem o prefixo `sudo`.

Depois de ter instalado o virtualenv, basta executar o shell e criar
seu próprio ambiente. Eu costumo criar uma pasta de projeto e uma pasta `venv`
dentro::

    $ mkdir myproject
    $ cd myproject
    $ virtualenv venv
    New python executable in venv/bin/python
    Installing distribute............done.

Agora, sempre que você quiser trabalhar em um projeto, você só tem que ativar o
ambiente correspondente. No OS X e Linux, faça o seguinte::

    $ . venv/bin/activate

Se você é um usuário Windows, execute o comando a abaixo::

    $ venv\scripts\activate

De qualquer forma, agora você deve estar usando seu virtualenv (note como o prompt de
seu shell mudou para mostrar o ambiente ativo).

Agora você pode digitar o seguinte comando para instalar o Flask em seu
virtualenv::

    $ pip install Flask

Poucos segundos depois, e ele estará instalado.


Instalação no Sistema
------------------------

Isto é possível, embora eu não recomendo. Basta executar
`pip` com privilégios de root::

    $ sudo pip install Flask

(On Windows systems, run it in a command-prompt window with administrator
privileges, and leave out `sudo`.)

(Em sistemas Windows, execute no prompt de comando com o com privilégios de administrador,
sem usar o comando `sudo`).


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
