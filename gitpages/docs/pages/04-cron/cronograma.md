# Projeção e Cronograma

## Projeção da Avaliação:

Para a execução da avaliação de qualidade do software AgroMart, será necessária a seguinte estrutura de recursos e infraestrutura:

### Infraestrutura

- **Ambiente de Testes:** Será necessário um ambiente controlado, representado pelo repositório [https://github.com/FCTE-Qualidade-de-Software-1/2025-1-T02-RADIA-PERLMAN](https://github.com/FCTE-Qualidade-de-Software-1/2025-1-T02-RADIA-PERLMAN), cujo se encontra separado do ambiente de produção, para a instalação e execução do AgroMart, permitindo a simulação de cenários de uso real para a coleta de métricas de eficiência e usabilidade.
- **Versionamento e Documentação:** O projeto utilizará o GitHub para controle de versão do código e dos artefatos de documentação. A documentação será gerada e publicada utilizando `MkDocs`, conforme a estrutura existente.

### Recursos de Software

- **Aplicação AgroMart:** Acesso a uma versão estável do software para a realização dos testes.
- **Framework Q-Rapids:** Utilização do Q-Rapids para a definição, coleta e análise de métricas de qualidade, conforme detalhado na seção [Q-Rapids](../05-qrapids/qrapids.md).
- **Ferramentas de Coleta de Dados:**
    1. **AgroMart:** Executado Localmente na máquina para permitir a observação de componentes e elementos na interface para usabilidade.
    2. **Insomnia:** Utilizado para simular requisições de usuário ao banco de dados e medir o tempo de resposta desde a Requisição até a Resposta do sistema.
    3. **Função MemoryUsage | JavaScript:** Função nativa da Liguagem JavaScript que permite visualizar o consumo de Memória RSS (Resident Set Size) alocada à processos do sistema.
    4. **Morgan:** Biblioteca adicionada dentro da Linguagem de Programação utilizada no código fonte do AgroMart para permitir a medição de Latência de requisições para a API do sistema.

### Recursos Humanos

- **Equipe de Avaliação:** Composta pelos membros listados em [Home](../../index.md), com responsabilidades distribuídas para cada etapa da avaliação, desde o planejamento até a análise dos resultados.

## Cronograma:

Para garantir uma boa organização e dividir bem as responsabilidades entre os membros, elaboramos um cronograma que distribui as atividades do trabalho final. Cada tarefa conta com responsáveis e prazos claros para finalização. Assim, conseguimos acompanhar o progresso do grupo.

### <center>**Tabela 1:** Cronograma

<div>
  <center>
  <table>
    <thead>
      <tr>
        <th>Atividade</th>
        <th>Autor(es)</th>
        <th>Prazo</th>
        <th>Data de Finalização</th>
      </tr>
    </thead>
    <tbody>
      <tr>
        <td>Estudar sobre Q-Rapids e adicionar resumo sobre esse framework na documentação</td>
        <td>
          <a href="https://github.com/Victor-oss/">Victório Lázaro</a>
        </td>
        <td>26/06/25</td>
        <td>25/06/25</td>
      </tr>
      <tr>
        <td>Definir plano para obter as métricas do Objetivo de Eficiência, usar preferencialmente as métricas do Q-Rapids</td>
        <td><a href="https://github.com/Izarias">Pedro Augusto</a> e <a href="https://github.com/pedrosena21">Pedro Sena</a></td>
        <td>29/06/25</td>
        <td>28/06/25</td>
      </tr>
      <tr>
        <td>Definir plano para obter as métricas do Objetivo de Usabilidade, usar preferencialmente as métricas do Q-Rapids</td>
        <td><a href="https://github.com/DaniloCTM/">Danilo Cesar</a> e <a href="https://github.com/Victor-oss/">Victório Lázaro</a></td>
        <td>29/06/25</td>
        <td>29/06/25</td>
      </tr>
      <tr>
        <td>Definir métricas do PSM/CID e implementar dashboard(s) no git para visualização dessas métricas</td>
        <td><a href="https://github.com/DanielRogs">Daniel Rodrigues</a> e <a href="https://github.com/luanduartee">Luan Mateus</a></td>
        <td>29/06/25</td>
        <td>29/06/25</td>
      </tr>
      <tr>
        <td>Fazer medição das questões de Usabilidade</td>
        <td><a href="https://github.com/Victor-oss/">Victório Lázaro</a>, <a href="https://github.com/DanielRogs">Daniel Rodrigues</a> e <a href="https://github.com/luanduartee">Luan Mateus</a></td>
        <td>07/07/25</td>
        <td>07/07/25</td>
      </tr>
      <tr>
        <td>Fazer medição das Questões de Eficiência</td>
        <td><a href="https://github.com/Izarias">Pedro Augusto</a> e <a href="https://github.com/pedrosena21">Pedro Sena</a></td>
        <td>07/07/25</td>
        <td>07/07/25</td>
      </tr>
      <tr>
        <td>Fazer correções nas documentações após ponto de controle</td>
        <td><a href="https://github.com/luanduartee">Luan Mateus</a></td>
        <td>08/07/25</td>
        <td>08/07/25</td>
      </tr>
    </tbody>
  </table>
  
  <center>
  <div>
    <p>Autor: <a href="https://github.com/Victor-oss" target="_blank">Victório Lázaro</a></p>
  </div>
  </center>
</div>

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                                                                                                                                                                                                                                                  | **Autor**                                        |
| ---------- | ---------- | -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------ |
| `1.0`      | 25/06/2025 | Criação do cronograma                                                                                                                                                                                                                                          | [Victório Lázaro](https://github.com/Victor-oss) |
| `1.1`      | 25/06/2025 | Alteração da primeira atividade do cronograma para ser só um estudo sobre o Q-Rapids; criação das duas tarefas relacionadas a definição das métricas dos objetivos de Eficiência e Usabilidade; criação da tarefa relacionada a definição das métricas PSM/CID | [Victório Lázaro](https://github.com/Victor-oss) |
| `1.2`      | 07/07/2025 | Adição e atribuição das atividades envolvendo as medições das questões de Usabilidade                                                                                                                                                                          | [Victório Lázaro](https://github.com/Victor-oss) |