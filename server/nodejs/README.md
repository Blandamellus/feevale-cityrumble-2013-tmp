# Instalação do Node.js e MongoDB

Primeiramente faça download e instale [Node.js](http://nodejs.org/) e [MongoDB](http://www.mongodb.org/).

Verique se os comandos `node` (ou `nodejs` se instalado pelos pacotes do Debian), `npm` e `mongo` estão disponíveis.

* Em ambientes windows, pode ser necessário adicionar as pastas dos executáveis à variável de ambiente `$PATH` 
    (algo como _Propriedades do meu computador_ -> _Configurações avançadas_ -> _Variáveis de ambiente_).
* Em ambientes GNU/Linux e Mac OSX pode-se verificar com o comando `whereis`

        $ whereis node
        node: /usr/local/bin/node
        $ whereis npm
        npm: /usr/local/bin/npm
        $ whereis mongo
        mongo: /usr/bin/mongo /usr/bin/X11/mongo /usr/include/mongo /usr/share/man/man1/mongo.1.gz

# Scripts Node.js

Para instalar os módulos do Node.js que são dependências dos scripts execute:

    npm install

Além das dependências instaladas pelo `npm`, existe uma dependência chamada `foursquarevenues`, que
faz parte de outro repositório no GitHub, devendo ser baixada com os comandos a seguir:

    git submodule init
    git submodule update

Para inicializar a base de dados (MongoDB) execute:

    node init_db.js
    
Note que, até o momento, já há verificação dos registros na base, 
sendo assim, se executaro o script mais de uma vez, os registros 
serão duplicados.

# IBM Websphere Workarea

Este diretório também deve funcionar como workarea para o servidor IBM Websphere (o que roda os 
Adapters do Worklight) e é configurado no aquivo `web.xml` da pasta `websphere/` (veja o README 
da mesma para detalhes).

Basicamente, isto é necessário apenas pelas  dependências do Node.js para os Adapters,
que são listadas no arquivo `packages.json` instaladas com o comando `npm install`.

Se preferir, você pode criar o _workarea_ em qualquer diretório acessível e instalar os
módulos do node.js necessários.