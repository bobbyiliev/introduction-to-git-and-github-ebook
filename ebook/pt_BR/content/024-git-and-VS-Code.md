# Git e VS Code

Por mais que eu goste de usar o terminal para minhas tarefas diárias, no final das contas prefiro realizar várias tarefas em uma única janela (GUI) ou fazer tudo diretamente pelo terminal.

No passado, eu usava editores de texto (vim, nano, etc.) no terminal para editar o código dos meus repositórios e depois utilizava o cliente git para commitar minhas alterações. Mas depois migrei para o Visual Studio Code para gerenciar e desenvolver meu código.

Recomendo que você confira este artigo sobre por que usar o Visual Studio. É um artigo do próprio site do Visual Studio.

[Por que você deve usar o Visual Studio](https://code.visualstudio.com/docs/editor/whyvscode)

O Visual Studio Code possui gerenciamento de controle de versão integrado (SCM) e inclui suporte ao Git nativamente. Muitos outros provedores de controle de versão estão disponíveis através de extensões no Marketplace do VS Code. Ele também suporta múltiplos provedores de controle de versão simultaneamente, permitindo abrir todos os seus projetos ao mesmo tempo e fazer alterações sempre que necessário.

## Instalando o VS Code

Você precisa instalar o Visual Studio Code. Ele roda nos sistemas operacionais macOS, Linux e Windows.

Siga os guias específicos para cada plataforma abaixo:

- [macOS](https://code.visualstudio.com/docs/setup/mac)
- [Linux](https://code.visualstudio.com/docs/setup/linux)
- [Windows](https://code.visualstudio.com/docs/setup/windows)

Você precisa instalar o Git antes de obter esses recursos. Certifique-se de instalar pelo menos a versão 2.0.0. Se não tiver o git instalado em sua máquina, confira este artigo útil sobre [Como começar com Git](https://www.digitalocean.com/community/tutorials/how-to-contribute-to-open-source-getting-started-with-git)

Você precisa definir seu nome de usuário e e-mail na configuração do Git, ou o git irá usar informações da sua máquina local ao commitar. Precisamos fornecer essas informações porque o Git as insere em cada commit que fazemos.

Para definir isso, execute os seguintes comandos:

```bash
git config --global user.name "John Doe"
git config --global user.email "johnde@domain.com"
```

As informações serão salvas no seu arquivo `~/.gitconfig`.

```
[user]
    name = John Doe
    email = johndoe@domain.com
```

Com o Git instalado e configurado em sua máquina local, você está pronto para usar o Git para controle de versão com o Visual Studio ou usando o terminal.

## Clonando um repositório no VS Code

O bom é que o Visual Studio detecta automaticamente se você abriu uma pasta que é um repositório. Se já abriu um repositório, ele será visível na Visualização de Controle de Código Fonte.

![Clonando um repositório no VS Code](https://cdn.devdojo.com/images/february2021/article1.png)

Se ainda não abriu uma pasta, a visualização de controle de código fonte dará a opção de Abrir Pasta da sua máquina local ou Clonar Repositório.

Se selecionar Clonar Repositório, será solicitado a URL do repositório remoto (por exemplo, no GitHub) e o diretório pai onde o repositório local será colocado.

Para um repositório do GitHub, você encontra a URL na caixa de diálogo Code do GitHub.

## Criar um branch

Para criar um branch, abra o comando pallet:

- Windows: Ctrl + Shift + P
- Linux: Ctrl + Shift + P
- MacOS: Shift + CMD + P

E selecione `Git Create Branch...`

![Criar um branch](https://cdn.devdojo.com/images/february2021/artcile3.png)

Depois basta digitar um nome para o branch. Lembre-se que no canto inferior esquerdo você pode ver em qual branch está. O padrão será o main, e se criar o branch com sucesso, verá o nome do novo branch criado.

![Criar um branch](https://cdn.devdojo.com/images/february2021/article4.png)

Se quiser alternar entre branches, abra o comando pallet e procure por `Git checkout to` e selecione o branch main ou outro branch.
![Criar um branch](https://cdn.devdojo.com/images/february2021/article5.png)

## Configurar um template de mensagem de commit

Se quiser agilizar o processo e ter um template pré-definido para suas mensagens de commit, pode criar um arquivo simples com essas informações.

Para isso, abra o terminal se estiver no Linux ou macOS e crie o seguinte arquivo: .gitmessage no seu diretório pessoal. Para criar o arquivo, abra-o no seu editor favorito, coloque o conteúdo padrão desejado e salve. Exemplo de conteúdo:

```bash
cat ~/.gitmessage
```

```
#Título

#Resumo do commit

#Inclua Co-authored-by para todos os colaboradores.
```

Para informar ao Git para usar esse arquivo como template padrão que aparece no editor ao rodar `git commit`, defina o valor da configuração `commit.template`:

```bash
$ git config --global commit.template ~/.gitmessage
$ git commit
```

## Conclusão

Se você prefere programar no Visual Studio Code e também usa controle de versão, recomendo que experimente interagir com os repositórios no VS Code. Acredito que cada um tem seu estilo e pode fazer as coisas de forma diferente dependendo do momento. Desde que você possa adicionar/modificar seu código e depois commitar as alterações no repositório, não existe um jeito certo ou errado de fazer isso. Por exemplo, você pode editar seu código no vim e enviar as alterações usando o git no terminal, ou programar no Visual Studio e commitar usando o terminal. Você é livre para fazer do jeito que achar mais conveniente. Usar o git dentro do VS Code pode tornar seu fluxo de trabalho mais eficiente e robusto.

## Fontes adicionais:

* [Controle de Versão](https://code.visualstudio.com/docs/editor/versioncontrol) - Leia mais sobre o suporte integrado ao Git.
* [Visão geral da configuração](https://code.visualstudio.com/docs/setup/setup-overview) - Configure e comece a usar o VS Code.
* [GitHub com Visual Studio](https://www.notion.so/Git-version-control-with-Visual-Studio-Code-8de38af5cf324b9d89c4827e32dfe173) - Leia mais sobre o suporte ao GitHub no VS Code
* Você também pode conferir este mini tutorial em vídeo sobre como usar o básico do controle de versão Git no Visual Studio Code

Fonte:

* Contribuído por: [Alex Georgiev](https://twitter.com/AlexGeorgiev17).
* Publicado originalmente [aqui](https://devdojo.com/alexg/version-control-with-visual-studio-code-1).
