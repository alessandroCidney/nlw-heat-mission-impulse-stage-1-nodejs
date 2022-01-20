# NLW Heat - Mission Impulse - Stage 1
Esta aplicação foi desenvolvida durante as aulas do evento NLW Heat, realizado pela Rocketseat.

## O que esta aplicação faz?
Este projeto consiste em uma API desenvolvida em Node.js por meio da qual é possível cadastrar novos usuários e novas mensagens, sendo possível estabelecer conexões com ela utilizando WebSocket ou utilizar suas rotas por meio de requisições.

## Rotas

### /github (GET)
Acessando essa rota é possível fazer o login com o GitHub e obter o código necessário para realizar a autenticação.
Para utilizá-la, basta fazer uma requisição do tipo GET e fazer login com o GitHub, o que pode ser feito facilmente acessando a rota pelo navegador.

### /signin/callback
A rota que está configurada para receber as informações após o login com o GitHub ser realizado.
Você não precisa acessá-la manualmente, pois, se o app estiver corretamente configurado no GitHub, você será redirecionado para ela após fazer o login na rota /github e obterá o código necessário para autenticar.

### /authenticate (POST)
Esta rota deve ser utilizada para realizar a autenticação utilizando o código obtido por meio da rota /github. Basta fazer uma requisição POST para ela passando o código por meio de uma propriedade `code` no body da requisição.

O retorno consiste em um token de acesso e as informações do usuário

Exemplo em JavaScript:
```javascript
const githubCode = '...';

fetch('http://localhost:4000/authenticate', {
    method: 'POST',
    body: JSON.stringify({
        code: githubCode
    })
})
.then((response) => response.json())
.then((data) => console.log(data))
.catch((err) => console.log('Error', err));
```

README.md em construção...