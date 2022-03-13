# json-server-base

Nessa aplicação o usuário pode se cadastrar, fazer login, publicar um post e um comentário.

## Cadastro:

https://json-server-lucas-tatagiba.herokuapp.com/register --> Para se cadastrar deve se utilizar este endpoint com o seguinte corpo:

```json
{
  "email": "email@email.com",
  "password": "suaSenha",
  "name": "seuNome",
  "age": 29
}
```

Exemplo de sucesso da resposta da requisição cadastro (201 Created):

```json
{
  "accessToken": "seu token",
  "user": {
    "email": "email@email.com",
    "name": "seuNome",
    "age": 29,
    "id": 1
  }
}
```

## Login:

https://json-server-lucas-tatagiba.herokuapp.com/login --> Para se logar o usuário deve utilizar este endpoint com o seguinte corpo:

```json
{
  "email": "email@email.com",
  "password": "suaSenha"
}
```

Exemplo de sucesso da resposta da requisição login (201 Created):

```json
{
  "accessToken": "seu Token",
  "user": {
    "email": "email@email.com",
    "name": "seuNome",
    "age": 29,
    "id": 1
  }
}
```

## Posts:

https://json-server-lucas-tatagiba.herokuapp.com/posts --> Para postar alguma coisa o usuário deverá está logado e deverá ser dono da conta que irá postar, para isso ao logar-se, deverá utilizar seu token de acesso gerado e utilizar no Bearer no header do posts e também utilizar a propriedade userId com o id de seu usuário no corpo da requisição. O corpo da requisição deverá estar com este formato:

```json
{
  "image": "urlImage",
  "comments": [],
  "userId": 1
}
```

Exemplo de sucesso da resposta da requisição posts (201 Created):

```json
{
  "image": "urlImage",
  "comments": [],
  "userId": 1,
  "id": 1
}
```

## comments:

https://json-server-lucas-tatagiba.herokuapp.com/comments --> Nesse endpoint o usuário pode adicionar comentários, para isso o usuário deverá estar logado apenas. Não sendo necessário o uso de algum ID, Exemplo de corpo de requisição:

```json
{
  "comment": "teste"
}
```

Exemplo de sucesso da resposta da requisição comments (201 Created):

```json
{
  "comment": "teste",
  "id": 1
}
```
