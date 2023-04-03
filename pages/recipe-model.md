# Modelo da receita

<div v-click-hide>

O primeiro passo é modelar o que será uma receita

```ts
interface Recipe {
  id?: string;
  name: string;
  ingredients: string[];
  preparation: string;
  recipeAuthor: RecipeAuthor;
}
```

</div>

<div v-click>

Veja que estamos fazendo referência a outro modelo

```ts {6}
interface Recipe {
  id?: string;
  name: string;
  ingredients: string[];
  preparation: string;
  recipeAuthor: RecipeAuthor;
}
```

</div>
