---
layout: section
background: false
---


# Fluxo da aplicação
Criação de uma nova receita <uim-angle-double-right class="text-orange-400 animate-pulse" />

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

Retornará `sucesso` para o cliente

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
background: https://images.unsplash.com/photo-1555861496-0666c8981751?ixlib=rb-4.0.3&ixid=MnwxMjA3fDB8MHxwaG90by1wYWdlfHx8fGVufDB8fHx8&auto=format&fit=crop&w=1170&q=80
---

E se der erro na validação?

---
layout: cover
background: false
---

Retornará `erro` para o cliente

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
    Validator -->|Não| BadRequest(Dados inválidos)
    BadRequest --> End(Fim)
    End -->|Erro| Server
    Server -->|Resposta de erro| Client
```

---
layout: cover
background: false
---

Fluxograma completo de criação de uma nova `receita`

<div v-click>

> A receita só poderá ser salva se todos os dados fornecidos forem válidos

</div>

```mermaid
flowchart LR
    Client((Usuário)) -->|Envia uma Receita| Server(API) --> Validator{Os dados são válidos?}
    Validator -->|Sim| Save(Salvar receita) --> DB[(Bando de dados)]
    Validator -->|Não| BadRequest(Dados inválidos)
    DB --> End(Fim)
    BadRequest --> End
    End -->|Erro ou Sucesso| Server
    Server -->|Resposta de erro ou sucesso| Client
```




