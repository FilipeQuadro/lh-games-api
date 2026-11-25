# LH Games — Atividade 3: Service de consumo de API (SENAI)

Loja de games em **Angular 15 + Angular Material + Bootstrap** que consome uma API REST
fake (**json-server**) para listar, cadastrar, editar e excluir produtos, com área restrita protegida por login.

## O que foi entregue (checklist da atividade)
| Requisito | Onde está |
|---|---|
| Tela que lista produtos (área restrita) | `src/app/restrito/lista-produto` |
| Listar produtos na tela inicial com dados da API | `src/app/inicio` (`*ngFor` + `ProdutoService.getProdutos()`) |
| Service de produtos (GET, POST, PUT, DELETE) | `src/app/produto.service.ts` |
| Tela de cadastro de produto | `src/app/restrito/cadastro-produto` |
| Tela de edição de produto | `src/app/restrito/atualiza-produto` |
| Service de login + token | `src/app/login.service.ts` (grava `token` no `localStorage`) |
| Tela de login | `src/app/login` |
| Usuário e senha | usuário **aluno**, senha **1234** |
| Guard do Angular | `src/app/guard.guard.ts` (`CanActivate`) |
| Rotas da área restrita | `src/app/app-routing.module.ts` e `src/app/restrito/restrito-routing.module.ts` |
| Esconder menu | `mostraMenu` (Subject) no `LoginService` + `*ngIf` em `app.component.html` |
| Logout | botão no `menu-restrito` (limpa o token e volta para o login) |

## Como rodar
```bash
npm install
npm install -g json-server
json-server --watch dbgames.json   # API em http://localhost:3000/produtos
ng serve                           # site em http://localhost:4200
```

## Testes no Postman
- **GET** `http://localhost:3000/produtos` — lista os produtos
- **POST** `http://localhost:3000/produtos` — cadastra (Body → x-www-form-urlencoded: id, produto, descricao, foto, preco)
- **PUT** `http://localhost:3000/produtos/4` — altera o produto 4
- **DELETE** `http://localhost:3000/produtos/4` — exclui o produto 4

Desenvolvido por Filipe.
