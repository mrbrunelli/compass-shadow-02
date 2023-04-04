# Modelo do autor da receita
Responsável por representar uma entidade do negócio.

Agora devemos modelar o que será um `autor da receita` na nossa aplicação

```ts
interface RecipeAuthor {
  name: string;
  email: string;
}
```

<v-clicks depth="2">

- ## Alguns pontos a considerar:
  - Veja que nosso `RecipeAuthor` não possuí `id`
  - Isso significa que nós não iremos ter persistência individual desse modelo
  - Por mais que ele seja um modelo, ele apenas cumpre o papel na composição de `Recipe`
  - Se quisessemos sua persistência, deveríamos adicionar um campo `id` para ele

</v-clicks>