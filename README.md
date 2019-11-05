# API Brydge


#### Autenticação:

É necessário passar o parâmetro API_TOKEN no HEADER da requisição

**API_TOKEN** - Token de autenticação fornecido com o seu perfil

### Listar Bandeiras

URL ```/api/ListCardBrand```

Resposta

 ```json
{
   "status":"success",
   "brands":[
      {
         "BAND_ID":"ff08fb93-29a6-4dc8-9de5-1447c630bb1b",
         "BAND_NOME":"Visa"
      },
      {
         "BAND_ID":"0c6601b6-3fd9-4ec2-84fc-2a9f6b022ae9",
         "BAND_NOME":"MasterCard"
      }
   ]
}

 ```


### Listar Cartões de Crédito


URL ```/api/ListCards```

Resposta

 ```json
{
   "status":"success",
   "cards":[
      {
         "CARD_ID":"a395ee07-b03b-42b1-80f3-15c69a7a2e35",
         "CARD_ULTIMOS_DIGITOS":1234,
         "BAND_ID":"ff08fb93-29a6-4dc8-9de5-1447c630bb1b"
      }
   ]
}
 ```


### Cash-in Cartão de Crédito


URL ```/api/CashIn```

Parâmetros POST (FormData)

 - **TRA_VALOR** - valor da transação
 - **CARD_ID** - ID do cartão de crédito (quando já cadastrado)

   ou

 - **CARD_NUMERO** - Numero do cartão de crédito
 - **CARD_NOME** - Nome do portador do cartão
 - **CARD_CVC** - Código de segurança
 - **CARD_MES_VENCIMENTO** - Mas de vencimento do cartão 
 - **CARD_ANO_VENCIMENTO** - Ano de vencimento do cartão 
 - **CARD_CREDITO** - true/false para função crédito do cartão 
 - **BAND_ID** - ID da bandeira do cartão, pode ser obtido através do endpoint ```/API/ListCardBrand```


Resposta Sucesso

```json
{
	
	"status":"success",
	"message":"Transação realizada com sucesso"

}
```

Resposta Erro

```json
{
	
	"status":"error",
	"message":"Não foi possível realizar a transação"

}
```

