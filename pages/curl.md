# Simulação de requisição

Com nossa aplicação executando, poderíamos disparar um `POST` para nosso endpoint de `receitas`

<div v-click>

Exemplo de `POST` <uim-angle-double-down class="text-orange-400" />

```shell {monaco}
curl --location 'http://localhost:3000/recipes' \
--header 'Content-Type: application/json' \
--data-raw '{
    "name": "Carne com mandioca",
    "ingredients": [
        "costela ripa",
        "mandioca",
        "salsinha",
        "pimenta calabresa",
        "óleo",
        "alho",
        "sal"
    ],
    "preparation": "Peque uma panela de pressão, frite o alho no óleo e despeje a costela. Depois jogue a mandioca pré cozida dentro e encha de água até cobrir e feche a tampa. Deixe na pressão por 30 minutos",
    "recipeAuthor": {
        "name": "Brunelli",
        "email": "brunelli@email.com.br"
    }
}'
```

</div>