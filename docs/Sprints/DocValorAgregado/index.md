# Gráfico de Valor Agregado

# Histórico de Versões 
|Versão|Data|Descrição|Autor(s)|
|---|---|---|---|
|1.0| 01/05 | Criação da pagina e gráfico de valor agregado |[Rennan](https://github.com/renannOgomes)|s

## Acompanhamento de Valor Agregado

### 1. Introdução

O cálculo de Valor Agregado (Earned Value) é uma técnica de gestão de projetos usada para medir o desempenho e o progresso de um projeto. Ele combina escopo, cronograma e custos para fornecer uma visão clara de como o projeto está avançando em relação ao planejado.

As três principais métricas usadas no cálculo de Valor Agregado são:

**Planned Value (PV) (Valor Planejado):**
Representa o valor do trabalho planejado para ser concluído até um determinado momento. É o orçamento alocado para as tarefas programadas no cronograma.
Fórmula:
PV = % planejado do trabalho x orçamento total

Com base na classificação feita na etapa "Sequenciador" do Lean Inception, se somados todos os valores de Negócio + UX + Esforço, temos um orçamento total de:


**Actual Value (AV) (Valor Real):**
Representa o custo real do trabalho realizado até o momento. É o valor efetivamente gasto no projeto.
Fórmula:
AV = soma dos custos reais incorridos

**Earned Value (EV) (Valor Agregado):**
Representa o valor do trabalho realmente concluído até o momento, com base no orçamento planejado. Ele mede o progresso real em termos financeiros.
Fórmula:
EV = % concluído do trabalho x orçamento total

Essas métricas permitem calcular indicadores como CPI (Índice de Desempenho de Custo) e SPI (Índice de Desempenho de Cronograma), que ajudam a avaliar se o projeto está dentro do orçamento e do cronograma.

### 1.2. CPI e SPI 
O CPI (Cost Performance Index) e o SPI (Schedule Performance Index) são indicadores derivados do cálculo de Valor Agregado que ajudam a avaliar o desempenho do projeto em termos de custo e cronograma.

O CPI mede a **eficiência do uso do orçamento no projeto**. Ele indica se o projeto está gastando mais ou menos do que o planejado.

Fórmula:
CPI = EV / AV

- CPI > 1: O projeto está gastando menos do que o planejado (eficiência de custo).
- CPI = 1: O projeto está exatamente dentro do orçamento.
- CPI < 1: O projeto está gastando mais do que o planejado (ineficiência de custo).

O SPI mede a **eficiência do cronograma do projeto**. Ele indica se o projeto está adiantado ou atrasado em relação ao planejado.

Fórmula:
SPI = EV / PV

- SPI > 1: O projeto está adiantado em relação ao cronograma.
- SPI = 1: O projeto está exatamente no cronograma.
- SPI < 1: O projeto está atrasado em relação ao cronograma.

### 2. Definição de Métricas

As métricas que vamos utilizar serão definidas com base nos conceitos de:

**Valor Agregado das Funcionalidades na Sprint:** Cada funcionalidade terá um valor atribuído com base no quanto de **valor ela adiciona para o usuário final (Negócio + UX)**, ao final da Sprint, será realizado uma soma do valor de todas funcionalidades que foram **implementadas**. 

**Custo de Desenvolvimetno das Funcionalidades na Sprint:** Cada funcionalidade terá um valor atribuído a sua **dificuldade de desenvolvimento (Esforço)**, ao final da Sprint, será realizado uma soma de do valor de todas as funcionalidades que estavam em **desenvolvimento**. 

Logo ao fim de cada Sprint, o gráfico será atualizado com os valores, da seguinte forma: 

- EV = EV(da Sprint anterior) + Valor Agregado das Funcionalidades na Sprint
- AC = AC(da Sprint anterior) + Custo de Desenvolvimetno das Funcionalidades na Sprint


### 3. Gráfico de Valor Agregado

<canvas id="myChart" width="600" height="400"></canvas>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  const ctx = document.getElementById('myChart').getContext('2d');
  const orçamentoTotal = 133;
  const valuesPlannedValues = [18, 19, 15, 10, 19, 11, 12, 12, 9, 8];
  let cumulativeSum = 0;
  const plannedValues = valuesPlannedValues.map(item => {
    cumulativeSum += (item/orçamentoTotal) *100;
    return cumulativeSum
  });
  const valuesActualValue = [0, 10]; //Adicione itens aqui Valor GASTO em cada Sprint /Add esforço 
  cumulativeSum = 0;
  const actualValues = valuesActualValue.map(item => {
    cumulativeSum += (item/orçamentoTotal) *100;
    return cumulativeSum
  });
  const valuesEarnedValue = [0, 0]; //Adicione itens aqui Valor GANHO em cada Sprint /Add Esforço + Ux + Negócio
  cumulativeSum = 0;
  const earnedValues = valuesEarnedValue.map(item => {
    cumulativeSum += (item/orçamentoTotal) *100;
    return cumulativeSum
  });
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['S1', 'S2', 'S3', 'S4', 'S5', 'S6', 'S7', 'S8', 'S9', 'S10'],
      datasets: [
        {
          label: 'PV - Planned Value',
          data: plannedValues,
          borderColor: '#283841',
          fill: false
        },
        {
          label: 'AV - Actual Value',
          data: actualValues,
          borderColor: '#426499',
          fill: false
        },
        {
          label: 'EA - Earned Value',
          data: earnedValues,
          borderColor: '#C08B7D',
          fill: false
        }
      ]
    },
    options: {
      responsive: true,
      plugins: {
        legend: {
          position: 'top'
        }
      },
      scales: {
        y: {
          beginAtZero: true
        }
      }
    }
  });
</script>

# Referências
>[1] CASTRO, António Agostinho Freitas. Estudo da utilização do EVM em ambientes ágeis. 2022. Tese de Doutorado. Acesso em: 01 de maio de 2025
