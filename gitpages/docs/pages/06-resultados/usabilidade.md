<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Resultados Obtidos | Usabilidade

## Questão 1: As mensagens orientam à solução do problema?

A questão 1 referente ao foco de qualidade “Usabilidade” é referente a completude da descrição das mensagens de erro que um usuário pode receber ao usar as funcionalidades da aplicação, para verificar se as mensagens são significativas e guiam o usuário para uma solução. A métrica usada para medir essa questão consiste na quociente entre o número de funções que descrevem corretamente os erros do software pelo número total de funções.

Rodando a aplicação localmente, a equipe mostra a seguir duas funcionalidades que o usuário tem acesso e que retornam mensagens em caso de erro. A primeira é na tela do usuário escolher a CSA que deseja entrar. O usuário só consegue logar caso a CSA seja selecionada.

<center>
<img src="../assets/mobileAgromart.png"/>
<br />
<spam>Figura 1 - Tela de Seleção da CSA</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

A mensagem que aparece caso se digite o código de uma CSA que não existe é informativa e indica o problema para o usuário. A mensagem é “CSA não encontrada”. Outra funcionalidade analisada foi a de cadastro de um usuário na CSA. Caso o usuário não possa ser cadastrado por algum erro como quebra de critério de aceitação (“senha menor do que 6 caracteres” ou “usuário ou email já cadastrado”), a aplicação sempre retorna a mesma mensagem de erro genérica mostrada na imagem abaixo.

<center>
<img src="../assets/mobileAgromart2.png"/>
<br />
<spam>Figura 2 - Tela de Cadastro do Usuário</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

A equipe só conseguiu descobrir os motivos dos erros ao fazer as requisições via Postman e vendo as respostas das requisições. Por exemplo, na resposta da requisição de cadastro de usuário na imagem abaixo.

<center>
<img src="../assets/PostmanAgromart.png"/>
<br />
<spam>Figura 3 - Erro Requisição para Cadastro do Usuário</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

Foi feita uma tabela com as mensagens de erro presentes no código e se elas orientam ou não o usuário a solução.

| Localização   | Linha | Orienta o usuário a solução |
| ------------- | ----- | --------------------------- |
| src/components/PlanCard/index.tsx | 63 | Não |
| src/pages/AddressForm/index.tsx | 67 | Não |
| src/pages/BillingAddress/index.tsx | 52 | Não |
| src/pages/Cart/index.tsx | 161 | Não |
| src/pages/CreditCardRegister/index.tsx | 212 | Não |
| src/pages/History/index.tsx | 83 | Não |
| src/pages/Home/index.tsx | 93 | Não |
| src/pages/Notifications/index.tsx | 35 | Não |
| src/pages/Plan/index.tsx | 73 | Não |
| src/pages/ProductPage/index.tsx | 76 | Sim |
| src/pages/ProfileInfo/index.tsx | 33 | Não |
| src/pages/SelectCSA/index.tsx | 53 | Sim |
| src/pages/SignIn/index.tsx | 73 | Não |
| src/pages/SignUp/index.tsx | 51 | Não |
| src/pages/StoreDetails/index.tsx | 209 |  Sim |
| src/pages/StoreDetails/index.tsx | 214 | Sim |
| src/pages/StoreDetails/index.tsx | 276 | Sim |


Com base nas funcionalidades apresentadas, o valor do quociente entre o número de funções que descrevem corretamente os erros do software pelo número total de funções é 5/17 (aproximadamente 29,41%). O valor da métrica está bem abaixo do esperado, que era 90%, e embora a equipe só tenha tido acesso a uma pequena amostra de funcionalidades essas funcionalidades são bem importantes para os usuários. 
Portanto, para melhorar a experiência do usuário, é fundamental substituir mensagens genéricas por mensagens claras e úteis. Uma sugestão da equipe para solucionar esse problema é o front-end da aplicação usar as mensagens retornadas pelas respostas às requisições do back-end sempre que possível, garantindo que o usuário receba informações específicas sobre o que ocorreu. Além disso, é importante que essas mensagens sejam claras e estejam em português, orientando o usuário sobre como resolver o problema ou qual ação tomar a seguir.
Para resolver esse problema, a equipe desenvolveu uma implementação parcial de código na tela de atualizar dados para demonstrar a ideia sugerida. As alterações no código são mostradas na imagem abaixo.

<center>
<img src="../assets/resolucao1.png"/>
<br />
<spam>Figura 4 - Implementação Parcial de Código para Resolver Problema das Mensagens de Erro Genéricas</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

O resultado é mostrado na foto abaixo, onde a mensagem de erro gerada pela api é mostrada para o usuário, indicando a causa do erro (no caso da foto, é que o nome de usuário para o qual se deseja trocar já está em uso por outro usuário).

<center>
<img src="../assets/resultado1.png"/>
<br />
<spam>Figura 5 - Demonstração de Mostrar Mensagens de Erro Informativas para o Usuário</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

## Conclusão:

Fica evidente, portanto, que durante a execução dos testes realizados, principalmente nas etapas de configuração e autenticação do Agromart, enfrentamos situações em que as mensagens retornadas pelo sistema não foram claras para indicar a causa real dos problemas, dificultando a identificação de erros como o cadastramento de um novo usuário na plataforma. Assim como observado nas mensagens de erro genéricas analisadas nesta questão de usabilidade, notamos que, em diversos momentos, foi necessário recorrer a ferramentas externas como o Postman para compreender o que realmente estava ocorrendo, evidenciando a importância de mensagens mais claras e orientativas para melhorar a experiência dos usuários e facilitar a resolução de problemas no uso diário do sistema.

---

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                    | **Autor**                                         |
| ---------- | ---------- | -------------------------------- | ------------------------------------------------- |
| `1.0`      | 05/07/2025 | Criação e estruturação da página | [Daniel Rodrigues](https://github.com/DanielRogs) |
| `1.1`      | 07/07/2025   | Adicionando texto das perguntas e apagando métricas Q2 e Q3 de Usabilidade | [Victório Lázaro](https://github.com/Victor-oss) |
