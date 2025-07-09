<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Resultados Obtidos | Eficiência

## Questão 1: O tempo de resposta do sistema é adequado para operações de edição e exclusão?

Para a questão 1, que aborda a eficiência, avaliamos a velocidade de resposta do sistema às operações de criação pelo usuário, medida em milissegundos. Especificamente, o endpoint de criação de CSA foi o escolhida para essa análise, apresentando uma latência de 5658,968 ms.


<center>
<img src="../assets/LatenciaAgromart.png"/>
<br />
<spam>Figura 1 - Teste de Inserção do Dado com Exibição da Latência do Processo</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

A latência registrada para o endpoint de criação de CSA é, sem dúvida, uma preocupação significativa sob o ponto de vista da eficiência e da experiência do usuário. Um tempo de resposta superior a cinco segundos não apenas compromete severamente a satisfação do usuário, que pode abandonar a operação por frustração, mas também indica a presença de gargalos críticos na arquitetura ou implementação da aplicação, que podem incluir desde consultas lentas ao banco de dados até complexidades excessivas na lógica de negócios ou dependências externas ineficientes.

Dessa forma, podemos concluir que a hipótese de baseline "Existem requisições que tiveram um tempo de resposta superior a 4000ms?" se confirma, tornando-se necessário incluir otimizações no banco de dados, como criação de índices ou reestruturação de queries e melhorias no código da aplicação para reduzir complexidade ou chamadas desnecessárias.

## Questão 2: O sistema realiza consultas ao banco de dados de forma eficiente?

A questão 2 aborda otimização das consultas ao banco de dados, que não só é crucial para o consumo adequado de recursos computacionais e financeiros, mas também para a satisfação do usuário. 

Executando a api-dicionario localmente e buscando pelas csas, registramos um tempo de execução de 25.111 ms. 

<center>
<img src="../assets/Consulta_all_csa.png"/>
<br />
<spam>Figura 2 - Consulta de CSAs no banco de dados</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

### Índices

A api tem uma grande quantidade de índices, ajudando na realização das consultas:

<center>
<img src="../assets/ExemploConsulta.png"/>
<br />
<spam>Figura 3 - Quantidade de índices da <b>api</b> descrito em "Count"</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>


Já os de índices do api-dicionario tem apenas dois índices, e apenas um deles serve para a consulta de CSAs pela chave primária, o que pode causar buscas sequenciais na tabela caso outros atributos sejam usados para fazer a busca:

<center>
<img src="../assets/ExemploConsulta2.png"/>
<br />
<spam>Figura 4 - Quantidade de índices da <b>api-dicionario</b> descrito em "Count"</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

Dessa forma, apesar de ainda possibilitar algumas melhorias, podemos concluir que a hipótese "95% de todas as consultas disponíveis são retornadas em até 5000ms" é correta, atestando uma eficiência mínima que permite que o usuário realize ações no sistema sem maiores empecilhos.


## Questão 3: O sistema de cadastro é eficiente na gestão de recursos de memória?

A questão 3 está relacionada à variação percentual do uso da memória RAM durante a operação de cadastro pelo usuário. Usando como base uma máquina equipada com 1 GB de memória, permitindo uma análise que abrange tanto cenários de memória limitada quanto de alta disponibilidade, tornando os resultados mais representativos. Já os dados foram obtidos através do uso da endpoint de cadastro de CSA, onde constatamos o uso líquido de memória e consequentemente sua variação percentual. 

<center>
<img src="../assets/UsoMemoria.png"/>
<br />
<spam>Figura 5 - Uso de Memória pela endpoint de cadastro de CSA</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

A variação percentual do uso de memória RAM que ocorreu durante essa requisição, considerando um computador com 1 GB de RAM, é de aproximadamente 0.084% se considerarmos a memória física que o processo está usando (rss). Dessa maneira, podemos afirmar positivamente à questão relacionada que diz: O sistema de cadastro é eficiente na gestão de recursos de memória?
Quanto a hipótese relacionada a esse métrica específica, que diz: O uso médio da memória RAM utilizada permanece com variação inferior a 10% ao tratar uma requisição, foi confirmada com a análise da endpoint supracitada com margem suficientemente grande para que o usuário não tenha qualquer dificuldade quando realizadas tarefas desse tipo.


---

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                    | **Autor**                                         |
| ---------- | ---------- | -------------------------------- | ------------------------------------------------- |
| `1.0`      | 05/07/2025 | Criação e estruturação da página | [Daniel Rodrigues](https://github.com/DanielRogs) |
| `1.1`      | 07/07/2025 | Análise das métricas de eficiência e escrita do texto | [Pedro Izarias](https://github.com/Izarias), [Pedro Sena](https://github.com/pedrosena21) |
| `1.2`      | 07/07/2025   | Adicionando texto das perguntas    | [Victório Lázaro](https://github.com/Victor-oss) |
