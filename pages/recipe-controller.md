---
layout: section
---

# Camada de controladores
Responsável por receber e responder requisições http.

---

# Controller de receitas
Responsável por receber e responder requisições `http`

<div v-click-hide>

Podemos começar a compor nossas instâncias
```ts
const router = Router()
const repository = new MongoDBRecipeRepository()
const service = new RecipeService(repository)
```

</div>

<div v-after>

E agora podemos implementar o router do nosso `framework http`

```ts {5-12}
const router = Router();
const repository = new MongoDBRecipeRepository()
const service = new RecipeService(repository)

router.post("/recipes", async (req: Request, res: Response) => {
  try {
    await service.createNewRecipe(req.body)
    return res.status(201).send()
  } catch (e) {
    return res.status(e.statusCode).json(e.message)
  }
})
```

</div>
