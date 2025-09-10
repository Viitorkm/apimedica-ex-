# 🩺 API de Médicos

Bem-vindo à documentação da **API de Médicos**.\
Esta API fornece endpoints para gerenciar médicos, pacientes e
consultas.

------------------------------------------------------------------------

## 🌐 Base URL

    https://api.medicos.com/v1

------------------------------------------------------------------------

## 🔑 Autenticação

A API utiliza **Bearer Token**.\
Inclua o header abaixo em todas as requisições autenticadas:

    Authorization: Bearer {seu_token}

------------------------------------------------------------------------

## 📚 Endpoints

### 👨‍⚕️ Médicos

#### ➕ Criar médico

`POST /medicos`

  --------------------------------------------------------------------------
  Parâmetro        Tipo       Obrigatório   Descrição
  ---------------- ---------- ------------- --------------------------------
  nome             string     ✅            Nome completo do médico

  especialidade    string     ✅            Ex: Cardiologia, Pediatria

  crm              string     ✅            Número de registro profissional

  telefone         string     ❌            Telefone de contato
  --------------------------------------------------------------------------

**Exemplo de requisição:**

``` json
{
  "nome": "Dra. Ana Costa",
  "especialidade": "Dermatologia",
  "crm": "123456-SP",
  "telefone": "(11) 99999-8888"
}
```

**Resposta de sucesso (201):**

``` json
{
  "id": "med_001",
  "nome": "Dra. Ana Costa",
  "especialidade": "Dermatologia",
  "crm": "123456-SP"
}
```

------------------------------------------------------------------------

#### 🔍 Listar médicos

`GET /medicos`

**Parâmetros de query opcionais:** - `especialidade` → Filtrar por
especialidade\
- `limit` → Limitar resultados (default: 20)

**Exemplo de resposta:**

``` json
[
  {
    "id": "med_001",
    "nome": "Dra. Ana Costa",
    "especialidade": "Dermatologia"
  },
  {
    "id": "med_002",
    "nome": "Dr. João Mendes",
    "especialidade": "Cardiologia"
  }
]
```

------------------------------------------------------------------------

### 🧑‍🤝‍🧑 Pacientes

#### ➕ Criar paciente

`POST /pacientes`

``` json
{
  "nome": "Carlos Silva",
  "data_nascimento": "1987-05-20",
  "cpf": "123.456.789-10"
}
```
