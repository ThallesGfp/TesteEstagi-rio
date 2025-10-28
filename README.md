# 🧩 Teste Prático – Integração HTTP com o OMIE

## 📘 Contexto
O OMIE é uma plataforma de gestão empresarial que disponibiliza diversos serviços por meio de uma API RESTful.  
Neste teste, queremos avaliar sua capacidade de **interpretar uma documentação técnica**, **entender a estrutura de uma requisição HTTP** e **montar um JSON adequado** para consumir um serviço de API.

Você encontrará abaixo **um exemplo de requisição completa** (já resolvida) e, em seguida, deverá **construir outra requisição semelhante**, com base nesse modelo e na documentação fornecida.

---

## 📚 Materiais de Referência
Use os links abaixo para se guiar e consultar detalhes sobre endpoints, parâmetros e exemplos:

- [Configuração do Postman com o OMIE](https://ajuda.omie.com.br/pt-BR/articles/5412735-configurando-o-postman#h_155b4aaa50)  
- [Documentação principal do desenvolvedor OMIE](https://developer.omie.com.br/)  
- [Lista de serviços e métodos da API OMIE](https://developer.omie.com.br/service-list/)

---

## 🧠 Objetivo do Teste
Você deverá montar **duas requisições HTTP** para a API do OMIE:

1. **(Exemplo fornecido)** Inserir uma conta a receber.  
2. **(Desafio proposto)** Listar todas as contas a receber do mês de novembro.  

---

## ✅ Exemplo Resolvido – Inserir uma Conta a Receber

### 📝 Descrição
Esta requisição cria uma nova conta a receber no sistema OMIE, enviando os dados do cliente, valor e vencimento.

### **Detalhes da Requisição**
**Verbo HTTP:** `POST`  
**URL:** `https://app.omie.com.br/api/v1/financas/contareceber/`  
**Headers:**
```
Content-Type: application/json
```

### **Body (JSON)**
```json
{
  "call": "IncluirContaReceber",
  "app_key": "teste",
  "app_secret": "teste",
  "param": [
    {
      "codigo_lancamento_integracao": "1761667332",
      "codigo_cliente_fornecedor": 4214850,
      "data_vencimento": "28/10/2025",
      "valor_documento": 100,
      "codigo_categoria": "1.01.02",
      "data_previsao": "28/10/2025",
      "id_conta_corrente": 4243124
    }
  ]
}
```

> 🔍 **Explicação:**  
> A requisição envia um objeto JSON ao endpoint `contareceber` com a chamada `IncluirContaReceber`.  
> Os campos `app_key` e `app_secret` autenticam a requisição.  
> Dentro de `param`, são passados os detalhes da conta a ser criada.

---

## 🚀 Desafio do Candidato – Listar Contas a Receber de Novembro

Agora, com base na estrutura do exemplo acima, **monte uma nova requisição HTTP** para **listar todas as contas a receber do mês de novembro**.

### O que você deve fazer:
Monte um documento contendo:

1. **Verbo HTTP** utilizado (ex: `POST`);  
2. **URL** do serviço correspondente (consulte a documentação OMIE para identificar o endpoint correto);  
3. **Headers** obrigatórios (como `Content-Type`);  
4. **Body (JSON)** contendo os parâmetros necessários para filtrar as contas a receber com vencimento **entre 01/11/2025 e 30/11/2025**;  
5. **Pequena explicação (2–3 linhas)** sobre o que a requisição faz.

### **Informações que você deve usar**
- `"call": "ConsultarContaReceber"`  
- `"app_key": "teste"`  
- `"app_secret": "teste"`  

Você pode se basear na estrutura do exemplo resolvido, adaptando apenas o `"call"` e o conteúdo de `"param"` conforme o serviço de consulta exige.

---

## 📦 Entrega Esperada
Entregue um arquivo em formato `.txt`, `.md` ou `.pdf` contendo:

- A requisição completa (URL, verbo, headers e body em JSON);  
- Uma breve explicação sobre o que ela faz;  
- (Opcional) Caso deseje, pode demonstrar a montagem no **Postman** ou via **cURL** e anexar prints ou comandos.

---

## 💬 Resumo
Este teste tem como objetivo avaliar se o candidato:

- Entende a estrutura de uma requisição HTTP (verbo, headers, body, endpoint);  
- Consegue ler e adaptar um exemplo prático;  
- Sabe pesquisar e aplicar o que encontra na documentação de uma API real;  
- É cuidadoso na formatação e clareza das respostas.
