<h1 align="center">
  <img src="assets/reprograma-fundos-claros.png"alt="logo reprograma" width="500">
</h1>

## Projeto Final

Turma Online 18 - Todas em Tech | back-end | Semana 18 | 2022 | Aluna: Leinane Santos da Conceição

## SUS Conecte: Mapeamento das Unidades de Saúde, da cidade de Santo Antônio de Jesus

<div align="center">
  <img src="./assets/hospital.gif">
</div>

---
Esse projeto tem como objetivo fazer o mapeamento das unidades de saúde da cidade de Santo Antônio de jesus, para que seja mais fácil o acesso da população a esses locais. Minha experiência como usuária destas unidades de saúde, trouxe a inquietação sobre a falta de informação que a população tem sobre essas unidades de saúde. Pois, para saber sobre os atendimentos disponíveis, medicamentos e os médicos que atuam no local, as pessoas têm que se dirigir até o posto de saúde, que em alguns casos, nem o telefone é divulgado para a população. A total falta de informação sobre esses postos, pode fazer com que algumas pessoas deixem de buscar pelos atendimentos disponíveis nesses locais. Com isso, o intuito do projeto, é deixar as informações sobre as unidades de saúde, da cidade de Saj, mais acessível para a população santo-antonienses.

---

### Sobre A API

SUS Conecte, é um projeto que foi desenvolvido como requisito final para a conclusão do curso “Todas em Tech” da {Reprograma}. Neste projeto, foi desenvolvido uma API Rest, conectada ao banco de dados MongoBD, que recebe os dados das unidades de saúde, de sues funcionários, os atendimentos realizados no local e os horários de atendimentos. Esses dados são registrados no banco de dados e poderão ser acessados pelos usuários destas unidades de saúde, de forma online, via página web, que será implementada futuramente.

---

### Métodos

API foi desenvolvida utilizando a linguagem javaScript e Nodejs, utilizando o método CRUDS para fazer a requisições
ao banco de dados MongoDB Atlas e testando as rotas rotas no insomnia.

---

### Funcionalidaes

<body>
<ol>
<li>Listar todas as unidades de saúde públicas da cidade de Santo Antônio de Jeus;</li>
<li>Listar o endereço, telefone e horários de atendimentos;</li>
<li>Listar os atendimentos disponíveis nas unidades de saúde;</li>
<li>Listar os Profissionais que atuam no local.</li>
</ol>
</body>


### 📑 Documentação
---

#### `[GET]`/postos/buscar

Retorna todas unidades-de-saúde do banco de dados

> Resposta do Servidor: HTTP status 200 OK

```json
[
  {
    "_id": "638675e8b4f0e83792e1f68b",
    "nome": "USF Alto Santo Antônio",
    "cnpj": "010203",
    "telefone": "756315654",
    "isIniciativaPrivada": false,
    "medicos_atuantes": ["Dr.Marcos", "Dr.Daniel"],
    "enfermeiros_atuantes": ["Camila", "Marta", "Carol", "Lucas"],
    "serviços_Especializados": [
      "ATENCAO PRIMARIA",
      "IMUNIZACAO",
      "SERVICO DE ATENCAO AO PACIENTE COM TUBERCULOSE",
      "SERVICO DE ATENCAO AO PRE-NATAL, PARTO E NASCIMENTO",
      "SERVICO DE VIGILANCIA EM SAUDE",
      "TELECONSULTORIA"
    ],
    "pessoas_responsaveis": "Direitora Marcia",
    "id": "638675e9b4f0e83792e1f68c",
    "createdAt": "2022-11-29T21:13:13.396Z",
    "updatedAt": "2022-11-29T21:13:13.396Z",
    "__v": 0
  }
]
```

---

#### `[GET]`/postos/buscar/:id

Rota que retorna uma unidade-de-saúde do id indicado

> Aceita como parâmetro de consulta

| Parâmetro | Descrição   |
| --------- | ----------- |
| id        | id do posto |

> Resposta do Servidor: HTTP status 200 OK

```json
[
  {
    "_id": "6386785eb4f0e83792e1f68e",
    "nome": "USF Urbis III",
    "cnpj": "010304",
    "telefone": "7536324710",
    "isIniciativaPrivada": false,
    "medicos_atuantes": ["Drª.Livia", "Drª.Diana"],
    "enfermeiros_atuantes": ["Ana", "Maria"],
    "serviços_Especializados": [
      "ATENCAO PRIMARIA",
      "IMUNIZACAO",
      "SERVICO DE ATENCAO AO PACIENTE COM TUBERCULOSE",
      "SERVICO DE ATENCAO AO PRE-NATAL, PARTO E NASCIMENTO",
      "SERVICO DE VIGILANCIA EM SAUDE",
      "TELECONSULTORIA"
    ],
    "endereco": {
      "cep": "44435428",
      "rua": "RUA A",
      "numero": "S/N",
      "complemento": " ",
      "referencia": "prox. da academia",
      "estado": "Bahia",
      "cidade": "Santo Antônio de Jesus",
      "bairro": "Urbis 3"
    },
    "instalações": {
      "tipo_Instalação": "Ambulatorial: ODONTOLOGIA, SALA DE CURATIVO, SALA DE IMUNIZACAO, SALA DE ENFERMAGEM (SERVICOS)",
      "descrição": "Clinicas Indiferenciado",
      "leitos": " 0",
      "salas": " 4"
    },
    "pessoas_responsaveis": "Diretora Ana",
    "id": "6386785eb4f0e83792e1f68f",
    "createdAt": "2022-11-29T21:23:42.345Z",
    "updatedAt": "2022-11-29T21:23:42.345Z",
    "__v": 0
  }
]
```

---

#### `[POST]` /postos/create

Cadastra uma unidade-de-saúde

> Resposta do Servidor:  HTTP status 201 OK

Exemplo:

```json
{
  "nome": "Urbis 4",
  "cnpj": "010607",
  "telefone": "7",
  "isIniciativaPrivada": false,
  "endereco": {
    "cep": "",
    "rua": "",
    "numero": "S/N",
    "complemento": " ",
    "referencia": "prox. da praça",
    "estado": "Bahia",
    "cidade": "Santo Antônio de Jesus",
    "bairro": "Irma Dulce"
  },
  "medicos_atuantes": ["Dr. Valter", "Dr.Manuel"],
  "enfermeiros_atuantes": ["Aline", "Fernanda", "Antônio"],
  "horario_de_Atendimento": {
    "Segunda-Feira": "08:00 às 17:00 horas",
    "Terça-Feira": "08:00 às 17:00 horas",
    "Quarta-Feira": "08:00 às 17:00 horas",
    "Quinta-Feira": "08:00 às 17:00 horas",
    "Sexta-Feira": "08:00 às 17:00 horas"
  },
  "serviços_Especializados": [
    "ATENCAO PRIMARIA",
    "IMUNIZACAO",
    "SERVICO DE ATENCAO AO PACIENTE COM TUBERCULOSE",
    "SERVICO DE ATENCAO AO PRE-NATAL, PARTO E NASCIMENTO",
    "SERVICO DE VIGILANCIA EM SAUDE",
    "TELECONSULTORIA"
  ],
  "pessoas_responsaveis": "Diretor Pedro",
  "instalações": {
    "tipo_Instalação": "AMBULATORIAL:  ODONTOLOGIA, SALA DE CURATIVO,CLINICAS BASICAS, SALA DE IMUNIZACAO, SALA DE ENFERMAGEM (SERVICOS)",
    "descrição": "CONSULTORIOS MEDICOS",
    "leitos": " 0",
    "salas": " 6"
  }
}
```

---

#### `[PUT]`/postos/atualizar/:id

Atualiza uma unidade-de-saúde

> Resposta do Servidor: HTTP status 200 OK

```json

  {
    "nome": " CentroSaj",
    "cnpj": "093546728",
    "telefone": "75936321256"
  }

```

---

#### `[DELETE]`/postos/deletar/:id

Rota que Deleta uma unidade-de-saude

 Requerido

| Parâmetro    |        Descricão        |
| -------------| ----------------------- |
| id           |      id do Posto        |
|Baerer Token  | Tokem para autenticação |

> Resposta do Servidor: HTTP status 204 NO CONTENT

```json
{}
```
---
### Autenticação do Usuário
---
#### `[POST AUTH]` /user/criar

 > Rota que cria um usuário 
 
 > Requerido

 Body: 

```json

{
	"name":"Urbis3",
	"email":"www.usfUrbis.com",
	"password":"*****"
	
}
```
> Resposta do Servidor: HTTP status 201 Ok

```json
{
	"message": "Seu cadastro foi criado com sucesso",
	"salvarUsuario": {
		"name": "Urbis3",
		"email": "www.usfUrbis.com",
		"password": "$2b$10$XHzVvS9vYp21w6kumcAU4.NA5Dtlotdw.aPBgQIsH6x8fzcaK5tQa",
		"createdAt": "2022-12-15T14:53:28.502Z",
		"_id": "639b3c15956d771e8f48b617",
		"__v": 0
	}
}

```
---
#### `[POST AUTH]` /user/criar
Rota para fazer login

```json
{
	
	"email":"www.usfUrbis3.com",
	"password":"*****"
	
}
```
> Resposta do Servidor: HTTP status 200 Ok

```json
{
	"message": "Você está logadah!",
	"token": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9."
}

```


---

### Arquitetura do projeto - MVC

```
MVC
📂 API
├─ 📂 src
│  ├─ 📂 controllers
│  │  └─ UsfController.js
│  │  └─ authfController.js
│  │  └─ userController.js
│  ├─ 📂 models
│  │  └─ UsfModel.js
│  │  └─ userSchema.js
|  ├─ 📂 middlewares
│  │  └─ auth.js
│  ├─ 📂 database
│  │  └─ mongoConfig.js
│  ├─ 📂 routes
│  │  └─ UsfRouter.js
│  │  └─ userRoutes.js
│  │  └─ indexRoutes.js
│  └─ app.js
├─ package-lock.json
|_ .env
├─ .env.example
├─ package.json
├─ .gitignore
├─ README.md
├─ vercel.json
└─ server.js

```
---

### Tecnologias utilizadas

| Tecnologias Utilizadas |
| ---------------------- |
| NodeJs                 |
| Git/GitHub             |
| JavaScript             |
| MongoDB Atlas          |
| Insomnia               |
| VScode                 |

---

### Dependências

| Dependência | Versão |
| ----------- | ------ |
| NPM         | >= 8x  |
| Express     | -      |
| Nodemon     | -      |
| Cors        | -      |

---

### Implementações Futuras

1. Desenvolver o front-end;
2. criar um aplicativo para celular (sus conecte), onde as pessoas terão acesso a informações das unidades de saúde
   de suas cidades. Informações sobre os medicamentos que estão disponíveis nas farmácias das unidades de saúde, os atendimentos que serão realizados durante o mês, os médicos que atuarão no local, os horários de atendimentos e os documentos necessários para o atendimento. também constará com informações sobre o planejamento familiar, realizados nas unidades de saúde.
3. Implementar testes unitários;
4. Implementar espaço para experiência do usuário.

---


