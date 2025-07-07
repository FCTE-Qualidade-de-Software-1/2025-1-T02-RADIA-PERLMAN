<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Resultados Obtidos | Usabilidade

## Questão 1:

A questão 1 referente ao foco de qualidade “Usabilidade” é referente a completude da descrição das mensagens de erro que um usuário pode receber ao usar as funcionalidades da aplicação, para verificar se as mensagens são significativas e guiam o usuário para uma solução. A métrica usada para medir essa questão consiste na quociente entre o número de funções que descrevem corretamente os erros do software pelo número total de funções.

Rodando a aplicação localmente, a equipe só conseguiu acesso a três funcionalidades que o usuário tem acesso e que retornam mensagens em caso de erro. A primeira é na tela do usuário escolher a CSA que deseja entrar. O usuário só consegue logar caso a CSA seja selecionada.

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

Outra funcionalidade que apresenta mensagem de erro genérica e que não guia o usuário à solução é a da tela de atualização de dados do usuário, que no caso a operação falhar só apresenta o texto “Não foi possível atualizar seus dados”. Com base nas três funcionalidades apresentadas, o valor do quociente entre o número de funções que descrevem corretamente os erros do software pelo número total de funções é ⅓ (aproximadamente 33,33%) sendo 1 a funcionalidade de seleção da CSA. O valor da métrica está bem abaixo do esperado, que era 90%, e embora a equipe só tenha tido acesso a uma pequena amostra de funcionalidades essas funcionalidades são bem importantes para os usuários. 
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
<spam>Figura 5 - Demonstração de Monstrar Mensagens de Erro Informativas para o Usuário</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>


## Questão 2:
A questão 2, também relacionada à "Usabilidade" busca quantificar a quantidade de erros que podem trazer confusão aos usuários por trazer termos técnicos, isto é, funções, variáveis ou componentes internos do software. A métrica utilizada para responder esta questão está descrita no tópico [Definição do GQM](../03-gqm/definicao.md), chamada **Clareza de Mensagens**, cujo recebe dois parâmetros:

- A = Número de mensagens que são fáceis de entender;
- B = Número total de mensagens.


E o resultado é obtido por:

_Taxa de Clareza de Mensagens do Aplicativo = A/B_

### Análise:
#### Ambiente Agromart-web:

No ambiente "Agromart-Web" foram identificados alguns trechos que trazem ao usuário termos internos do sistema sem declarar, após o erro, o que a mensagem significa. Os trechos podem ser observados em:

- _agromart-web/src/hooks/auth.tsx:_
```typescript
function useAuth(): AuthContextData {
  const context = useContext(AuthContext);

  if(!context){
    throw new Error('useAuth must be used within an AuthProider');
  }

  return context;
}
```

A mensagem de erro presente na linha 95 do Arquivo mencionado não apresenta ao usuário o problema em uma liguagem apropriada, ao invés disso, menciona componentes internos do sistema.

- _agromart-web/src/hooks/notification.tsx:_
```
function useNotifications(): NotificationContextData {
  const context = useContext(NotificationContext);

  if(!context){
    throw new Error('useNotification must be used within an AuthProider');
  }

  return context;
}
```
O mesmo problema do arquivo anterior é cometido em `notification.jsx`, apresentando uma mensagem com termos internos ao sistema e sem promover uma liguagem apropriada ao usuário final.

No ambiente do agromart-web, foram registrados:

- B = 10 Mensagens de Erros/Acertos Totais;
- A = 8 Mensagens de Erros/Acertos que não mencionam termos internos ao software.

#### Ambiente Mobile-Client:

No ambiente "Mobile-Client" também foram identificados alguns trechos que trazem ao usuário termos internos do sistema sem declarar, após o erro, o que a mensagem significa. Os trechos podem ser observados em:

- _mobile-client/src/pages/AdressForm/index.tsx_
```typescript
  const SCHEMA = Yup.object().shape({
    cep: Yup.string().required(),
    city: Yup.string().required(),
    neighborhood: Yup.string().required(),
    street: Yup.string().required(),
    number: Yup.string().required(),
    complement: Yup.string(),
  });
```

O método `Yup` emite ao usuário uma mensagem em sua interface indicando que os campos `cep`, `city`, `neighborhood`, `street`, `number` e `complement` são obrigatórios em caso da ausência destes dados. Contúdo, o desenvolvedor não indicou qual será a mensagem à ser exibida ao usuário. Essa omissão permite que o software exiba, por padrão, mensagens vindos do próprio sistema.

- _mobile-client/src/hooks/AuthProvider.tsx_
```typescript
function useAuth(): AuthContextData {
  const context = useContext(AuthContext);

  if (!context) {
    throw new Error('useAuth must be used within an AuthProvider');
  }

  return context;
}
```

Aqui, o mesmo erro problema obtido no ambiente agromart-web é cometido. O erro na linha 215 no arquivo mencionado exibe na interface do usuário a mensagem _"useAuth must be used within an AuthProvider"_, cujo não utiliza de uma liguagem adequada e faz referências à componentes internos do sistema.

- _mobile-client/src/hooks/CartProvider.jsx_
```typescript
function useCart(): CartContextData {
  const context = useContext(CartContext);

  if (!context) {
    throw new Error('useCart must be used within an CartProvider');
  }

  return context;
}
```

O mesmo erro detalhado anteriormente é feito neste arquivo, na linha 101. A mensagem que é exibida na interface do usuário _"useCart must be used within an CartProvider"_ faz referência à componentes internos do software.

- _mobile-client/src/hooks/StoresProvider.jsx_
```typescript
function useStores(): StoresContextData {
  const context = useContext(StoresContext);

  if (!context) {
    throw new Error('useStores must be used within an StoresProvider');
  }

  return context;
}
```

Mais uma vez, a linha 42 do arquivo exibe a mensagem _"useStores must be used within an StoresProvider"_ em sua interface em caso de erro, cujo utiliza de termos internos do software.

No ambiente Mobile-Client, foram registrados:

- B = 28 Mensagens de Erros/Acertos Totais;
- A = 19 Mensagens de Erros/Acertos que não mencionam termos internos ao software. 

### Resultado:

Os resultados obtidos individualmente por ambiente foram:

| Amiente       | Total de Mensagens (B) | Mensagens claras (A) | Taxa de Clareza das Mensagens |
| ------------- | ---------------------- | -------------------- | ----------------------------- |
| agromart-web  | 10                     | 8                    | 80%                           |
| mobile-client | 28                     | 19                   | 67%                           |

Os resultados gerais, portanto podem ser vistas abaixo:

- A = 38 Mensagens Totais;
- B = 27 Mensagens Claras.
- **Taxa de Clareza das Mensagens:** 71%

O resultado indica, portanto, valores **abaixo** da hipótese esperada para esta questão, cujo foram indicadas na seção [Definição do GQM](../03-gqm/definicao.md).

## Questão 3:

A questão analisada está relacionada à métrica de Usabilidade, com foco na clareza das mensagens exibidas pelo sistema. O objetivo desta métrica é avaliar se as mensagens apresentadas ao usuário são de fácil entendimento, auxiliando-o na compreensão do problema ocorrido e, quando possível, indicando como solucioná-lo.

Durante os testes no ambiente da aplicação, foram identificadas três mensagens principais que aparecem em situações de erro nas funcionalidades acessadas. São elas:

**"Ops, Não foi possível carregar as lojas"**: Esta mensagem não especifica o motivo da falha (por exemplo: problema de rede, falha no servidor, ou dados inconsistentes). Assim, o usuário não sabe se deve tentar novamente, verificar sua conexão ou entrar em contato com o suporte.

<center>
<img src="../assets/mensagem_lojas.jpeg" width="350"/>
<br />
<spam>Figura 6 - Mensagem de erro de não carregamento das lojas</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

**"Erro ao cadastrar usuário”**: Também trata-se de uma mensagem genérica, sem explicar se o erro ocorreu por causa de falha de validação (ex: senha fraca, e-mail inválido), usuário já existente ou outro fator.

<center>
<img src="../assets/mensagem_usuario.jpeg" width="350"/>
<br />
<spam>Figura 7 - Mensagem de erro no cadastro de usuário</spam>
<br />
<spam>Fonte: Autores, 2025</spam>
</center>

**"Ops :( Não foi possível atualizar seus dados"**: Novamente, a mensagem não orienta o usuário sobre o que causou a falha, nem sugere um próximo passo.

<center>
<img src="../assets/mensagem_dados.jpeg" width="350"/>
<br />
<spam>Figura 8 - Mensagem de erro de atualização dos dados</spam>
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
