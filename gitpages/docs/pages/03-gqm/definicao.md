<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.1</span>

# Plano de Medição

## Objetivo de Medição 1 - Verificar usabilidade do AGROMART

| **Analisar** | AgroMart |
| --- | --- |
| **Para o propósito de** | Avaliar |
| **Com respeito a** | Usabilidade |
| **Do ponto de vista do/a** | Equipe de Desenvolvimento |
| **No contexto de** | Qualidade de Software 1 |

### Questões e Hipóteses:

| Questão (Q)                             | Hipótese Associada                                                 |
| --------------------------------------- | ------------------------------------------------------------------ |
| **Q1:** As mensagens orientam à solução do problema?     | 90% das mensagens de erro possíveis descrevem de forma coerente o real motivo do erro, no mínimo.                     |

### Métricas

| Métrica (M) | Descrição | Critérios  | Foco da Medição
| ------------------------------------------------------ | --------------- | ------------------------------------------------------------------------------------------- | ------------- |
| **M1:** Completude de Descrição de Mensagens  | Pertence à métrica de Usabilidade e seu objetivo é determinar a taxa de funcionalidades que apresentam uma resposta que, de fato, guie o usuário a uma solução em casos de erros. | A = Número de Funções que descrevem corretamente os erros do software. <br> B = Número Total de Funções  | Externo/Interno 

<br/><br/>

---

## Objetivo de medição 2 - Verificar eficiência do AGROMART

| **Analisar** | AgroMart |
| --- | --- |
| **Para o propósito de** | Avaliar |
| **Com respeito a** | Eficiência |
| **Do ponto de vista do/a** | Equipe de Desenvolvimento |
| **No contexto de** | Qualidade Software 1 |

### Questões e Hipóteses:

| Questão (Q)                             | Hipótese Associada                                                 |
| --------------------------------------- | ------------------------------------------------------------------ |
| **Q1:** O tempo de resposta do sistema é adequado para operações de edição e exclusão?     | 80% das requisições tiveram um tempo de resposta inferior a 100ms.                     |
| **Q2.** O sistema realiza consultas ao banco de dados de forma eficiente? | 95% de todas as consultas disponíveis são retornadas em até 150ms.                  |
| **Q3.** O sistema de cadastro é eficiente na gestão de recursos de memória?      | O uso médio da memória RAM utilizada permanece com variação inferior a 10% ao tratar uma requisição. |

### Métricas

| Métrica (M) | Descrição | Elementos de Medição | Foco da Medição |
| ----------- | --------- | -------------------- | --------------- |
| **M1:** Tempo de resposta (latência) por requisição (ms) | Determina o tempo de resposta por requisição em milissegundos, avaliando a eficiência do sistema. | T = Tempo de execução em milissegundos (ms) | Externo/Interno |
| **M2:** Tempo de execução da consulta SQL (ms) | Mede o tempo decorrido durante uma consulta ao banco de dados realizada pelo sistema. | T = Tempo de execução em milissegundos (ms) | Externo/Interno |
| **M3:** Variação percentual do uso de memória | Avalia a variação no uso de memória RAM pelo sistema ao processar uma requisição. | M₁ = Memória antes (MB)<br>M₂ = Memória depois (MB)<br>ΔM% = ((M₂ - M₁) / M₁) × 100 | Externo/Interno |

<br/><br/>

---

**Contribuições**

| **Matrícula** | **Nome** | **Atividade realizada** | **% de contribuição** |
| --- | --- | --- | --- |
| 211061583 | Daniel Rodrigues da Rocha | Desenvolvimento dos Objetivos, Questões, diagramas e parcialmente o abstraction sheet | 16,6 |
| 221031149 | Danilo César Tertuliano Melo | Atualização nas métricas do objetivo 2; aplicação de formatação | 16,6 |
| 211041221 | Luan Mateus Cesar Duarte | Elaboração parcial dos fatores de qualidade, fatores de variação e impacto nas hipóteses de baseline do abstraction sheet | 16,6 |
| 200062620 | Pedro Augusto Dourado Izarias | Elaboração parcial das questões, hipóteses, métricas e atualização do diagrama relacionado | 16,6 |
| 211029540 | Pedro Sena Barbosa Holtz Yen | Elaboração parcial das questões, hipóteses e métricas das medições de Usabilidade e Eficiência | 16,6 |
| 211031860 | Victório Lázaro Rocha de Morais | Adição da questão 4 do objetivo 1 e sua hipótese; edição da imagem do objetivo 1 | 16,6 |

---

**Histórico de Versões**

| **Versão** | **Data**     | **Descrição**                     | **Autor**                                         |
|------------|--------------|-----------------------------------|---------------------------------------------------|
| `1.0`      | 02/06/2025   | Criação e estruturação da página  | [Luan Mateus](https://github.com/luanduartee)     |
| `1.1`      | 03/06/2025   | Reorganização dos Conteúdo GQM    | [Daniel Rodrigues](https://github.com/DanielRogs) |
| `1.2`      | 07/07/2025   | Apagando métricas Q2 e Q3 de Usabilidade e arrumando texto da Q1    | [Victório Lázaro](https://github.com/Victor-oss) |
| `1.3`      | 08/07/2025   | Reestruturação e atulização de conteúdos    | [Luan Mateus](https://github.com/luanduartee) |
