Prefácio
========

Leia isso antes de começar a usar o Flask. Espero que responda a algumas
questões sobre a finalidade e os objetivos do projeto, e quando você
deve ou não usá-lo.

Qual o significado de "micro" ?
-----------------------

“Micro” does not mean that your whole web application has to fit into a single
Python file, although it certainly can. Nor does it mean that Flask is lacking
in functionality. The "micro" in microframework means Flask aims to keep the
core simple but extensible. Flask won't make many decisions for you, such as
what database to use. Those decisions that it does make, such as what
templating engine to use, are easy to change.  Everything else is up to you, so
that Flask can be everything you need and nothing you don't.

Por padrão, Flask não inclui uma camada de abstração de banco de dados, uma validação de form
ou qualquer outra coisa que já exista em bibliotecas diferentes que podem
lidar com isso. Em vez disso, Flask suporta extensões para adicionar essa funcionalidade para
sua aplicação como se fosse implantado no Flask. Há várias extensões
para proporcionar a integração de banco de dados, validação de formulário, manipulação de upload, vários tecnologias
de autenticação abertas, e mais. Flask pode ser "micro", mas está pronto para
uso na produção e uma variedade de necessidades.

Configuração e Convenções
-----------------------------

Flask tem muitos valores de configuração, com padrões sensíveis, e algumas
convenções quando começar. Para convenções de templates e arquivos estáticos são
armazenados em subdiretórios dentro da aplicação na árvore fonte do Python, com o
nomes `templates` e `static` respectivamente. Embora isso possa ser mudado por você,
geralmente não precisa, especialmente quando começar.

Crescendo com Flask
------------------

Depois de ter o Flask instalado e funcionando, você vai encontrar uma variedade de extensões
disponíveis na comunidade para integrar no seu projecto em produção. The Flask
core team reviews extensions and ensures approved extensions do not break with
future releases.

As your codebase grows, you are free to make the design decisions appropriate
for your project.  Flask will continue to provide a very simple glue layer to
the best that Python has to offer.  You can implement advanced patterns in
SQLAlchemy or another database tool, introduce non-relational data persistence
as appropriate, and take advantage of framework-agnostic tools built for WSGI,
the Python web interface.

Flask includes many hooks to customize its behavior. Should you need more
customization, the Flask class is built for subclassing. If you are interested
in that, check out the :ref:`becomingbig` chapter.  If you are curious about
the Flask design principles, head over to the section about :ref:`design`.

Continue to :ref:`installation`, the :ref:`quickstart`, or the
:ref:`advanced_foreword`.
