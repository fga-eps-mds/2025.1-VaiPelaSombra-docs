# Análise SonarCloud

## Histórico de Revisão
| Data | Versão | Descrição | Autor(es)|
|:----:|:------:|:---------:|:--------:|
| 15/07 | 1.0 | Adicionando Página do Sonar | [Suzane Duarte](https://github.com/suzaneaduarte)|

## Análise de Qualidade de Código – SonarCloud

Esta página apresenta os resultados das análises realizadas com o **SonarCloud** nos repositórios do projeto **Vai Pela Sombra** (frontend e backend). A ferramenta SonarCloud nos permite monitorar a qualidade do código, segurança, cobertura de testes e outros indicadores essenciais para garantir um software mais confiável e sustentável.

---

## Resumo das Métricas

Abaixo estão os principais indicadores extraídos da análise mais recente realizada em **15/07/2025**.

### Frontend (`2025.1-VaiPelaSombra-FrontEnd`)

- **Linhas de código**: 4.4k (TypeScript, CSS)
- **Security**: A (0 issues)
- **Reliability**: C (10 issues)
- **Maintainability**: A (41 clean code points)
- **Hotspots Reviewed**: 0.0%
- **Cobertura de Testes**: 30.3%
- **Duplicações**: 0.0%
- **Status**: ❌ Failed

**Motivo da falha**: A cobertura de testes automatizados está em apenas **30.3%**, abaixo da meta mínima de **80%**, definida como padrão de qualidade pelo SonarCloud. Além disso, há **10 alertas de confiabilidade** (Reliability issues) que precisam ser revisados.

---

### Backend (`2025.1-VaiPelaSombra-BackEnd`)

- **Linhas de código**: 1.9k (TypeScript)
- **Security**: A (0 issues)
- **Reliability**: A (0 issues)
- **Maintainability**: A (28 clean code points)
- **Hotspots Reviewed**: 0.0%
- **Cobertura de Testes**: 64.8%
- **Duplicações**: 0.8%
- **Status**: ❌ Failed

**Motivo da falha**: Embora o backend tenha boas métricas de segurança, confiabilidade e manutenibilidade, a **cobertura de testes ainda está em 64.8%**, abaixo da meta estabelecida de 80%.

---

## Próximas Ações

Para melhorar a qualidade do projeto e alcançar aprovação nas análises do SonarCloud, as seguintes ações foram levantadas pela equipe: 

- **Aumentar a cobertura de testes**:
  - Priorizar testes unitários em componentes críticos.
  - Cobrir fluxos de exceção e bordas.
- **Revisar e corrigir alertas de confiabilidade** no frontend.
- **Revisar hotspots** identificados assim que o SonarCloud disponibilizar mais dados.
---

