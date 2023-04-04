---
layout: section
---

# Camada de persistência
Responsável por realizar operações de busca e persistência do modelo.

---

# Repositório de receitas
Responsável por realizar operações de busca e persistência de `receitas`

<div v-click>

Podemos criar uma abstração do que seria um repositório de receitas

```ts
interface RecipeRepository {
    save(recipe: Recipe): Promise<void>
}
```

</div>

<div v-click>
    
E podemos criar a implementação de `RecipeRepository`

```ts
class MongoDBRecipeRepository implements RecipeRepository {
    async save(recipe: Recipe): Promise<void> {
        await this.collection.insertOne(recipe)
    }
}
```

</div>
