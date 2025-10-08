# Gitignore

Ao trabalhar em um repositório Git, muitas vezes você terá arquivos e diretórios que não deseja commitar, para que não fiquem disponíveis para outras pessoas que usam o repositório.

Em alguns casos, você pode não querer commitar alguns arquivos no Git por motivos de segurança.

Por exemplo, se você tem um arquivo de configuração que armazena todas as credenciais do banco de dados e outras informações sensíveis, nunca deve adicioná-lo ao Git e enviá-lo para o GitHub, pois outras pessoas poderão acessar essas informações confidenciais.

Outro caso em que você pode não querer commitar um arquivo ou diretório é quando esses arquivos são gerados automaticamente e não contêm código-fonte, para não poluir seu repositório. Também faz sentido não commitar arquivos que contêm informações de ambiente, para que outras pessoas possam usar seu código com seus próprios arquivos de ambiente.

Para evitar que esses tipos de arquivos sejam commitados, você pode criar um arquivo `gitignore` que inclui uma lista de todos os arquivos e diretórios que devem ser excluídos do seu repositório Git. Neste capítulo, você aprenderá como fazer isso!

### Ignorando um arquivo específico

Veja o exemplo a seguir: se você tem um projeto em `PHP` e um arquivo chamado `config.php`, que armazena os detalhes da conexão com o banco de dados, como usuário, senha, host, etc.

Para excluir esse arquivo do seu projeto git, você pode criar um arquivo chamado `.gitignore` dentro do diretório do seu projeto:

```bash
touch .gitignore
```

Dentro desse arquivo, basta adicionar o nome do arquivo que deseja ignorar, então o conteúdo do `.gitignore` ficaria assim:

```
config.php
```

Assim, da próxima vez que você rodar `git add .` e depois `git commit` e `git push`, o arquivo `config.php` será ignorado e não será adicionado nem enviado para o seu repositório no Github.

Dessa forma, você mantém suas credenciais do banco de dados seguras!

### Ignorando um diretório inteiro

Em alguns casos, você pode querer ignorar uma pasta inteira. Por exemplo, se você tem uma pasta enorme chamada `node_modules`, não há necessidade de adicioná-la e commitá-la ao seu projeto Git, pois esse diretório é gerado automaticamente sempre que você executa `npm install`.

O mesmo vale para a pasta `vendor` no Laravel. Você não deve adicionar a pasta `vendor` ao seu projeto Git, pois todo o conteúdo dessa pasta é gerado automaticamente quando você executa `composer install`.

Para ignorar as pastas `vendor` e `node_modules`, basta adicioná-las ao seu arquivo `.gitignore`:

```
# Pastas ignoradas
/vendor/
node_modules/
```

### Ignorando um diretório inteiro, exceto um arquivo específico

Às vezes, você quer ignorar um diretório, exceto um ou alguns arquivos dentro dele. Pode ser que o diretório seja necessário para sua aplicação rodar, mas os arquivos criados não devem ser enviados ao repositório remoto, ou talvez você queira ter um arquivo `README.md` dentro do diretório por algum motivo. Para isso, seu arquivo `.gitignore` deve ficar assim:

```
data/*
!data/README.md
```

A primeira linha indica que você quer ignorar o diretório `data` e todos os arquivos dentro dele. Porém, a segunda linha instrui que o `README.md` é uma exceção.

Observe que a ordem é importante nesse caso. Caso contrário, não funcionará.

### Obtendo um arquivo gitignore para Laravel

Para obter um arquivo `gitignore` para Laravel, você pode pegar o arquivo do [repositório oficial do Laravel no Github](https://github.com/laravel/laravel/).

O arquivo seria parecido com isso:

```
/node_modules
/public/hot
/public/storage
/storage/*.key
/vendor
.env
.env.backup
.phpunit.result.cache
Homestead.json
Homestead.yaml
npm-debug.log
yarn-error.log
```

Ele inclui essencialmente todos os arquivos e pastas que não são necessários para rodar a aplicação.

### Usando o gitignore.io

Como o número de frameworks e aplicações cresce a cada dia, pode ser difícil manter seus arquivos `.gitignore` atualizados ou pode ser complicado se você precisar procurar o arquivo `.gitignore` correto para cada framework específico que usar.

Recentemente descobri um projeto open-source chamado [gitignore.io](https://www.toptal.com/developers/gitignore/). É um site e uma ferramenta de linha de comando com uma enorme lista de arquivos `gitignore` pré-definidos para diferentes frameworks.

Tudo o que você precisa fazer é visitar o site e buscar pelo framework específico que está usando.

Por exemplo, vamos buscar um arquivo `.gitignore` para Node.js:

![Arquivo gitignore para Nodejs](https://imgur.com/bjT2aHP)

Depois é só clicar no **Create button** e você terá instantaneamente um arquivo `.gitignore` bem documentado para seu projeto Node.js, que ficará assim:

```
# Criado por https://www.toptal.com/developers/gitignore/api/node
# Editar em https://www.toptal.com/developers/gitignore?templates=node

### Node ###
# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
lerna-debug.log*

# Relatórios de diagnóstico (https://nodejs.org/api/report.html)
report.[0-9]*.[0-9]*.[0-9]*.[0-9]*.json

# Dados de runtime
pids
*.pid
*.seed
*.pid.lock

# Diretório para libs instrumentadas geradas por jscoverage/JSCover
lib-cov

# Diretório de cobertura usado por ferramentas como istanbul
coverage
*.lcov

# Cobertura de teste nyc
.nyc_output

# Armazenamento intermediário do Grunt (https://gruntjs.com/creating-plugins#storing-task-files)
.grunt

# Diretório de dependências do Bower (https://bower.io/)
bower_components

# Configuração node-waf
.lock-wscript

# Addons binários compilados (https://nodejs.org/api/addons.html)
build/Release

# Diretórios de dependências
node_modules/
jspm_packages/

# Arquivos de declaração TypeScript v1
typings/

# Cache do TypeScript
*.tsbuildinfo

# Diretório opcional de cache npm
.npm

# Cache opcional do eslint
.eslintcache

# Cache Microbundle
.rpt2_cache/
.rts2_cache_cjs/
.rts2_cache_es/
.rts2_cache_umd/

# Histórico opcional do REPL
.node_repl_history

# Saída do 'npm pack'
*.tgz

# Arquivo de integridade do Yarn
.yarn-integrity

# Arquivo de variáveis de ambiente dotenv
.env
.env.test

# Cache parcel-bundler (https://parceljs.org/)
.cache

# Saída de build do Next.js
.next

# Saída de build / generate do Nuxt.js
.nuxt
dist

# Arquivos do Gatsby
.cache/
# Comente a linha public se seu projeto usa Gatsby e não Next.js
# https://nextjs.org/blog/next-9-1#public-directory-support
# public

# Saída de build do vuepress
.vuepress/dist

# Diretórios Serverless
.serverless/

# Cache FuseBox
.fusebox/

# Arquivos DynamoDB Local
.dynamodb/

# Arquivo de porta TernJS
.tern-port

# Armazena versões do VSCode usadas para testar extensões VSCode
.vscode-test

# Fim de https://www.toptal.com/developers/gitignore/api/node
```

### Usando o gitignore.io CLI

Se você gosta de linha de comando, o projeto gitignore.io oferece uma versão CLI também.

Para instalar no Linux, basta rodar o seguinte comando:

```bash
git config --global alias.ignore \
'!gi() { curl -sL https://www.toptal.com/developers/gitignore/api/$@ ;}; gi'
```

Se estiver usando outro sistema operacional, recomendo conferir a documentação [aqui](https://docs.gitignore.io/install/command-line) para saber como instalar para seu Shell ou OS específico.

Depois de instalar o comando `gi`, você pode listar todos os arquivos `.gitignore` disponíveis do gitignore.io rodando:

```bash
gi list
```

Por exemplo, se você precisar rapidamente de um arquivo `.gitignore` para Laravel, basta rodar:

```bash
gi laravel
```

E você receberá um arquivo `.gitignore` bem documentado para Laravel:

```
# Criado por https://www.toptal.com/developers/gitignore/api/laravel
# Editar em https://www.toptal.com/developers/gitignore?templates=laravel

### Laravel ###
/vendor/
node_modules/
npm-debug.log
yarn-error.log

# Específico do Laravel 4
bootstrap/compiled.php
app/storage/

# Específico do Laravel 5 & Lumen
public/storage
public/hot

# Específico do Laravel 5 & Lumen com caminho público alterado
public_html/storage
public_html/hot

storage/*.key
.env
Homestead.yaml
Homestead.json
/.vagrant
.phpunit.result.cache

# Laravel IDE helper
*.meta.*
_ide_*

# Fim de https://www.toptal.com/developers/gitignore/api/laravel
```

### Conclusão

Ter um arquivo `gitignore` é essencial, e é ótimo poder usar uma ferramenta como o [gitignore.io](gitignore.io) para gerar seu arquivo `gitignore` automaticamente, dependendo do seu projeto!

Se você gostou do projeto gitignore.io, não deixe de conferir e contribuir com o projeto [aqui](https://github.com/toptal/gitignore.io).
