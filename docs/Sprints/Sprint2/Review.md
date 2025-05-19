# Review 

## Quando
Essa sprint se iniciou no dia 05/05/2025 e durou 7 dias terminando dia 12/05/2025 

## Análise do Scrum Master

Nessa Sprint foi o inicio do desenvolvimento técnico do projeto, foram escolhidas 2 US principais, sendo que essas duas US foram dividas em duas "partes": desenvolvimento FrontEnd e BackEnd, cada parte ficou para um time, que seria responsável por desenvolver e realizar o PR, contudo devido ao atraso na entrega de algumas demandas da Sprint 1 alguns times tiveram que se reorganizar para entregar o planejado, uma das medidas que foram tomadas visando "dar mais tempo" foi reagendar a reunião de Planning/Review de Segunda-feira, para toda Terça-feira. 

## Riscos

<canvas id="myChart" width="600" height="400"></canvas>

## Burndown
Não houve pontuação nessa sprint

## Velocity
Não houve pontuação nessa sprint

## Valor Agregado
Não houve pontuação nessa sprint

## Conhecimento dos Membros

Ao fim da Sprint 2 fizemos um questionário para levantar os dados relacionados a evolução do conhecimento técnico da equipe e incrementamos a média das respostas no gráfico a baixo. 

<canvas id="myChart2" width="600" height="400"></canvas>

## Histórico de Revisão
| Data | Versão | Descrição | Autor(es)|
|:----:|:------:|:---------:|:--------:|
| 14/05/23 | 1.0 | Adicionando sprint planning, retrospective e review da Sprint2| [Rennan](https://github.com/renannOgomes)|


<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  const ctx = document.getElementById('myChart').getContext('2d');
  const seriesBaixaPar = [15,10, 5];
  const seriesRiscoProva = [9,12,12];
  const seriesFaltaEnergia = [2,2,2];
  const seriesProblemasSaude = [8,8,4];
  const seriesRiscoTranc = [10,10,10];
  const seriesProblemaTec = [12,12,4];
  const seriesFaltaConhec = [20,15,16];
  const seriesProblemaPessoal = [6,6,6];
  const seriesFaltaDeEntro = [8,8,8];
  const seriesSobrecarga = [6,3,3];
  const seriesCaosFinal = [0,0,0];
  const seriesNaoGerarDeploy = [0,0,15];
  const seriesSobrecargaEspec = [0,0,12];
  new Chart(ctx, {
    type: 'line',
    data: {
      labels: ['S1', 'S2', 'S3', 'S4', 'S5', 'S6', 'S7', 'S8', 'S9', 'S10'],
      datasets: [
        {
          label: 'Baixa participação em reuniões',
          data: seriesBaixaPar,
          borderColor: '#1F77B4',
          fill: false
        },
        {
          label: 'Risco de provas de outras materias atrapalharem os horarios',
          data: seriesRiscoProva,
          borderColor: '#FF7F0E',
          fill: false
        },
        {
          label: 'Falta de energia',
          data: seriesFaltaEnergia,
          borderColor: '#2CA02C',
          fill: false
        },
        {
          label: 'Problemas de saúde',
          data: seriesProblemasSaude,
          borderColor: '#D62728',
          fill: false
        },
        {
          label: 'Risco de trancamento',
          data: seriesRiscoTranc,
          borderColor: '#9467BD',
          fill: false
        },
        {
          label: 'Problema em Tecnicos (computador queimar etc)',
          data: seriesProblemaTec,
          borderColor: '#8C564B',
          fill: false
        },
        {
          label: 'Falta de conhecimento',
          data: seriesFaltaConhec,
          borderColor: '#E377C2',
          fill: false
        },
        {
          label: 'Problemas pessoais',
          data: seriesProblemaPessoal,
          borderColor: '#7F7F7F',
          fill: false
        },
        {
          label: 'Falta de entrosamento entre o grupo',
          data: seriesFaltaDeEntro,
          borderColor: '#BCBD22',
          fill: false
        },
        {
          label: 'Sobrecarga de um grupo especifico',
          data: seriesSobrecarga,
          borderColor: '#17BECF',
          fill: false
        },
        {
          label: 'Caos de final de semestre',
          data: seriesCaosFinal,
          borderColor: '#FF9896',
          fill: false
        },
        {
          label: 'Não Conseguir gerar Deploy',
          data: seriesNaoGerarDeploy,
          borderColor: '#17BECF',
          fill: false
        },
        {
          label: 'Sobrecarga de membros especificos ',
          data: seriesSobrecargaEspec,
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
  //TABELA DE MÉDIA DE CONHECIMENTOS!!
  const ctx2 = document.getElementById('myChart2').getContext('2d');
  const seriesGit = [3, 3];
  const seriesNode = [2, 2];
  const seriesTypeScript = [3,3];
  const seriesBancoDados = [2, 2];
  const seriesFigma = [2, 3];
  const seriesScrumXP = [2, 3];
  const seriesTestes = [2, 2];
  const seriesDocker = [1, 2];
  const seriesReact = [1, 2];
  new Chart(ctx2, {
    type: 'line',
    data: {
      labels: ['S1', 'S2', 'S3', 'S4', 'S5', 'S6', 'S7', 'S8', 'S9', 'S10'],
      datasets: [
        {
          label: 'Git',
          data: seriesGit,
          borderColor: '#1F77B4',
          fill: false
        },
        {
          label: 'Node.js',
          data: seriesNode,
          borderColor: '#FF7F0E',
          fill: false
        },
        {
          label: 'TypeScript',
          data: seriesTypeScript,
          borderColor: '#2CA02C',
          fill: false
        },
        {
          label: 'Banco de Dados',
          data: seriesBancoDados,
          borderColor: '#D62728',
          fill: false
        },
        {
          label: 'Figma',
          data: seriesFigma,
          borderColor: '#9467BD',
          fill: false
        },
        {
          label: 'Scrum/XP',
          data: seriesScrumXP,
          borderColor: '#8C564B',
          fill: false
        },
        {
          label: 'Testes automatizados',
          data: seriesTestes,
          borderColor: '#E377C2',
          fill: false
        },
        {
          label: 'Docker',
          data: seriesDocker,
          borderColor: '#7F7F7F',
          fill: false
        },
        {
          label: 'React',
          data: seriesReact,
          borderColor: '#e33636',
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