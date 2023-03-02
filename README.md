# API de Games
Esta API é utilizada 
## Endpoints
### GET /games
Esse endpoint é responsável por retornar a listagem de todos os games cadastrados no banco de dados.
#### Parametos
Nenhum
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber o token JWT para conseguir acessar endpoints protegidos na API.

Exemplo de resposta:
```
{
    "token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJpZCI6MSwiZW1haWwiOiJhbGZyZWRvbGl1MTRAbGl2ZS5jb20iLCJpYXQiOjE2Nzc3NjM3OTUsImV4cCI6MTY3NzkzNjU5NX0.5ANCwMPDANY_Onp-hWd_4xj04yKz6nxMC1NqA4XrEFU"
}
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Token inválido, Token expirado.

Exemplo de resposta:
```
{
    "err": "Token invalido"
}
```

### POST /auth
Esse endpoint é responsável por fazer o processo de login.
#### Parametos
email: E-mail do usuário cadastrado no sistema.

password: Senha do usuário cadastrado no sistema, com aquele determinado e-mail.

Exemplo:
```
{
    "email": "exemplo@dominio.com",
    "password": "123qwe"
}
```
#### Respostas
##### OK! 200
Caso essa resposta aconteça você vai receber a listagem de todos os games.

Exemplo de resposta:
```
[
    {
        "id": 1,
        "title": "Minecraft",
        "price": 40,
        "year": 2009
    },
    {
        "id": 4,
        "title": "Valorant",
        "price": 20,
        "year": 2019
    },
    {
        "id": 6,
        "title": "Runescape",
        "price": 27,
        "year": 2008
    }
]
```
##### Falha na autenticação! 401
Caso essa resposta aconteça, isso significa que aconteceu alguma falha durante o processo de autenticação da requisição. Motivos: Senha ou e-mail incorretos.

Exemplo de resposta:
```
{ err: "Credenciais invalidas!" }
```
