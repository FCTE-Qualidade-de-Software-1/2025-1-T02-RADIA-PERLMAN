<span style="background-color:#00aa95; color:white; font-size:0.8em; font-weight: bold; padding:2px 6px; border-radius:4px;">Versão 1.0</span>

# Resultados Obtidos | Usabilidade

## Questão 1:

## Questão 2: A linguagem da mensagem está adequada ao público-alvo (sem termos técnicos)?
A questão 2, também relacionada à "Usabilidade" busca quantificar a quantidade de erros que podem trazer cofusão aos usuários por trazer termos técnicos, isto é, funções, variáveis ou componentes internos do software. A métrica utilizada para responder esta questão está descrita no tópico [Definição do GQM](../03-gqm/definicao.md), chamada **Clareza de Mensagens**, cujo recebe dois parâmetros:

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

## Conclusão:

---

**Histórico de Versões**

| **Versão** | **Data**   | **Descrição**                    | **Autor**                                         |
| ---------- | ---------- | -------------------------------- | ------------------------------------------------- |
| `1.0`      | 05/07/2025 | Criação e estruturação da página | [Daniel Rodrigues](https://github.com/DanielRogs) |
