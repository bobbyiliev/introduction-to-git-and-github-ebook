# Inicializando um projeto Git

Se você está começando um novo projeto ou se tem um projeto existente que gostaria de adicionar ao Git e depois enviar para o GitHub, é necessário inicializar um novo projeto Git com o comando `git init`.

Para manter as coisas simples, vamos supor que queremos começar a construir um projeto totalmente novo. A primeira coisa que normalmente faço é criar uma nova pasta onde vou armazenar os arquivos do projeto. Para isso, posso usar o comando `mkdir` seguido do nome da pasta, o que criará um novo diretório/pasta vazio:

```bash
mkdir novo-projeto
```

O comando acima criará uma pasta chamada `novo-projeto`. Então, como aprendemos no capítulo 4, podemos usar o comando `cd` para acessar o diretório:

```bash
cd novo-projeto
```

Depois disso, usando o comando `ls`, poderemos verificar que o diretório está completamente vazio:

```bash
ls -lah
```

Com isso, estamos prontos para inicializar um novo projeto Git:

```bash
git init
```

Você verá a seguinte saída:

```
Initialized empty Git repository in /home/devdojo/novo-projeto/.git/
```

Como você pode ver, o que o comando `git init` faz é criar uma nova pasta `.git`, que já discutimos no capítulo 5.

Com isso, você criou com sucesso um novo projeto Git vazio! Vamos para o próximo capítulo, onde você aprenderá a usar o comando `git status` para verificar o status atual do seu repositório.
