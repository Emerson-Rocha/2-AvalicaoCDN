# 📚 Atividade Prática – MongoDB: Schema Validation e Índices

## 🎯 Objetivo da Aula

Desenvolver conhecimentos práticos sobre validação de documentos e criação de índices no MongoDB, utilizando o MongoDB Shell (`mongosh`).

Ao final da atividade, o aluno deverá compreender como garantir a integridade dos dados e analisar o desempenho das consultas utilizando índices.

## 🛠️ Tecnologias e ferramentas

- MongoDB
- MongoDB Shell (`mongosh`)
- MongoDB Compass (opcional)
- Git e GitHub
- Visual Studio Code

## 📋 Conteúdos abordados

1. Criação de banco de dados e coleções.
2. Validação de documentos utilizando JSON Schema.
3. Definição de campos obrigatórios (`required`).
4. Definição de tipos de dados (`bsonType`).
5. Utilização de valores permitidos (`enum`).
6. Definição de valores mínimos (`minimum`).
7. Inserção de documentos com `insertMany()`.
8. Consulta dos índices existentes.
9. Criação de índices simples.
10. Criação de índices compostos.
11. Análise de desempenho utilizando `explain("executionStats")`.

## 🚀 Instruções para realizar a atividade

### Etapa 1 – Criar o banco de dados

Crie o banco de dados com o nome:

`loja_eletronicos`

### Etapa 2 – Criar a coleção com validação

Crie uma coleção chamada `produtos`, utilizando JSON Schema para validar os documentos.

A validação deverá contemplar:

- Nome do produto.
- Categoria.
- Marca.
- Preço.
- Estoque.
- Garantia.
- Status do produto.
- Especificações técnicas.

Utilize os recursos `required`, `properties`, `bsonType`, `enum` e `minimum`.

### Etapa 3 – Inserir os documentos

Execute o comando `insertMany()` para inserir os produtos disponibilizados no material da atividade.

Confira se os documentos foram inseridos corretamente.

### Etapa 4 – Consultar os índices

Verifique quais índices já existem na coleção `produtos`.

Utilize o comando:

```javascript
db.produtos.getIndexes()
```

### Etapa 5 – Criar índices

Crie os seguintes índices:

**1. Índice simples no campo categoria**

```javascript
db.produtos.createIndex({ categoria: 1 })
```

**2. Índice simples no campo marca**

```javascript
db.produtos.createIndex({ marca: 1 })
```

**3. Índice composto nos campos categoria e preco**

```javascript
db.produtos.createIndex({
    categoria: 1,
    preco: 1
})
```

### Etapa 6 – Analisar o desempenho das consultas

Utilize o comando `explain("executionStats")` para analisar o comportamento das consultas.

Observe os seguintes indicadores:

| Indicador | Significado |
|---|---|
| COLLSCAN | Leitura sequencial da coleção |
| IXSCAN | Utilização de índice |
| totalDocsExamined | Quantidade de documentos examinados |
| executionTimeMillis | Tempo de execução da consulta |

### Etapa 7 – Comparar os resultados

Compare o desempenho de uma consulta antes e depois da criação de um índice.

Identifique as diferenças entre a execução utilizando `COLLSCAN` e `IXSCAN`.

## 📦 Entrega da atividade

O aluno deverá disponibilizar no GitHub:

- Arquivo com os comandos utilizados na atividade.
- Scripts de criação do banco e da coleção.
- Comandos de inserção dos documentos.
- Comandos de criação dos índices.
- Evidências da execução das consultas.
- Comparação dos resultados antes e depois da criação dos índices.

## 📸 Evidências

Adicione capturas de tela demonstrando:

1. Criação da coleção com validação.
2. Inserção dos documentos.
3. Consulta dos índices.
4. Criação dos índices simples e composto.
5. Resultado do `explain("executionStats")`.
6. Comparação de desempenho das consultas.

## 📖 Material de apoio

Consulte o PDF disponibilizado pelo professor para acompanhar os comandos e os dados utilizados na atividade.

## 💻 Organização sugerida do repositório

```text
atividade-mongodb/
│
├── README.md
├── scripts/
│   └── atividade-mongodb.js
│
└── evidencias/
    ├── schema.png
    ├── insert.png
    ├── indexes.png
    └── explain.png
```

---

**Bons estudos!** 🚀

