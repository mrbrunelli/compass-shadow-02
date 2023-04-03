# Modelo do autor da receita
Responsável por representar uma entidade do negócio

Agora devemos modelar o que será um `autor da receita` na nossa aplicação

```ts
interface RecipeAuthor {
  name: string;
  email: string;
}
```