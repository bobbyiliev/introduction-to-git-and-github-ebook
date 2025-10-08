# Fluxo de Trabalho no Git

Agora que você conhece os comandos básicos, vamos juntar tudo e passar por um fluxo de trabalho básico com Git.

Normalmente, o fluxo de trabalho é assim:

* Primeiro, você clona um projeto existente com o comando `git clone`, ou, se estiver começando um novo projeto, inicializa com o comando `git init`.

* Depois disso, antes de começar a alterar o código, é melhor criar um novo branch Git onde irá trabalhar. Você pode fazer isso com o comando `git checkout -b NOME_DO_SEU_BRANCH`.

* Com o branch pronto, você começa a fazer as alterações no seu código.

* Quando terminar as alterações, precisa prepará-las com o comando `git add`.

* Para salvar/registrar as alterações no seu repositório Git local, execute o comando `git commit` e forneça uma mensagem de commit descritiva.

* Para enviar suas alterações locais para o projeto remoto no GitHub, use o comando `git push origin NOME_DO_SEU_BRANCH`.

* Por fim, depois de enviar suas alterações, você precisa abrir um pull request (PR) do seu branch para o branch principal do repositório.

* É considerado uma boa prática adicionar algumas pessoas como revisores e pedir para revisarem as alterações.

* Finalmente, depois que as alterações forem aprovadas, o PR será mesclado ao branch principal, trazendo todas as suas alterações do seu branch para o branch principal.

O processo geral fica assim:

![Git Workflow](https://imgur.com/fosS9En.png)

Minha dica é criar um novo repositório e passar por esse processo algumas vezes até se sentir totalmente confortável com todos os comandos.
