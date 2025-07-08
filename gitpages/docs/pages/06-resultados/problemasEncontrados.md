<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Problemas Encontrados

Durante o trabalho, a equipe encontrou um problema com o Agromart relacionado à falta de documentação e modificações que devem ser feitas no código para rodar a aplicação localmente. O Agromart é uma aplicação que precisa de 3 repositórios para conseguir rodar localmente e ser possível fazer login. Os repositórios são mobile-client (o front-end), api (back-end) e api-dicionario (parte da arquitetura responsável por guardar a url do back-end de todas as CSAs que estão integradas com o ambiente Agromart, permitindo que o aplicativo se comunique com diferentes APIs). A documentação para executar toda a arquitetura localmente é inexistente, além de terem problemas no código que dificultam essa ação (como o fato da URL para a api-dicionário ser um link fixo no código do front-end e a api desse link nem estar disponível). Devido a esse problema, a equipe desenvolveu um tutorial para rodar a aplicação localmente e disponibilizou esse tutorial no [Github da equipe](https://fcte-qualidade-de-software-1.github.io/2025-1-T02-RADIA-PERLMAN/pages/08-agromart-local/agromart-local/).

Esse tutorial é importante porque uma documentação clara e objetiva sobre como rodar um sistema open-source é essencial para garantir que outros desenvolvedores consigam contribuir, testar ou usar o projeto com facilidade. Sem instruções precisas, o tempo gasto tentando entender como o projeto funciona pode desmotivar colaboradores e dificultar sua adoção. Uma boa documentação torna o projeto mais acessível e colaborativo, ajudando a construir uma comunidade ativa em torno dele.

Também foram encontrados problemas através das análises feitas sobre as métricas definidas para o trabalho, sendo um deles a alta latência para requisições feitas para a api, mais precisamente, de tempo superior a 4000ms, provando a necessidade de melhorias no banco de dados e na aplicação pela equipe do agromart para que solucione o problema.


---

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                    | **Autor**                                         |
| ---------- | ---------- | -------------------------------- | ------------------------------------------------- |
| `1.0`      | 05/07/2025 | Criação e estruturação da página | [Daniel Rodrigues](https://github.com/DanielRogs) |
| `1.1`      | 08/07/2025 | Adição de problema encontrado | [Pedro Izarias](https://github.com/Izarias) |
