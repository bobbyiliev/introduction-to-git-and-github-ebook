# Git Clone

Na maioria das vezes, em vez de começar um projeto do zero, você vai entrar em uma empresa e começar a trabalhar em um projeto existente, ou contribuir para um projeto open source já estabelecido. Nesse caso, para obter o repositório do GitHub para sua máquina local, você precisa usar o comando `git clone`.

A maneira mais simples de clonar seu repositório do GitHub é primeiro visitar o repositório no navegador, clicar no botão verde `Code` e escolher o método que deseja usar para clonar o repositório:

![Clonar um repositório Git](https://user-images.githubusercontent.com/21223421/111689082-3ee7fd00-8834-11eb-966a-d8a3c9e8736e.png)

No meu caso, prefiro o método SSH, pois já tenho minhas chaves SSH configuradas conforme o capítulo 14.

Como estou clonando este repositório [aqui](https://github.com/bobbyiliev/introduction-to-bash-scripting), a URL ficará assim:

```
git@github.com:bobbyiliev/introduction-to-bash-scripting.git
```

Depois de copiar isso, volte ao terminal, vá até o diretório onde deseja clonar o repositório e execute o seguinte comando:

```bash
git clone git@github.com:bobbyiliev/introduction-to-bash-scripting.git
```

A saída será parecida com isto:

```
Cloning into 'introduction-to-bash-scripting'...
remote: Enumerating objects: 21, done.
remote: Counting objects: 100% (21/21), done.
remote: Compressing objects: 100% (16/16), done.
remote: Total 215 (delta 7), reused 14 (delta 4), pack-reused 194
Receiving objects: 100% (215/215), 3.08 MiB | 5.38 MiB/s, done.
Resolving deltas: 100% (114/114), done.
```

Basicamente, o comando `git clone` faz o download do repositório do GitHub para sua pasta local.

Agora você pode começar a fazer alterações no projeto criando um novo branch, escrevendo código e finalmente commitando e enviando suas alterações!

Uma coisa importante a lembrar é que, caso você não seja o mantenedor do repositório e não tenha permissão para enviar alterações diretamente, será necessário primeiro fazer um fork do repositório original e então clonar o repositório forkado da sua conta. No próximo capítulo, veremos o processo completo de como fazer um fork de um repositório!
