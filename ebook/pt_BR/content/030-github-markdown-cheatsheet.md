# Guia Rápido de Markdown do GitHub

### Título 1

    Marcação :  # Título 1 #

    -OU-

    Marcação :  ============= (abaixo do texto do Título 1)

### Título 2

    Marcação :  ## Título 2 ##

    -OU-

    Marcação: --------------- (abaixo do texto do Título 2)

### Título 3 ###

    Marcação :  ### Título 3 ###

#### Título 4 ####

    Marcação :  #### Título 4 ####

### Texto comum

    Marcação :  Texto comum

###  _Texto enfatizado_

    Marcação :  _Texto enfatizado_ ou *Texto enfatizado*

### ~~Texto riscado~~

    Marcação :  ~~Texto riscado~~

### __Texto forte__

    Marcação :  __Texto forte__ ou **Texto forte**

### ___Texto forte enfatizado___

    Marcação :  ___Texto forte enfatizado___ ou ***Texto forte enfatizado***

### [Link nomeado](http://www.google.fr/ "Título do link nomeado") e http://www.google.fr/ ou <http://example.com/>

    Marcação :  [Link nomeado](http://www.google.fr/ "Título do link nomeado") e http://www.google.fr/ ou <http://example.com/>

### [título-1](#titulo-1 "Ir para título-1")

    Marcação: [título-1](#titulo-1 "Ir para título-1")

### Tabela, como esta:

Primeiro Cabeçalho  | Segundo Cabeçalho
------------------- | -----------------
Célula de Conteúdo  | Célula de Conteúdo
Célula de Conteúdo  | Célula de Conteúdo

```
Primeiro Cabeçalho  | Segundo Cabeçalho
------------------- | -----------------
Célula de Conteúdo  | Célula de Conteúdo
Célula de Conteúdo  | Célula de Conteúdo
```

#### Adicionando uma barra vertical `|` em uma célula:

Primeiro Cabeçalho  | Segundo Cabeçalho
------------------- | -----------------
Célula de Conteúdo  | Célula de Conteúdo
Célula de Conteúdo  | \|

```
Primeiro Cabeçalho  | Segundo Cabeçalho
------------------- | -----------------
Célula de Conteúdo  | Célula de Conteúdo
Célula de Conteúdo  |  \| 
```

#### Tabela alinhada à esquerda, direita e centro

Cabeçalho Esquerda | Cabeçalho Direita | Cabeçalho Centro
| :--- | ---: | :---:
Célula de Conteúdo  | Célula de Conteúdo | Célula de Conteúdo
Célula de Conteúdo  | Célula de Conteúdo | Célula de Conteúdo

```
Cabeçalho Esquerda | Cabeçalho Direita | Cabeçalho Centro
| :--- | ---: | :---:
Célula de Conteúdo  | Célula de Conteúdo | Célula de Conteúdo
Célula de Conteúdo  | Célula de Conteúdo | Célula de Conteúdo
```

### `code()`

    Marcação :  `code()`

```javascript
    var codigo_especifico =
    {
        "data": {
            "lookedUpPlatform": 1,
            "query": "Kasabian+Test+Transmission",
            "lookedUpItem": {
                "name": "Test Transmission",
                "artist": "Kasabian",
                "album": "Kasabian",
                "picture": null,
                "link": "http://open.spotify.com/track/5jhJur5n4fasblLSCOcrTp"
            }
        }
    }
```

    Marcação : ```javascript
             ```
### Lista não ordenada

* Item da lista
    * Subitem
        * Sub-subitem etc
* Item da lista 2

~~~
 Marcação : * Item da lista
              * Subitem
                  * Sub-subitem etc
          * Item da lista 2
-OU-
 Marcação : - Item da lista
              - Subitem
                  - Sub-subitem etc
          - Item da lista 2 
~~~

### Lista ordenada

1. Lista numerada
    1. Lista numerada aninhada
    2. Que é numerada
2. Que é numerada

~~~
 Marcação : 1. Lista numerada
              1. Lista numerada aninhada
              2. Que é numerada
          2. Que é numerada
~~~

- [ ] Uma tarefa não concluída
- [x] Uma tarefa concluída

~~~
 Marcação : - [ ] Uma tarefa não concluída
          - [x] Uma tarefa concluída
~~~

- [ ] Uma tarefa não concluída
    - [ ] Uma sub-tarefa

~~~
 Marcação : - [ ] Uma tarefa não concluída
              - [ ] Uma sub-tarefa
~~~

> Citação
>> Citação aninhada
    Marcação :  > Citação
              >> Citação aninhada
### _Linha horizontal :_
- - - -

    Marcação :  - - - -

### _Imagem com alt :_

![texto alternativo](http://via.placeholder.com/200x150 "Título opcional")

    Marcação : ![texto alternativo](http://via.placeholder.com/200x150 "Título opcional")

### Texto recolhível:

<details>
  <summary>Título 1</summary>
  <p>Conteúdo 1 Conteúdo 1 Conteúdo 1 Conteúdo 1 Conteúdo 1</p>
</details>
<details>
  <summary>Título 2</summary>
  <p>Conteúdo 2 Conteúdo 2 Conteúdo 2 Conteúdo 2 Conteúdo 2</p>
</details>

    Marcação : <details>
               <summary>Título 1</summary>
               <p>Conteúdo 1 Conteúdo 1 Conteúdo 1 Conteúdo 1 Conteúdo 1</p>
             </details>

```html
<h3>HTML</h3>
<p> Algum código HTML aqui </p>
```

Link para uma parte específica da página:

### [Ir para o TOPO](#TOPO)

    Marcação : [texto aqui](#nome_da_secao)
              titulo_secao<a name="nome_da_secao"></a>    

### Tecla de atalho:

<kbd>⌘F</kbd>

<kbd>⇧⌘F</kbd>

    Marcação : <kbd>⌘F</kbd>

### Lista de teclas de atalho:

| Tecla | Símbolo |
| --- | --- |
| Option | ⌥ |
| Control | ⌃ |
| Command | ⌘ |
| Shift | ⇧ |
| Caps Lock | ⇪ |
| Tab | ⇥ |
| Esc | ⎋ |
| Power | ⌽ |
| Return | ↩ |
| Delete | ⌫ |
| Cima | ↑ |
| Baixo | ↓ |
| Esquerda | ← |
| Direita | → |

### Emoji:

:exclamation: Use ícones de emoji para destacar o texto. :+1:  Veja os códigos de emoji em [emoji-cheat-sheet.com](http://emoji-cheat-sheet.com/)

    Marcação : O código aparece entre dois pontos :CODIGOEMOJI:
