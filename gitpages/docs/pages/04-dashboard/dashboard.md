<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Dashboard de PSM/CID da Equipe

## Calendário e Processo

## Cumulative Flow | Fluxo Cumulatívo

O Fluxo Cumulativo é uma ferramenta visual para acompanhar o andamento do trabalho em um processo de desenvolvimento contínuo. Através de um gráfico que mostra a quantidade total de itens em cada etapa do fluxo ao longo do tempo, é possível ter uma visão clara do volume de trabalho em progresso, do tempo de ciclo e da taxa de entrega. Esse tipo de representação gráfica permite identificar gargalos, sobrecargas e possíveis desequilíbrios entre o início e a conclusão das tarefas em cada fase.

Em métodos ágeis com foco em entrega contínua de valor, como o Kanban, o controle do fluxo de trabalho é essencial para garantir estabilidade e desempenho previsível. O gráfico de fluxo cumulativo (CFD - Cumulative Flow Diagram) ajuda nesse controle ao revelar se as tarefas estão fluindo de maneira equilibrada entre as etapas. Quando o volume de entrada em uma etapa não acompanha o volume de saída, surgem filas ou atrasos que afetam a eficiência da equipe. Manter um fluxo estável, onde a entrada e a saída de trabalho são proporcionais, é um dos princípios para alcançar processos eficientes e sustentáveis.

### Parâmetros:

**1. A fazer:** Atividades do backlog do produto que foram aprovados/aceitos para implementação (comprometidos com), mas ainda não foram iniciados. Em geral, eles foram atribuídos a uma iteração ou versão.

**2. Em andamento:** Atividades que começaram a ser desenvolvidos.

**3. Concluído:** As atividades concluíram todas as atividades de desenvolvimento em uma iteração e estão prontos para liberação interna.

**4. Implantado:** As Atividades concluíram todas as atividades de desenvolvimento definidas pelo processo, incluindo atividades de integração e teste, e foram implantados em uma versão interna ou externa.

### Cumulative Flow da equipe Radia Perlman

<canvas id="myChart" width="400" height="200"></canvas>

<script src="https://cdn.jsdelivr.net/npm/chart.js"></script>
<script>
  // Função para gerar as datas no formato DD/MM/AAAA
  function gerarDatas(inicio, fim) {
    const datas = [];
    let atual = new Date(inicio);
    const dataFim = new Date(fim);
    while (atual <= dataFim) {
      const dia = String(atual.getDate()).padStart(2, '0');
      const mes = String(atual.getMonth() + 1).padStart(2, '0');
      const ano = atual.getFullYear();
      datas.push(`${dia}/${mes}/${ano}`);
      atual.setDate(atual.getDate() + 1);
    }
    return datas;
  }
  // Data de início e data atual
  const labels = gerarDatas('2025-06-25', new Date());
  const ctx = document.getElementById('myChart').getContext('2d');
  const myChart = new Chart(ctx, {
      type: 'line',
      data: {
          labels: labels,
          datasets: [{
              label: 'Implantado',
              data: [0, 0, 0, 0],
              borderColor: 'rgb(20, 8, 128)',
              backgroundColor: 'rgba(20, 8, 128, 0.74)',
              fill: true
          }, {
              label: 'Completo',
              data: [0, 0, 0, 0],
              borderColor: 'rgb(158, 3, 3)',
              backgroundColor: 'rgba(158, 3, 3, 0.74)',
              fill: true
          }, {
              label: 'Em Progresso',
              data: [0, 3, 3, 3],
              borderColor: 'rgb(182, 194, 75)',
              backgroundColor: 'rgba(182, 194, 75, 0.74)',
              fill: true
          }, {
              label: 'Para Fazer',
              data: [3, 0, 0, 0],
              borderColor: 'rgb(36, 93, 155)',
              backgroundColor: 'rgba(36, 94, 155, 0.74)',
              fill: true
          }]
      },
    options: {
      responsive: true,
        interaction: {
          mode: 'index',
          intersect: false,
        },
        stacked: true,
        plugins: {
          title: {
            display: true,
            text: 'Cumulative Flow - Radia Perlman'
          }
        },
        scales: {
          x: {
            stacked: true
          },
          y: {
            stacked: true,
            beginAtZero: true
          }
        }
    }
  });
</script>

---

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                    | **Autor**                                                                                         |
| ---------- | ---------- | -------------------------------- | ------------------------------------------------------------------------------------------------- |
| `1.0`      | 28/06/2025 | Criação e estruturação da página | [Daniel Rodrigues](https://github.com/DanielRogs) e [Luan Mateus](https://github.com/luanduartee) |
