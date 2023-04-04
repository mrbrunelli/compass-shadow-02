# Composição de modelos

Responsável por representar uma entidade do negócio.

Nossos modelos serão compostos da seguinte forma

```ts {all|11}
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
