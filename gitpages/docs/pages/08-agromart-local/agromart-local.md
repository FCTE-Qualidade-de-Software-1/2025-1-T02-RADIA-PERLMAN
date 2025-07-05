# Tutorial para Rodar o Agromart Local

## Sobre a arquitetura do Agromart

O Agromart é uma aplicação que precisa de 3 repositórios para conseguir rodar localmente e ser possível fazer login. Os repositórios são [mobile-client](https://github.com/AgroMart/mobile-client) (o front-end), [api](https://github.com/AgroMart/api) (back-end) e [api-dicionario](https://github.com/AgroMart/api-dicionario) (parte da arquitetura responsável por guardar a url do back-end de todas as CSAs que estão integradas com o ambiente Agromart, permitindo que o aplicativo se comunique com diferentes back-ends). A arquitetura da aplicação é detalhada na imagem abaixo

<center>

<a id="fig2">Figura 1 – Arquitetura do Agromart</a>

<img src="https://github.com/FCTE-Qualidade-de-Software-1/2025-1-T02-RADIA-PERLMAN/blob/agromart_local/gitpages/docs/assets/arquitetura-agromart.png?raw=true">

<font size="2"><p style="text-align: center"><b>Autores: CELLA e FREITAS (2023)</b></p></font>

</center>

Como no repositório da api-dicionário não existe nenhuma documentação para rodar essa aplicação nem nenhuma documentação nos repositórios para rodar toda a arquitetura do software localmente (sem usar o Heroku ou outro serviço de hospedagem em nuvem), o grupo decidiu fazer um tutorial para isso já que será necessário rodar a aplicação para conseguir obter algumas das métricas.

## Api-Dicionário

1) Inicialmente, é preciso fazer um clone do repositório [api-dicionario](https://github.com/AgroMart/api-dicionario). Em seguida, na raiz do projeto, é necessário exportar as variáveis de ambiente com comando:

```
export NODE_ENV="development"
```

2) Criar um arquivo .env e adicionar as variáveis de ambiente:

```
DATABASE_URL=postgres://postgres:password@localhost:5433/postgres
PORT=8080
```

3) No arquivo src/config/sequelize.js substituir o development:

```
export const development = {
    ...defaultConfig,
    dialectOptions: {
    ssl: false // Desativa explicitamente para desenvolvimento
    }
};
```

4) Rodar postgresql local:

```
sudo docker run --name agromart-api-dicionario-postgres -e POSTGRES_PASSWORD=password -p 5433:5432  postgres
```


5) Installar dependências:

```
yarn install 
#ou 
npm install 
```

6) Rodar migration:

```
yarn db:migrate
#ou
npm run db:migrate
```

7) Rodar projeto:

```
yarn start:dev 
#ou
npm run start:dev 
```

8) Depois de subir a API, é necessário criar uma CSA na API para ser possível logar na aplicativo do Agromart. Faça uma requisição POST no endereço http://localhost:8080/csa usando um serviço como o Postman. A requisição deve ter o body no padrão abaixo. Você também precisa conseguir o endereço ip da sua máquina e substituir o IP_DA_SUA_MAQUINA pelo ip no atributo urlBase para conseguir fazer as requisições para o seu backend do Agromart local. Outra observação é que caso você esteja usando o Expo pelo celular Android, é preciso que seu celular e sua máquina estejam conectados na mesma rede Wi-fi

```
{
    "nomeCSA" : "Nome da CSA",
    "urlBase" : "http://IP_DA_SUA_MAQUINA:1337/",
    "responsavelCSA" : "Nome responsavel",
    "emailCSA" : "email@email.com"
}
```

O resultado dessa requisição vai conter o id da CSA e esse id é o código da CSA pedido pelo aplicativo quando se tenta logar 

<center>

<a id="fig2">Figura 2 – Tela de Login que pede o Código da CSA</a>

<img src="https://github.com/FCTE-Qualidade-de-Software-1/2025-1-T02-RADIA-PERLMAN/blob/agromart_local/gitpages/docs/assets/tela_de_login_agromart.png?raw=true">

<font size="2"><p style="text-align: center"><b>Autores: CELLA e FREITAS (2023)</b></p></font>

</center>


## Api Back-end Local

1) Para rodar o back-end local do Agromart (onde ficam guardados todas as informações referentes às regras de negócio da aplicação), não é necessário fazer nenhuma alteração e só seguir a documentação disponível no repositório do projeto [api](https://github.com/AgroMart/api/blob/devel/README.md) abaixo do tópico "Como executar o projeto localmente"

## Front-end Mobile

1) Para rodar o front-end da aplicação, é necessário fazer uma alteração depois de fazer o clone do repositório. No arquivo src/services/api-dicionario.ts, altere a linha:

```
export const baseURL = 'https://agromarttcc.shop/dicionario/';
```

para 

```
export const baseURL = 'http://IP_DA_SUA_MAQUINA:8080/';
```

sendo novamente necessário substituir o IP_DA_SUA_MAQUINA pelo endereço ip da sua máquina local

2) Em seguida, é só seguir a documentação disponível no repositório do projeto [mobile-client](https://github.com/AgroMart/mobile-client?tab=readme-ov-file#como-executar-o-projeto). E então você pode usar a aplicação por um dispositivo android ou outra opção disponibilizada pelo Expo.

**Bibliografia**

> CELLA, Pedro Vítor de Salles; FREITAS, André Aben-Athar de. Uma evolução do projeto Agromart: implantação individualizada e automatizada de um ambiente de CSA. 2023. Trabalho de Conclusão de Curso (Graduação em Engenharia de Software) – Universidade de Brasília, Faculdade UnB Gama, Brasília, 2023. Disponível em: https://bdm.unb.br/bitstream/10483/35945/1/2023_AndreFreitas_PedroVitorCella_tcc.pdf. Acesso em: 30 jun. 2025.
>

**Histórico de Versões**

| **Versão** | **Data**     | **Descrição**                     | **Autor**                                     |
|------------|--------------|-----------------------------------|-----------------------------------------------|
| `1.0`      | 25/06/2025   | Criação do documento e inserção de instruções para rodar o api-dicionario, api e mobile-client  | [Victório Lázaro](https://github.com/Victor-oss) |