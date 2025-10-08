# Chaves SSH

Existem algumas maneiras de autenticar no GitHub. Essencialmente, você precisa disso para poder enviar suas alterações locais do seu laptop para o seu repositório no GitHub.

Você pode usar um dos seguintes métodos:

* HTTPS: Essencialmente, isso exigirá seu nome de usuário e senha do GitHub toda vez que tentar enviar suas alterações
* SSH: Com SSH, você pode gerar um par de chaves SSH e adicionar sua chave pública ao GitHub. Assim, você não será solicitado a informar seu nome de usuário e senha toda vez que enviar suas alterações para o GitHub.

![Login no Git e GitHub](https://imgur.com/y544tCR.png)

Uma coisa que você precisa ter em mente é que a URL do repositório GitHub é diferente dependendo se você está usando SSH ou HTTPS:

* HTTPS: `https://github.com/bobbyiliev/demo-repo.git`
* SSH: `git@github.com:bobbyiliev/demo-repo.git`

Note que ao escolher SSH, o `https://` é substituído por `git@`, e você tem `:` após `github.com` em vez de `/`. Isso é importante pois define como você irá autenticar cada vez.

### Gerando chaves SSH

Para gerar um novo par de chaves SSH caso ainda não tenha uma, você pode rodar o seguinte comando:

```bash
ssh-keygen
```

Por questões de segurança, você pode especificar uma senha, que será a senha da sua chave SSH privada.

O comando acima irá gerar 2 arquivos:

* 1 chave SSH **privada** e 1 chave SSH pública. A chave privada deve sempre ser armazenada com segurança no seu laptop e você não deve compartilhá-la com ninguém.
* 1 chave SSH **pública**, que você precisa enviar para o GitHub.

Os dois arquivos serão gerados automaticamente na seguinte pasta:

```
~/.ssh
```

Você pode usar o comando `cd` para acessar a pasta:

```bash
cd ~/.ssh
```

Depois, com o comando `ls`, pode verificar o conteúdo:

```bash
ls
```

Saída:

```
id_rsa  id_rsa.pub
```

O `id_rsa` é sua chave privada, e novamente, você não deve compartilhá-la com ninguém.

O `id_rsa.pub` é a chave pública que precisa ser enviada para o GitHub.

### Adicionando a chave SSH pública ao GitHub

Depois de criar suas chaves SSH, você precisa enviar a **chave pública** para sua conta do GitHub. Para isso, primeiro você precisa obter o conteúdo do arquivo.

Para obter o conteúdo do arquivo, use o comando `cat`:

```bash
cat ~/.ssh/id_rsa.pub
```

A saída será parecida com isto:

```
ssh-rsa AAB3NzaC1yc2EAAAADAQAB...... seu_usuario@seu_host
```

Copie tudo e então acesse o [GitHub](https://github.com) e siga estes passos:

* Clique na sua foto de perfil no canto superior direito

* Depois clique em configurações

![Configurações do GitHub](https://imgur.com/tRDwDjC.png)

* À esquerda, clique em `SSH and GPG Keys`:

![Chaves SSH](https://imgur.com/iL2E3Ux.png)

* Depois disso, clique no botão `New SSH Key`

* Especifique um título para a chave SSH, deve ser algo descritivo, por exemplo: `Chave SSH do Laptop de Trabalho`. E na área `Key`, cole sua chave SSH pública:

![Chave SSH GitHub](https://imgur.com/X89gLwD.png)

* Por fim, clique no botão `Add SSH Key` na parte inferior da página

### Conclusão

Com isso, agora você tem suas chaves SSH geradas e adicionadas ao GitHub. Assim, você poderá enviar suas alterações sem precisar digitar seu usuário e senha do GitHub toda vez.

Para mais informações sobre chaves SSH, confira este tutorial [aqui](https://www.digitalocean.com/community/tutorials/how-to-set-up-ssh-keys-2).
