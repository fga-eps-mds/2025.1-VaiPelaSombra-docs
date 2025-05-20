# Plano de Qualidade do Produto

## 1. Introdução

A qualidade é um dos pilares fundamentais de qualquer produto. A norma **ISO 9126** define qualidade como “a totalidade de características e critérios de um produto ou serviço que determinam sua capacidade de satisfazer necessidades declaradas ou implícitas”.

Posteriormente, essa norma foi substituída pela **ISO 25010**, publicada em 2011, que padroniza os critérios de qualidade para produtos de software. Segundo essa nova definição, qualidade é o grau em que um sistema atende às necessidades explícitas e implícitas dos stakeholders, gerando valor para os envolvidos.

A ISO 25010 estabelece **oito características essenciais** para avaliar a qualidade de um software:

* **Adequação funcional**
* **Eficiência de desempenho**
* **Compatibilidade**
* **Usabilidade**
* **Confiabilidade**
* **Segurança**
* **Manutenibilidade**
* **Portabilidade**

## 2. Objetivo

O objetivo da elaboração deste plano de qualidade é especificar as ferramentas que serão utilizadas e as métricas analisadas pela equipe para que seja definida a qualidade do produto e, assim, tomar decisões mais assertivas. Dessa forma, os objetivos deste documento são:

- Definir os objetivos de qualidades.

- Apresentar formas de atingir os objetivos de qualidade.

- Selecionar e coletar métricas

- Apresentar a interpretação e uso das métricas para o produto.

- Especificar procedimentos, técnicas e ferramentas

## 3. Objetivos de qualidade

De acordo com os objetivos estabelecidos pela **norma ISO 25010:2011**, a análise da qualidade de um projeto é estruturada em três áreas principais: **qualidade interna**, **qualidade externa** e **qualidade de uso**.

As qualidades interna e externa estão voltadas à avaliação do próprio produto e se baseiam em **seis características fundamentais**:

* **Funcionalidade**
* **Confiabilidade**
* **Usabilidade**
* **Eficiência**
* **Manutenibilidade**
* **Portabilidade**

Cada uma dessas características é composta por subcaracterísticas, que podem ser observadas durante o uso do software e são influenciadas diretamente pelos atributos internos do sistema.

Já a **qualidade de uso** foca na perspectiva do usuário final e envolve **quatro características principais**:

* **Eficácia**
* **Produtividade**
* **Segurança**
* **Satisfação**

Essas características resultam da interação entre os elementos da qualidade interna e externa, refletindo o valor entregue ao usuário. Ao considerar essas três dimensões, a análise da qualidade do projeto torna-se mais abrangente, permitindo avaliar tanto os aspectos técnicos do software quanto a experiência real de uso, garantindo uma visão completa sobre a qualidade do produto.

## 4. Verificação e validação

Para alcançar os objetivos de qualidade do projeto, iremos adotar duas técnicas de verificação e validação:

- Análise estática do código: Essa técnica utiliza o Sonar Cloud como ferramenta de análise estática de código, para obter métricas mensuráveis. Essa ferramenta identifica potenciais problemas no código e fornece informações relevantes para a gestão da qualidade do projeto, que colabora para a tomada de decisões e pontos a serem atacados pela equipe.

- Testes automatizados: Foram realizados testes automatizados, incluindo testes unitários e de integração. Essa abordagem permite validar tanto os cenários esperados quanto situações de erro, garantindo o funcionamento adequado do software em diversas condições. 

Essas duas técnicas combinadas permitem abordar aspectos técnicos, garantindo a qualidade do projeto de forma abrangente e satisfatória.

## 5. Padrões, práticas, convenções e métricas

### ISOs e modelos de qualidade

A principal ISO e modelo utilizados no projeto são:

* NBR - ISO/IEC 25010 [2]

* Modelo de Qualidade Q-Rapids [3]

### Métricas

As métricas definidas para o VaiPelaSombra foram:

| Métrica                  | Descrição                                           |
| ------------------------ | --------------------------------------------------- |
| Files                    | Quantidade de arquivos de código                    |
| Functions                | Quantidade de funções no código                     |
| Complexity               | Complexidade ciclomática                            |
| Comment Lines Density    | Densidade (%) de linhas comentadas                  |
| Duplicated Lines density | Densidade (%) de linhas duplicadas                  |
| Coverage                 | Cobertura de código pelos testes                    |
| Ncloc                    | Quantidade de linhas de código                      |
| Tests                    | Testes unitários e de integração                    |
| Test Errors              | Testes que possuem erros                             |
| Test Failures            | Testes que falharam                                 |
| Test Execution Time      | Tempo de execução dos testes                        |
| Security Rating          | Avaliação de segurança de falhas e vulnerabilidades |

### Métricas para o produto

Através do uso de métricas, é possível identificar as subcaracterísticas relacionadas e, por consequência, avaliar a qualidade do produto. Essa avaliação também permite analisar a produtividade do projeto e obter resultados que podem influenciar as decisões tomadas em relação ao seu desenvolvimento.

A partir das métricas especificadas no SonarCloud e no Q-Rapids e dos valores coletados pelas métricas definidas, foram estabelecidos valores mínimos aceitáveis para cada métrica no projeto VaiPelaSombra, conforme tabela abaixo.

| Métrica                      | Valor        |
| ---------------------------- | ------------ |
| Complexity                   | até 10       |
| Comment Lines Density (%)    | até 30%      |
| Duplicated Lines Density (%) | até 5%       |
| Coverage                     | acima de 80% |
| Test Failures                | 0            |
| Test Errors                  | 0            |
| Security Rating              | 0 (A)        |
| Satisfação do usuário        | acima de 3   |

## 6. Testes

O software é uma das construções mais complexas dos humanos por isto está sujeito a inconsistências e erros. O conjunto de processos para validar o correto funcionamento de um software são chamados testes e as atividades de teste surgiram justamente para evitar que estes erros cheguem ao usuário final. [4]

* Testes de unidade: a maior parte dos testes se encontram nesta categorização e são utilizados para verificar pequenas partes de um código, normalmente uma classe somente.

* Testes de integração: estes testes verificam uma transação completa ou uma funcionalidade

* Testes de sistema: testes que simulam uma sessão com usuário real

## 7. Ferramentas, técnicas e metodologias

[Jest](https://jestjs.io/pt-BR/): Framework de testes para TypeScript;

[ESLint](https://eslint.org/):  Ferramenta de verificação de código, que garante que o código esteja de acordo com os padrões encontrados no ECMAScript;

[Codcov](https://about.codecov.io/): Ferramenta que verifica cobertura de código;

[SonarCloud](https://www.sonarsource.com/products/sonarcloud/?gads_campaign=SC-Class01-Brand&gads_ad_group=SonarCloud&gads_keyword=sonarcloud&gclid=Cj0KCQjwyLGjBhDKARIsAFRNgW_ldned9rPbZ6BecorNDUxvGxjLbdoawwMROpUJnpr5qGlKr3oBOh0aAnZlEALw_wcB): Ferramenta de varredura de código para analisar o código de acordo com as regras e métricas definidas.

## 8. Controle de código 

A fim de assegurar a execução de procedimentos de qualidade, utilizamos uma combinação de tarefas automatizadas e manuais. 

As tarefas automatizadas incluem: controle de versão, controle de código, controle de commits, testes automatizados. Essas tarefas são realizadas por ferramentas e sistemas que auxiliam na garantia da qualidade do software.

## 9. Coleta e manutenção

O **processo de manutenção de sistemas de software** tem como objetivo principal realizar modificações no produto após a liberação de releases. Essas alterações podem ser motivadas por necessidades de correção, aprimoramento de desempenho, adaptação a novos ambientes ou melhorias em outros atributos do sistema.

A norma classifica a manutenção em quatro categorias principais, conforme a natureza das modificações:

* **Manutenção Adaptativa**: Trata da adequação do software a mudanças no ambiente onde ele opera, como atualizações de dependências, compatibilidade com novas versões de sistemas operacionais, ou atendimento a novos requisitos legais e regulatórios.

* **Manutenção Corretiva**: Foca na identificação e correção de falhas detectadas após a entrega do software, seja por meio de testes contínuos, relatórios de erros ou feedback de usuários.

* **Manutenção Preventiva**: Visa aumentar a confiabilidade e facilitar manutenções futuras. Engloba ações como refatoração de código, melhorias na documentação, aplicação de boas práticas de desenvolvimento e correção de áreas propensas a falhas.

* **Manutenção Perfectiva**: Envolve melhorias solicitadas pelos usuários, como aprimoramento de funcionalidades existentes, adição de novos recursos ou ajustes na interface e desempenho para melhorar a experiência geral.

Manter um software em constante evolução é essencial para garantir sua funcionalidade, relevância e alinhamento com as expectativas dos usuários e com o ambiente em que está inserido.


## 4. Referências

> [1] ENGSOFTMODERNA. Engenharia de Software Moderna. Disponível em: https://engsoftmoderna.info/. Acesso em: 19 maio 2025.

> [2] Importância dos testes de software na qualidade do sistema. TreinaWeb. Disponível em: https://www.treinaweb.com.br/blog/importancia-dos-testes-de-software-na-qualidade-do-sistema. Acesso em: 19 maio 2025.

> [3] ISO/IEC 25010. ISO 25000. Software and data quality. 2011. Disponível em: https://iso25000.com/index.php/en/iso-25000-standards/iso-25010. Acesso em 19 maio 2025


## 5. Histórico de versão

|**Data**|**Descrição**|**Autor(es)**|
|--------|-------------|--------------|
| 19/05/2025 | Criação de plano de qualiidade do produto | Suzane Duarte |