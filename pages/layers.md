---
layout: cover
background: https://images.unsplash.com/photo-1646321155200-0dbac918eeef?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1174&q=80
---

# Como ficaram nossas camadas?

---
layout: section
---
# Resumo das camadas


```mermaid
flowchart LR
    subgraph App
        direction LR
        subgraph ControllerLayer
            RecipeController
        end
        subgraph ServiceLayer
            RecipeService
        end
        subgraph DomainLayer
            RecipeModel
            RecipeAuthorModel
        end
        subgraph RepositoryLayer
            RecipeRepository
            Database
        end
        RecipeController -->|Entrada| RecipeService
        RecipeService -->|Saída| RecipeController
        RecipeService --> RecipeRepository
        RecipeService --> RecipeModel
        RecipeModel --> RecipeAuthorModel
        RecipeRepository --> Database
    end
    style RecipeModel stroke-dasharray: 5 5
    style RecipeAuthorModel stroke-dasharray: 5 5
```
