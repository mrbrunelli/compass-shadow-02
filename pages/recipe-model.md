---
layout: section
---

# Camada de domínio
Reponsável por representar uma entidade do negócio.

---

# Modelo da receita
Responsável por representar uma entidade do negócio.

<div v-click-hide>

O primeiro passo é modelar o que será uma `receita` na nossa aplicação

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

<div v-after>

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
