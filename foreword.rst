Prefácio
========

Leia isso antes de começar a usar o Flask. Espero que responda a algumas
questões sobre a finalidade e os objetivos do projeto, e quando você
deve ou não usá-lo.

Qual o significado de "micro" ?
-----------------------

"Micro" não significa que a sua aplicação web inteira tem que se encaixar em um único
arquivo Python, embora certamente pode. Também não quer dizer que o Flask está faltando
em termos de funcionalidade. O "micro" no microframework Flask visa manter o
núcleo simples, mas extensível. Flask não vai tomar muitas decisões para você, como
o banco de dados para usar. Essas decisões que ele faz, como o que
motor de templates usar, são fáceis de mudar. Todo o resto é com você, então
o Flask que pode ser tudo que você precisa e nada que você não faz.

Por padrão, Flask não inclui uma camada de abstração de banco de dados, uma validação de form
ou qualquer outra coisa que já exista em bibliotecas diferentes que pode
lidar com isso. Em vez disso, Flask suporta extensões para adicionar essa funcionalidade a
sua aplicação como se fosse implantado no Flask. Há várias extensões
para proporcionar a integração de banco de dados, validação de formulário, manipulação de upload, vários tecnologias
de autenticação abertas, e muito mais. Flask pode ser "micro", mas está pronto para
uso na produção para uma variedade de necessidades.

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

Como sua base de código cresce, você é livre para tomar as decisões de design apropriado
para seu projeto. Flask irá continuar a proporcionar uma camada de cola muito simples
o melhor que Python tem a oferecer. Você pode implementar padrões avançados em
SQLAlchemy ou outra ferramenta de banco de dados, introduzir a persistência de dados não-relacional
conforme o caso, e tirar proveito de ferramentas de framework-agnostic construídos para WSGI,
a interface web para Python.

Flask includes many hooks to customize its behavior. Should you need more
customization, the Flask class is built for subclassing. If you are interested
in that, check out the :ref:`becomingbig` chapter.  If you are curious about
the Flask design principles, head over to the section about :ref:`design`.

Continue to :ref:`installation`, the :ref:`quickstart`, or the
:ref:`advanced_foreword`.
