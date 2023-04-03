---
layout: cover
background: false
---

# Camada de serviços

---

# Serviço de receitas
Responsável por interagir com a camada de `modelo` e `repositório` e executar as regras de negócio

<div v-click-hide>

Vamos receber nossa instância de repositório como dependência

```ts
class RecipeService {
    constructor(private readonly repository: RecipeRepository) {}
}
```

</div>

<div v-after>
E vamos implementar nossas regras de negócio

```ts {4-12}
class RecipeService {
    constructor(private readonly repository: RecipeRepository) {}

    async createNewRecipe(recipe: Recipe): Promise<void> {
        const { error } = validate(recipe)
        if (error) throw new BadRequestError(`invalid recipe: ${error}`)
        try {
            await this.repository.save(recipe)
        } catch (e) {
            throw new InternalServerError("internal error")
        }
    }
}
```

</div>