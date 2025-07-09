<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.1</span>

# Abstraction Sheet:

## Abstraction sheet do Objetivo de Medição 1

<table>
  <tr>
    <th>Objeto</th>
    <th>Propósito</th>
    <th>Foco da Qualidade</th>
    <th>Ponto de Vista</th>
  </tr>
  <tr>
    <td>Proteção contra erros do usuário</td>
    <td>Avaliar</td>
    <td>Usabilidade</td>
    <td>Equipe de Desenvolvimento</td>
  </tr>
  <tr>
    <th colspan="2">Foco da Qualidade</th>
    <th colspan="2">Fatores de Variação</th>
  </tr>
  <tr>
    <td colspan="2">
        <ul>
            <li>Usabilidade</li>
            <li>Funcionalidade</li>
            <li>Confiabilidade</li>
            <li>Portabilidade</li>
            <li>Eficiência</li>
            <li>Completitude</li>
        </ul>
    </td>
    <td colspan="2">
        <ul>
            <li>Nível de alfabetização do usuário</li>
            <li>Clareza das mensages do sistema (Uso de imagens, ícones, descrição)</li>
            <li>Visibilidade de status do sistema</li>
        </ul>
    </td>
  </tr>
    <tr>
    <th colspan="2">Hipóteses de Baseline</th>
    <th colspan="2">Impacto nas hipóteses de baseline</th>
  </tr>
  <tr>
    <td colspan="2">
        <ul>
            <li>90% das mensagens de erro possíveis descrevem de forma coerente o real motivo do erro, no mínimo</li>
            <li>Pelo menos 90% das mensagens de erro não mencionam termos relacionados ao funcionamento interno do sistema</li>
            <li>Pelo menos 90% das mensagens de erro não mencionam termos relacionados ao funcionamento interno do sistema</li>
        </ul>
    </td>
    <td colspan="2">
        <ul>
            <p>Caso a disposição de informações do AgroMart não seja acessível ou não apresentem uma linguagem compreensível, afetará em:</p>
            <li>Capacidade de identificar o motivo da falha.</li>
            <li>Compreensão de como corrigir a falha</li>
            <li>Capacidade de consultar instruções previamente elaboradas</li>
        </ul>
    </td>
  </tr>
</table>

#### Relação entre Objetivos, Questões e Métricas - Usabilidade

![Métricas Usabilidade](./assets/metricas2.png)

## Abstraction sheet do Objetivo de Medição 2

<table>
  <tr>
    <th>Objeto</th>
    <th>Propósito</th>
    <th>Foco da Qualidade</th>
    <th>Ponto de Vista</th>
  </tr>
  <tr>
    <td>Interface Web do Produtor</td>
    <td>Avaliar</td>
    <td>Eficiência</td>
    <td>Equipe de Desenvolvimento</td>
  </tr>
  <tr>
    <th colspan="2">Foco da Qualidade</th>
    <th colspan="2">Fatores de Variação</th>
  </tr>
  <tr>
    <td colspan="2">
        <ul>
            <li>Eficiência</li>
            <li>Usabilidade</li>
            <li>Funcionalidade</li>
            <li>Confiabilidade</li>
            <li>Portabilidade</li>
            <li>Completitude</li>
        </ul>
    </td>
    <td colspan="2">
        <ul>
            <li>Uso de recursos de hardware</li>
            <li>Velocidade de processamento do sistema</li>
            <li>Hardware utilizado pelo usuário</li>
        </ul>
    </td>
  </tr>
    <tr>
    <th colspan="2">Hipóteses de Baseline</th>
    <th colspan="2">Impacto nas hipóteses de baseline</th>
  </tr>
  <tr>
    <td colspan="2">
        <ul>
            <li>Existem requisições que tiveram um tempo de resposta superior a 4000ms</li>
            <li>95% de todas as consultas disponíveis são retornadas em até 5000ms</li>
            <li>O uso médio da memória RAM utilizada permanece com variação inferior a 10% ao tratar uma requisição</li>
        </ul>
    </td>
    <td colspan="2">
        <ul>
            <p>Se o sistema não for eficiente em uso de infraestrutura e for lento, pode ocasionar em:  </p>
            <li>Frustração por parte do produtor ao executar operações simples de criação </li>
            <li>Falha causadora de morte do processo da aplicação</li>
        </ul>
    </td>
  </tr>
</table>

<br/>

#### Relação entre Objetivos, Questões e Métricas - Eficiência

![Métricas Eficiência](./assets/metricas.png)

---

**Histórico de Versões**

| **Versão** | **Data**     | **Descrição**                     | **Autor**                                         |
|------------|--------------|-----------------------------------|---------------------------------------------------|
| `1.0`      | 03/06/2025   | Reorganização dos Conteúdo GQM    | [Daniel Rodrigues](https://github.com/DanielRogs) |
| `1.1`      | 07/07/2025   | Apagando métricas Q2 e Q3 de Usabilidade    | [Victório Lázaro](https://github.com/Victor-oss) |
| `1.2`      | 08/07/2025   | Criação do diagrama de eficiência    | [Pedro Izarias](https://github.com/Izarias) |
