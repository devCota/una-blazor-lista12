# Lista de Exercicios XII em C# .NET - IHC, UX e Heuristicas de Nielsen

![Status](https://img.shields.io/badge/status-concluido-green)
![Plataforma](https://img.shields.io/badge/platform-Windows%20%7C%20Linux-blue)
![Tecnologia](https://img.shields.io/badge/C%23-.NET%208%20Blazor-purple)
![Render](https://img.shields.io/badge/render-Interactive%20Server-0d6efd)

---

## Sobre o Projeto

Este repositorio documenta a implementacao da **Lista de Exercicios XII** da disciplina **Interacao Humano Computador e UX**, desenvolvida no contexto academico do **Centro Universitario UNA**, sob orientacao do **Professor Daniel Henrique Matos de Paiva**.

O projeto foi desenvolvido em **C# com .NET 8**, utilizando **Blazor Interactive Server**, com foco em componentizacao, estado e reutilizacao de interface no cenario do sistema **EcoMonitor** da ONG ReCiclo.

A proposta da atividade foi transformar um prototipo em uma prova de conceito funcional, com interacao em tempo real e estrutura simples.


## Objetivo da Atividade

Desenvolver uma aplicacao Blazor que apresente a tela principal do EcoMonitor com componentes reutilizaveis para registrar acoes sustentaveis.

O foco principal da entrega foi:

- criar um componente reutilizavel com `[Parameter]`
- controlar estado dinamico com contador acumulado
- responder a interacao do usuario com clique em botao

---


## Cenario Proposto

No exercicio pratico, a ONG **ReCiclo** precisa de uma PoC funcional para o sistema de gamificacao ambiental.

O sistema deve permitir que o usuario registre diferentes tipos de acoes sustentaveis e acompanhe o impacto gerado, em tempo real, na tela Home.

---

## Heuristicas de Nielsen Aplicadas

### 1. Visibilidade do status do sistema

Cada componente exibe o total acumulado e atualiza imediatamente apos o clique em **Registrar Atividade**.

### 2. Consistencia e padroes

As tres acoes sustentaveis usam o mesmo componente `EcoStatus`, mantendo padrao visual, texto e comportamento.

### 3. Reconhecimento em vez de memorizacao

As informacoes relevantes ficam visiveis no card (nome da acao, pontos por acao e total), sem exigir que o usuario memorize regras.

---

## Estrutura do Projeto

O projeto foi mantido com organizacao simples, separando layout, pagina e componente principal da atividade.

### Estrutura

```text
una-blazor-lista12/
├── Program.cs
├── EcoMonitor.csproj
├── Components/
│   ├── App.razor
│   ├── Routes.razor
│   ├── EcoStatus.razor
│   ├── EcoStatus.razor.css
│   └── Pages/
│       ├── Home.razor
│       └── Home.razor.css
└── README.md
```

### Descricao dos arquivos principais

- `Components/EcoStatus.razor` -> logica e parametros do componente reutilizavel
- `Components/EcoStatus.razor.css` -> estilo visual dos cards de atividade
- `Components/Pages/Home.razor` -> composicao da tela com tres instancias do componente
- `Components/Pages/Home.razor.css` -> layout da Home (cabecalho e grade de cards)
- `Components/App.razor` -> configuracao de renderizacao interativa da aplicacao

---

## Funcionamento da Aplicacao

Na Home, o sistema exibe tres cards de acao ambiental:

- Reciclagem de Plastico (peso 1)
- Descarte de Eletronicos (peso 5)
- Plantio de Arvores (peso 10)

Durante a interacao, o usuario pode:

- clicar em **Registrar Atividade** em qualquer card
- aumentar o total acumulado conforme o peso da acao
- visualizar feedback visual de meta atingida a partir de 100 pontos

---

## Guia de Execucao

### Requisitos

- .NET 8 SDK instalado

### Executar o projeto

Na pasta raiz do repositorio, rode:

```bash
dotnet run --launch-profile https
```

### Compilar o projeto

```bash
dotnet build
```

---

## Explicacao Tecnica do [Parameter]

O componente `EcoStatus` usa `[Parameter]` para tornar o card reutilizavel sem duplicar logica.

Parametros aplicados:

- `TituloAcao` -> define o nome da acao exibida no card
- `PesoAcao` -> define quantos pontos sao somados por clique
- `MetaAtingidaEm` -> define o valor de referencia para feedback de conquista

Com isso, a `Home.razor` instancia o mesmo componente tres vezes, alterando apenas os valores dos parametros.

---

## Conceitos Utilizados

- componentizacao com Blazor
- parametros com `[Parameter]`
- estado local com campo privado no componente
- manipulacao de eventos com `@onclick`
- renderizacao condicional com `@if`
- separacao de estrutura e estilo com `.razor` e `.razor.css`

---

## Boas Praticas Aplicadas

- codigo simples e adequado ao nivel de 1o semestre
- reutilizacao de componente para evitar duplicacao
- mensagens e layout claros para facilitar entendimento
- organizacao por responsabilidade (pagina, componente e estilo)

---

## Conclusao

O projeto entrega a proposta da Lista 12 de forma funcional, objetiva e alinhada ao enunciado.

A implementacao demonstra como conceitos de UX e usabilidade podem ser aplicados em uma interface Blazor simples, com foco em clareza de interacao, feedback visual e reutilizacao de componentes.

---

## Autor

Lucas Cota  
Estudante de Analise e Desenvolvimento de Sistemas  
Foco em Backend e Engenharia de Software
