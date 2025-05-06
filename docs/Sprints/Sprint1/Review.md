## Quando
Essa sprint se iniciou no dia 28/03/2025 e durou 7 dias terminando dia 04/05/2025 

## Análise do Scrum Master

Essa primeria Sprint foi dedicada ao desenvolvimento do protótipo de Alta Fidelidade com base no Backlog que foi elaborado, a equipe foi dividida em squads menores, para que pudessem focar no desenvolvimento de suas respectivas telas.

## Riscos

<canvas id="myChart" width="600" height="400"></canvas>

## Burndown
Não houve pontuação nessa sprint

## Velocity
Não houve pontuação nessa sprint

## Valor Agregado
Não houve pontuação nessa sprint

## Conhecimento dos Membros

Com base nos dados que foram coletados no ínicio da Sprint1, foi elaborado esse gráfico que ao fim de cada Sprint será adicionado os valores correspondentes a média de conhecimento do time ao fim da Sprint.

<canvas id="myChart2" width="600" height="400"></canvas>

## Histórico de Revisão
| Data | Versão | Descrição | Autor(es)|
|:----:|:------:|:---------:|:--------:|
| 05/05/23 | 1.0 | Adicionando sprint planning, retrospective e review | [Rennan](https://github.com/renannOgomes)|


<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  const ctx = document.getElementById('myChart').getContext('2d');
  const series1 = [15,10];
  const series2 = [9,12];
  const series3 = [2,2];
  const series4 = [8,8];
  const series5 = [10,10];
  const series6 = [12,12];
  const series7 = [20,15];
  const series8 = [6,6];
  const series9 = [8,8];
  const series10 = [6,3];
  const series11 = [0,0];
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['S1', 'S2', 'S3', 'S4', 'S5', 'S6', 'S7', 'S8', 'S9', 'S10'],
      datasets: [
        {
          label: 'Baixa participação em reuniões',
          data: series1,
          borderColor: '#1F77B4',
          fill: false
        },
        {
          label: 'Risco de provas de outras materias atrapalharem os horarios',
          data: series2,
          borderColor: '#FF7F0E',
          fill: false
        },
        {
          label: 'Falta de energia',
          data: series3,
          borderColor: '#2CA02C',
          fill: false
        },
        {
          label: 'Problemas de saúde',
          data: series4,
          borderColor: '#D62728',
          fill: false
        },
        {
          label: 'Risco de trancamento',
          data: series5,
          borderColor: '#9467BD',
          fill: false
        },
        {
          label: 'Problema em Tecnicos (computador queimar etc)',
          data: series6,
          borderColor: '#8C564B',
          fill: false
        },
        {
          label: 'Falta de conhecimento',
          data: series7,
          borderColor: '#E377C2',
          fill: false
        },
        {
          label: 'Problemas pessoais',
          data: series8,
          borderColor: '#7F7F7F',
          fill: false
        },
        {
          label: 'Falta de entrosamento entre o grupo',
          data: series9,
          borderColor: '#BCBD22',
          fill: false
        },
        {
          label: 'Sobrecarga de um grupo especifico',
          data: series10,
          borderColor: '#17BECF',
          fill: false
        },
        {
          label: 'Caos de final de semestre',
          data: series11,
          borderColor: '#FF9896',
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
  const ctx2 = document.getElementById('myChart2').getContext('2d');
  //3,2,3,2,2,2,2,1
  const seriesA = [3];
  const seriesB = [2];
  const seriesC = [3];
  const seriesD = [2];
  const seriesE = [2];
  const seriesF = [2];
  const seriesG = [2];
  const seriesH = [1];
  new Chart(ctx2, {
    type: 'line',
    data: {
      labels: ['S1', 'S2', 'S3', 'S4', 'S5', 'S6', 'S7', 'S8', 'S9', 'S10'],
      datasets: [
        {
          label: 'Git',
          data: seriesA,
          borderColor: '#1F77B4',
          fill: false
        },
        {
          label: 'Node.js',
          data: seriesB,
          borderColor: '#FF7F0E',
          fill: false
        },
        {
          label: 'JavaScript',
          data: seriesC,
          borderColor: '#2CA02C',
          fill: false
        },
        {
          label: 'Banco de Dados',
          data: seriesD,
          borderColor: '#D62728',
          fill: false
        },
        {
          label: 'Figma',
          data: seriesE,
          borderColor: '#9467BD',
          fill: false
        },
        {
          label: 'Scrum/XP',
          data: seriesF,
          borderColor: '#8C564B',
          fill: false
        },
        {
          label: 'Testes automatizados',
          data: seriesG,
          borderColor: '#E377C2',
          fill: false
        },
        {
          label: 'Docker',
          data: seriesH,
          borderColor: '#7F7F7F',
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