---
layout: section
---

# Camada de domínio
Reponsável por representar uma entidade do negócio.

---

# Modelo da receita
Responsável por representar uma entidade do negócio.


O primeiro passo é modelar o que será uma `receita` na nossa aplicação

```ts {all|2|6}
interface Recipe {
  id?: string;
  name: string;
  ingredients: string[];
  preparation: string;
  recipeAuthor: RecipeAuthor;
}
```


<div v-click>

- Veja que estamos fazendo referência a outro modelo

</div>
