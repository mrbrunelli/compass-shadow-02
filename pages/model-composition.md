# Composição de modelos

Nossos modelos ficarão dessa forma

```ts
interface RecipeAuthor {
  name: string;
  email: string;
}

interface Recipe {
  id?: string;
  name: string;
  ingredients: string[];
  preparation: string;
  recipeAuthor: RecipeAuthor;
}
```
