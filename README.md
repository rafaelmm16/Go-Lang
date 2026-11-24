# Go-lang

Repositório de estudos e prática da linguagem **Go (Golang)**, organizado de forma progressiva — desde os fundamentos da linguagem até a estruturação de módulos, consumo de APIs REST e um projeto prático de terminal (TUI).

## Pré-requisitos

- [Go](https://go.dev/dl/) `1.21` ou superior instalado e configurado no `PATH`

Para verificar a instalação:

```bash
go version
```

## Estrutura do repositório

```text
Go-lang/
├── 01-introducao/
│   ├── main.go
│   ├── variaveis.go
│   ├── condicoes.go
│   ├── repeticao.go
│   ├── funcoes.go
│   └── calculadora.go
├── 02-structs-e-ponteiros/
│   ├── struct.go
│   └── ponteiro.go
├── 03-oop-go/
│   ├── metodo.go
│   └── interfaces.go
├── 04-get-e-api/
│   └── api.go
├── 05-json/
│   └── json.go
├── 06-organizacao/
│   ├── go.mod
│   ├── main.go
│   ├── internal/
│   │   └── domain/
│   │       └── users.go
│   └── pkg/
│       └── web/
│           └── users.go
├── projetos/
│   └── jogo-clicker/
│       ├── go.mod
│       ├── go.sum
│       └── clicker.go
├── .gitignore
└── README.md
```

## Módulos e conteúdos

### 1. Introdução (`01-introducao/`)

Fundamentos básicos da sintaxe em Go:

| Arquivo | Descrição |
| --- | --- |
| [`main.go`](01-introducao/main.go) | Laço `for` com condição de parada (`break`) e chamada de função (`DizBomdia`) |
| [`variaveis.go`](01-introducao/variaveis.go) | Declaração de variáveis (`var`, `:=`), constantes (`const`) e formatação com `fmt.Printf` |
| [`condicoes.go`](01-introducao/condicoes.go) | Estruturas condicionais `if`, `else if` e `else` |
| [`repeticao.go`](01-introducao/repeticao.go) | Laços `for` tradicionais, `for range` e uso de slices |
| [`funcoes.go`](01-introducao/funcoes.go) | Funções com parâmetros, múltiplos retornos e escopo de variáveis |
| [`calculadora.go`](01-introducao/calculadora.go) | Calculadora interativa via terminal usando `fmt.Scanln` e `switch` |

### 2. Structs e Ponteiros (`02-structs-e-ponteiros/`)

| Arquivo | Descrição |
| --- | --- |
| [`struct.go`](02-structs-e-ponteiros/struct.go) | Definição da struct `Pessoa`, função construtora `NewUser` e slices de structs |
| [`ponteiro.go`](02-structs-e-ponteiros/ponteiro.go) | Passagem de ponteiros (`*int` e `&`) para alterar valores em memória na função `HappyBirth` |

### 3. Orientação a Objetos em Go (`03-oop-go/`)

| Arquivo | Descrição |
| --- | --- |
| [`metodo.go`](03-oop-go/metodo.go) | Métodos com ponteiro receptor (`*Site`) para modificar campos de uma struct |
| [`interfaces.go`](03-oop-go/interfaces.go) | Definição e implementação da interface `Humano` com as structs `Pessoa` e `Robo` |

### 4. Requisições HTTP e APIs (`04-get-e-api/`)

| Arquivo | Descrição |
| --- | --- |
| [`api.go`](04-get-e-api/api.go) | Requisição `HTTP GET` usando `net/http` e leitura do corpo da resposta com `io.ReadAll` |

### 5. Manipulação de JSON (`05-json/`)

| Arquivo | Descrição |
| --- | --- |
| [`json.go`](05-json/json.go) | Consumo de API REST e desserialização de JSON para structs Go usando `encoding/json` (`json.Unmarshal`) |

### 6. Organização de Projetos (`06-organizacao/`)

Exemplo de aplicação modularizada seguindo convenções de diretórios Go (`internal/` e `pkg/`):

- [`go.mod`](06-organizacao/go.mod): definição do módulo `Consumer`
- [`main.go`](06-organizacao/main.go): ponto de entrada que consome o pacote `web` e lista os usuários
- [`internal/domain/users.go`](06-organizacao/internal/domain/users.go): definição da struct de domínio `Users`
- [`pkg/web/users.go`](06-organizacao/pkg/web/users.go): função `GetUsers()` responsável pela requisição HTTP e conversão JSON

### Projeto: Jogo Clicker (`projetos/jogo-clicker/`)

Aplicação interativa de terminal (TUI) construída com a biblioteca [`github.com/rivo/tview`](https://github.com/rivo/tview):

- [`clicker.go`](projetos/jogo-clicker/clicker.go): interface com botão de clique, contador de pontos, goroutine de atualização periódica e sincronização com `sync.Mutex`
- [`go.mod`](projetos/jogo-clicker/go.mod) e [`go.sum`](projetos/jogo-clicker/go.sum): gerenciamento de dependências do módulo `clicker`

## Como executar

### Arquivos de estudo (`01-introducao` a `05-json`)

Como cada diretório de estudo possui múltiplos arquivos com `package main` independentes, execute informando o caminho do arquivo desejado:

```bash
go run 01-introducao/variaveis.go
go run 01-introducao/calculadora.go
go run 02-structs-e-ponteiros/ponteiro.go
go run 05-json/json.go
```

### Módulo `06-organizacao`

```bash
cd 06-organizacao
go run .
```

### Projeto `jogo-clicker`

```bash
cd projetos/jogo-clicker
go mod download
go run .
```
