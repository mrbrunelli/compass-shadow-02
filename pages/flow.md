---
layout: cover
background: false
---


# Fluxo da aplicação


---
layout: cover
background: false
---

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API)
```

---
layout: cover
background: false
---

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
```

---
layout: cover
background: false
---

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
    Validator -->|Sim| Save(Salvar receita) --> DB[(Banco de dados)]
    DB --> End(Fim)
```

---
layout: cover
background: false
---

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
    Validator -->|Sim| Save(Salvar receita) --> DB[(Banco de dados)]
    DB --> End(Fim)
    End -->|Sucesso| Server
    Server -->|Resposta de sucesso| Client
```

---
layout: cover
background: false
---

E se der erro na validação?

---
layout: cover
background: false
---

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
    Validator -->|Não| BadRequest(Dados inválidos)
    BadRequest --> End(Fim)
    End -->|Erro| Server
    Server -->|Resposta de erro| Client
```

---

# Fluxo completo de criação de uma receita

<div v-click>
A receita só poderá ser salva se todos os dados fornecidos estiverem válidos
</div>

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) -->|Validação dos dados| Validator{Os dados são válidos?}
    Validator -->|Sim| Save(Salvar receita) --> DB[(Bando de dados)]
    Validator -->|Não| BadRequest(Dados inválidos)
    DB --> End(Fim)
    BadRequest --> End
    End -->|Erro ou Sucesso| Server
    Server -->|Resposta de erro ou sucesso| Client
```




