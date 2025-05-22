# Guia de contribuição

### Histórico de Versões

|Versão|Data|Descrição|Autor(s)|
|---|---|---|---|
|1.0| 05/05/25 | criação inicial do documento de Guia de Contribuição|[Luana Torres](https://github.com/luanatorress)|


## 1. Introdução

**Como contribuir para o projeto Vai Pela Sombra ?**

Siga as diretrizes abaixo.

## 2. Diretrizes para contribuir

### 2.1 Politica de branches

#### Repositórios de desenvolvimento

Nos repositórios do código do projeto temos uma branch principal, a **master**, e uma branch para desenvolvimento, a **develop**. 

A branch **master** é a branch mais estável do projeto, que estará em produção. Essa branch é protegida de commits e para o desenvolvimento de novas funcionalidades, deve receber Pull Requests (PRs). Ela estará em produção para as releases. Já a **develop** serve como uma branch de segurança. 

Os PRs devem ser sempre feitos para a **develop** para que, após o merge, componham as Releases.

##### Novas branches

As branches para o desenvolvimento de novas features devem ser criadas a partir da branch **develop** e devem seguir o padrão **x-nome-da-issue**, onde **x** é o número da issue que será resolvida na branch, acompanhado pelo nome da issue.

Os Pull Requests das novas branches devem ser feitos para a branch **develop**.

Em casos de correções rápidas de bugs, a branch deve seguir o padrão **FIX-x-problema-a-ser-resolvido**, onde x é o número da issue, caso exista.

#### Repositório de documentação

No repositório de documentação na **develop** está o código da página de documentação do github pages. A branch **develop** está protegida e só deve aceitar modificações por Pull Requests.

As novas branches, assim como nos repositórios de desenvolvimento devem seguir a estrutura **x-nome-da-issue**.

### 2.2 Politica de Issues

A criação de novas *issues* deverá seguir um dos padrões estabelecidos abaixo:

#### 2.2.1 Bug report

Tem o objetivo de relatar problemas, erros, defeitos ou falhas.
---
name: Bug report
about: Criação de relatório de bug
title: 'BUG: <nome curto e descritivo>'
labels: ''
assignees: ''
---

# Título

[Resumo curto e descritivo do problema]

## Descrição

[Descreva o problema detalhadamente. Inclua informações como o que estava acontecendo quando o problema ocorreu, que comportamento esperado não aconteceu, qualquer mensagem de erro que apareceu, etc.]

## Passos para reproduzir

[Descreva passo a passo como reproduzir o problema. Inclua todas as etapas necessárias para ver o problema.]

1. Passo 1
2. Passo 2
3. Passo 3

## Comportamento esperado

[Descreva o comportamento esperado que não está acontecendo.]

## Comportamento atual

[Descreva o comportamento atual que está acontecendo.]

## Capturas de tela

[Se possível, inclua capturas de tela que mostrem o problema.]

## Ambiente

[Descreva o ambiente em que o problema ocorreu, por exemplo:]

- Sistema operacional:
- Navegador (se aplicável):
- Versão do aplicativo:

## Soluções propostas

[Se tiver alguma ideia de como resolver o problema, descreva aqui.]



#### 2.2.2 História de usuário

Usada para descrever funcionalidades a nível de história de usuário;

---
name: História de Usuário
about: Criação de história de usuário
title: 'US \<id\>: \<síntese da US \>'
labels: ''
assignees: ''
---

# US \<id\>: \<sintese da US \>
<!-- Ex.: Cadastrar novos usuários -->

**Descrição**

Eu como ***persona*** gostaria de ***realizar*** para ***alcançar um objetivo***.

Exemplo: Como usuário que está planejando uma viagem, quero ver fotos de hotéis e pontos turísticos, para que eu possa usar de inspiração e tomar decisões de destinos.

**Tarefas**

- [ ] Escrever testes

**Critérios de Aceitação**

- [ ] Testável;


#### 2.2.3 Geral

Utilizado para criar ou relatar tarefas ou outras atividades gerais.
---
name: Geral
about: Tarefas gerais
title: ''
labels: ''
assignees: ''

---

**Descrição**
Deve conter uma descrição detalhada explicando a finalidade para a qual à issue foi criada.

**Tarefas :** 
- [ ] Tarefa 1;

***Requisitos:***
As issues devem possuir título, descrição, no mínimo um assinante (assignee) responsável, labels, milestone(a sprint que deve ser concluída) e estimated(pontuação) para as issues pontuadas.

### 2.3 Política de Commit

Os *commits* deverão seguir o padrão de mensagens especificado pelo [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) [2]. As seguintes regras também se aplicam:

- A descrição de um *commit* deve ser escrita em Português;
- Um *commit* deve referenciar a *issue* trabalhada;
- Um *commit* deve representar uma unidade de trabalho. Por exemplo: não adicionar arquivos relacionados a *issues* diferentes no mesmo *commit*;

Exemplo: **Issue 1: Realizar autenticação do usuário (serviço)**

```bash
git commit -m "#1 feat: adicionado serviço de autenticação"
```

### 3 Referências

> EQUIPE ALECTRION 2023-1. Guia de Contribuição. Disponível em: https://fga-eps-mds.github.io/2023-1-Alectrion-DOC/documentacao/guiaDeContribuicao/

> CONVENTIONAL COMMITS. Conventional Commits. Disponível em: https://www.conventionalcommits.org/en/v1.0.0/