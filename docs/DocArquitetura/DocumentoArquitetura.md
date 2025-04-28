# Documento de Arquitetura

## Documento de Arquitetura de Software

### 1 Introdução

Este documento tem como finalidade descrever a arquitetura de software do projeto Vai Pela Sombra, uma aplicação web voltada para o planejamento de viagens com foco em recomendações personalizadas, eventos locais e dicas culturais. A arquitetura descrita aqui visa fornecer uma visão clara das decisões técnicas e estruturais adotadas no sistema, servindo como referência para desenvolvedores, arquitetos de software, gerentes de projeto e demais partes interessadas.

#### 1.1 Finalidade

Este documento tem como finalidade descrever a arquitetura de software do projeto Vai Pela Sombra, uma aplicação web voltada para o planejamento de viagens com foco em recomendações personalizadas, eventos locais e dicas culturais. A arquitetura descrita aqui visa fornecer uma visão clara das decisões técnicas e estruturais adotadas no sistema, servindo como referência para desenvolvedores, arquitetos de software, gerentes de projeto e demais partes interessadas.

#### 1.2 Escopo

O projeto está estruturado em uma arquitetura de microserviços, com separação entre os seguintes módulos:

- **Frontend**: construído com React e TypeScript, responsável pela interface do usuário.
- **Backend:** desenvolvido em Node.js com TypeScript, responsável pela lógica de negócios, autenticação, e interação com o banco de dados.
- **API Gateway/Serviço de Integração:** também desenvolvido em Node.js, será responsável pela exposição dos dados e funcionalidades da aplicação de forma centralizada e segura.
- **Banco de Dados:** PostgreSQL, centralizando as informações sobre usuários, destinos, interesses, eventos, entre outros dados relevantes para o planejamento de viagens.

A aplicação tem como objetivo:

- Permitir que usuários cadastrem seus interesses;

- Oferecer recomendações personalizadas de destinos;

- Exibir eventos locais nos destinos selecionados;

- Fornecer dicas culturais, de saúde e segurança para viajantes;

- Possibilitar o agendamento de itinerários personalizados de viagens;

- Permitir o planejamento de viagens em grupo, facilitando a organização conjunta de roteiros e atividades.

#### 1.3 Visão Geral

Este documento está estruturado em seções que abrangem a representação geral da arquitetura, metas e restrições, visões lógica e de implementação, bem como considerações de desempenho e qualidade. Também são apresentados os principais diagramas que sustentam as decisões arquiteturais, como o Diagrama de Entidade-Relacionamento e o Diagrama Lógico de Dados.

### 2 Representação da Arquitetura

A arquitetura utilizada no projeto será baseada em microserviços. Microserviço é uma abordagem para desenvolver uma única aplicação como um conjunto de serviços, cada um rodando em seu próprio processo e se comunicando através de mecanismos leves, geralmente via HTTP. Essa abordagem promove a escalabilidade, a independência entre os módulos e a facilidade de manutenção.

#### 2.1 Diagrama de Relações

![Diagrama de Relações](./assets/imagemDiagramaRelacoes.png)
<center> 

*Fonte: [Pablo Guilherme](https://github.com/PabloGJBS)*

</center>

### 3 Metas e Restrições de Arquitetura

Nesta seção, são descritas as principais metas e restrições que guiam a arquitetura do sistema *Vai Pela Sombra*. As decisões aqui documentadas têm impacto direto sobre a escolha de tecnologias, frameworks, práticas de segurança, escopo funcional e usabilidade da aplicação. Essas restrições visam garantir a padronização do desenvolvimento, a consistência entre os microserviços e o cumprimento dos requisitos não funcionais definidos.

A seguir, apresenta-se uma tabela com as principais restrições técnicas e metas do projeto:

| Restrição   | Ferramenta/Descrição |
|-------------|----------------------|
| **Linguagem** | TypeScript (frontend e backend) |
| **Framework** | React (Frontend), Node.js + Express (Backend), API Gateway em Node.js |
| **Plataforma** | Web responsiva (navegador desktop e mobile) |
| **Segurança** | Os usuários serão autenticados via token JWT, com verificação em cada requisição feita ao backend via API Gateway. O acesso a funcionalidades como criação de itinerários e gerenciamento de grupos será restrito a usuários autenticados. |
| **Idioma** | Português (com possibilidade futura de suporte multilíngue) |

### 4. Visão Lógica

#### 4.1 Visão geral: Pacotes e Camadas

A aplicação *Vai Pela Sombra* adota uma arquitetura baseada em microserviços, com divisão clara entre frontend e backend. O frontend é desenvolvido com React e TypeScript, sendo responsável exclusivamente pela camada de apresentação (View). Já o backend é construído com Node.js e Express, implementando a lógica de negócios por meio do padrão MVC (Model-View-Controller), onde cada microserviço encapsula sua própria responsabilidade.

Essa separação em camadas oferece maior modularidade, facilita a manutenção do código, permite reuso em diferentes contextos e favorece o desenvolvimento paralelo entre equipes. A seguir, é detalhada a estrutura lógica do backend baseada no modelo MVC.

#### 4.1.1 Model

A camada de Model representa a estrutura dos dados da aplicação e é responsável pela comunicação com o banco de dados PostgreSQL. Utilizando ORMs como Sequelize ou Prisma, essa camada permite abstrair as operações de leitura e escrita no banco, facilitando a manutenção e evitando dependências diretas com a estrutura relacional. Cada microserviço possui seus próprios modelos (ex: Usuário, Destino, Evento, Grupo).

#### 4.1.2 Controller

Os Controllers são responsáveis por receber as requisições HTTP, processar a lógica de negócio e coordenar a interação entre o Model e a resposta enviada ao cliente (via API Gateway). Essa camada centraliza a validação dos dados, chamadas de serviços auxiliares, regras de autenticação/autorização e tratamento de exceções.

#### 4.1.3 View

A camada de View, no contexto do backend, é representada pelas respostas formatadas em JSON que são retornadas aos consumidores da API. Já a View completa da aplicação é implementada no frontend, utilizando os recursos do React para apresentar dados ao usuário de forma interativa, responsiva e dinâmica. O React atua tanto como template quanto como controlador local de estado de interface.

#### 4.2 Diagrama 1

### 5 Visão de Implementação

#### 5.1 DeR - Diagrama Entidade e Relacionamento

A seguir apresentamos o Diagrama Entidade Relacionamento do projeto

![Diagrama Entidade Relacionamento](./assets/imagemDER.png)

<center> 

*Fonte: [Pablo Guilherme](https://github.com/PabloGJBS)*

</center>

Descrição do Diagrama Entidade-Relacionamento (DER)

-  **Usuário:**
    - **idUsuario** (chave primária): Identificador único do usuário.
    - **nome**: Nome do usuário.
    - **email**: E-mail do usuário.
    - **senha**: Senha do usuário.
    - **dataCriacao**: Data de criação do cadastro do usuário.

- **Perfil**
    - **idPerfil** (chave primária): Identificador único do perfil.
    - **bioPerfil**: Biografia ou descrição pessoal do usuário.
    - **preferenciasViagem**: Preferências de viagem do usuário.
    - **fotoPerfil**: Foto de perfil do usuário.

- **UsuárioHotel**
    - **idUsuarioHotel** (chave primária): Identificador único do usuário administrador do hotel.
    - **nomeEmpresa**: Nome da empresa ou hotel.
    - **enderecoEstabelecimento**: Endereço do hotel.
    - **telefone**: Telefone de contato do hotel.

- **Itinerário**
    - **idItinerario** (chave primária): Identificador único do itinerário.
    - **tituloItinerario**: Título do itinerário.
    - **dataInicio**: Data de início da viagem.
    - **dataFim**: Data de término da viagem.
    - **statusItinerario**: Status do itinerário (ex.: planejado, concluído).
- **Acomodações**
    - **idAcomodacao** (chave primária): Identificador único da acomodação.
    - **tipoAcomodacao**: Tipo da acomodação (quarto, suíte, etc.).
    - **precoDiaria**: Valor da diária.
    - **descricao**: Descrição da acomodação.
    - **fotosAcomodacao**: Lista de fotos da acomodação.

- **Destino**
    - **idDestino** (chave primária): Identificador único do destino.
    - **descricao**: Descrição do destino.
    - **tituloDestino**: Título ou nome do destino.
    - **dataInicialDestino**: Data inicial de interesse pelo destino.
    - **dataFinalDestino**: Data final de interesse pelo destino.
    - **longitudeDestino**: Coordenada de longitude do destino.
    - **latitudeDestino**: Coordenada de latitude do destino.

- **Avaliações**
    - **idAvaliacao** (chave primária): Identificador único da avaliação.
    - **anexoImagem**: Imagem opcional anexada à avaliação.
    - **textoAvaliacao**: Texto escrito pelo usuário para a avaliação.

#### 5.2 DLD - Diagrama Lógico de Dados

A seguir a imagem do Diagrama Lógico de Dados do projeto

![Diagrama Lógico de Dados](./assets/imagemDLD.png)

<center> 

*Fonte: [Pablo Guilherme](https://github.com/PabloGJBS)*

</center>

Descrição do Diagrama Entidade-Relacionamento (DLD)

- **UsuarioHotel**
    - **idUsuarioHotel** (chave primária): Identificador único do usuário administrador do hotel.
    - **idEndereco** (chave estrangeira): Referência ao endereço do hotel.
    - **idTelefone** (chave estrangeira): Referência ao telefone do hotel.
    - **nomeEmpresa**: Nome da empresa ou hotel.

- **enderecoEstabelecimento**
    - **idEnderecoEstabelecimento** (chave primária): Identificador único do endereço.
    - **campoEndereco**: Endereço principal.
    - **cepEnderecoEstabelecimento**: CEP do local.
    - **logBairroEnderecoEstabelecimento**: Bairro do local.
    - **estadoEnderecoEstabelecimento**: Estado do local.

- **telefone**
    - **idTelefone** (chave primária): Identificador único do telefone.
    - **telefone**: Número de telefone (campo decimal com 11 dígitos).

- **Acomodacoes**
    - **idAcomodacao** (chave primária): Identificador único da acomodação.
    - **idUsuarioHotel** (chave estrangeira): Referência ao hotel que oferece a acomodação.
    - **idFotosAcomodacoes** (chave estrangeira): Referência às fotos da acomodação.
    - **precoDiaria**: Preço da diária da acomodação.
    - **descricao**: Descrição da acomodação.

- **fotosAcomodacao**
    - **idFotosAcomodacao** (chave primária): Identificador único da foto.
    - **fotosAcomodacao**: Caminho ou URL da foto.
    - **dataFoto**: Data em que a foto foi registrada.

- **Destino**
    - **idDestino** (chave primária): Identificador único do destino.
    - **idAcomodacao** (chave estrangeira): Referência à acomodação relacionada.
    - **dataInicialDestino**: Data de início da viagem para o destino.
    - **dataFinalDestino**: Data de término da viagem para o destino.
    - **descricao**: Descrição do destino.
    - **tituloDestino**: Título ou nome do destino.
    - **longitudeDestino**: Coordenada de longitude.
    - **latitudeDestino**: Coordenada de latitude.

- **Avaliacoes**
    - **idAvaliacao** (chave primária): Identificador único da avaliação.
    - **idUsuario** (chave estrangeira): Referência ao usuário que realizou a avaliação.
    - **textoAvaliacao**: Texto escrito da avaliação.
    - **anexoImagem**: Caminho da imagem anexa à avaliação.

- **Usuario**
    - **idUsuario** (chave primária): Identificador único do usuário.
    - **nome**: Nome do usuário.
    - **email**: E-mail do usuário.
    - **senha**: Senha do usuário.
    - **dataCriacao**: Data de criação do usuário.

- **Perfil**
    - **idPerfil** (chave primária): Identificador único do perfil.
    - **idPreferenciasViagem** (chave estrangeira): Referência às preferências de viagem.
    - **bioPerfil**: Texto descritivo sobre o usuário.
    - **fotoPerfil**: Caminho da foto de perfil do usuário.

- **preferenciasViagem**
    - **idPreferenciasViagem** (chave primária): Identificador único da preferência de viagem.
    - **preferenciasViagem**: Preferência de viagem (ex.: aventura, praia, cultura, etc.).

- **Itinerario**
    - **idItinerario** (chave primária): Identificador único do itinerário.
    - **tituloItinerario**: Título do itinerário criado.
    - **dataInicio**: Data de início da viagem.
    - **dataFim**: Data de término da viagem.


### 6. Tamanho e Desempenho

O sistema *Vai Pela Sombra* é uma aplicação Web desenvolvida para auxiliar no planejamento de viagens, oferecendo funcionalidades como cadastro de interesses, criação de itinerários personalizados, recomendações de destinos, eventos locais e planejamento em grupo. Espera-se que a aplicação seja acessada por usuários diversos, com picos de uso concentrados em períodos de férias e feriados.

Como o sistema é dividido em microserviços, é possível ajustar o dimensionamento de cada componente de forma independente. Por exemplo, o microserviço de usuários tende a ter menor volume de dados e requisições, enquanto os microserviços de itinerários e grupos de viagem podem crescer consideravelmente conforme a base de usuários aumenta e mais viagens são planejadas.

Durante o período inicial de adoção, é viável hospedar a aplicação em plataformas de cloud mais simples (como o Railway ou o Render). No entanto, à medida que a aplicação cresce e atinge um público maior, recomenda-se a adoção de soluções mais robustas, como AWS, Google Cloud ou Azure, para garantir alta disponibilidade, desempenho e escalabilidade.

A arquitetura também considera o desempenho em dispositivos com recursos limitados. O frontend em React foi projetado de forma responsiva, com carregamento assíncrono de dados, para garantir uma boa experiência mesmo em conexões de internet mais lentas.

### 7. Qualidade

A adoção da arquitetura de microserviços no projeto *Vai Pela Sombra* permite estabelecer metas claras de qualidade técnica, como:

- **Escalabilidade**: cada microserviço pode ser escalado de forma independente, otimizando o uso de recursos conforme a demanda.
- **Facilidade de manutenção**: a separação dos módulos facilita a identificação e correção de erros, bem como a implementação de melhorias.
- **Evolução contínua**: a estrutura modular permite a adição de novas funcionalidades sem impactar o sistema como um todo.
- **Reaproveitamento de código**: componentes comuns podem ser reutilizados entre serviços ou até mesmo em outros projetos.
- **Testabilidade**: com serviços menores e independentes, é possível aplicar testes unitários, de integração e de contrato de forma mais eficiente.
- **Entrega contínua**: a arquitetura favorece a integração contínua e entrega contínua (CI/CD), otimizando o processo de deploy e reduzindo o tempo entre desenvolvimento e disponibilização em produção.

Esses aspectos contribuem para a confiabilidade e longevidade da aplicação, tornando-a apta para evoluir conforme as necessidades dos usuários.

### 8 Referências

### Tabela de Versionamento

|Versão|Data|Descrição|Autor(s)|
|---|---|---|---|
|1.0| 25/04| criação inicial do documento de arquitetura|[Pablo Guilherme](https://github.com/PabloGJBS)|
|1.1| 28/04| adicionando diagramas DER, DLD e de Relações e descrições do banco de dados |[Pablo Guilherme](https://github.com/PabloGJBS)|
