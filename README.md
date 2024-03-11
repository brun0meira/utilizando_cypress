# Cypress

## 1. Introdução

### 1.1 O que é o Cypress?

O Cypress é uma ferramenta de teste de front-end que se destaca por sua velocidade, facilidade de uso e confiabilidade. Projetado para atender às demandas da web moderna, o Cypress permite que os desenvolvedores escrevam testes que simulam interações de usuários. Ele é especialmente útil para testes de integração e teste de ponta a ponta (end-to-end), permitindo que os desenvolvedores escrevam testes em JavaScript e executem esses testes em um navegador real.

O Cypress oferece uma série de recursos úteis para testes de front-end, incluindo:

1. **Fácil configuração:** O Cypress é fácil de instalar e configurar, com um conjunto mínimo de dependências.

2. **Execução em tempo real:** Os testes podem ser executados em tempo real em um navegador, permitindo que os desenvolvedores visualizem e interajam com o aplicativo conforme os testes são executados.

3. **Rastreamento de comandos:** O Cypress registra todos os comandos executados durante o teste, facilitando a depuração e a identificação de problemas.

4. **Execução paralela:** O Cypress suporta a execução paralela de testes, permitindo que os desenvolvedores testem rapidamente em diferentes ambientes e configurações.

5. **Integração contínua:** O Cypress pode ser facilmente integrado a pipelines de integração contínua (CI) para automatizar a execução de testes em cada commit ou pull request.

## 2. Vantagens e Desvantagens do Cypress

### 2.1 Vantagens

#### 2.1.1 Facilidade de Uso
A sintaxe simples e intuitiva do Cypress facilita a criação de testes, mesmo para desenvolvedores iniciantes.

#### 2.1.2 Tempo Real
A visualização em tempo real dos testes durante a execução permite uma rápida identificação de problemas.

#### 2.1.3 Debugging Simplificado
A capacidade de inspecionar elementos durante a execução dos testes simplifica o processo de identificação e correção de falhas.

#### 2.1.4 Compatibilidade
O Cypress oferece suporte a vários navegadores modernos, garantindo uma cobertura abrangente dos testes.

#### 2.1.5 Execução paralela
O Cypress suporta a execução paralela de testes, permitindo testar em diferentes ambientes e configurações de forma rápida e eficiente.

#### 2.1.6 Integração contínua 
O Cypress pode ser facilmente integrado a pipelines de integração contínua (CI), automatizando a execução de testes em cada commit ou pull request.

### 2.2 Desvantagens

#### 2.2.1 Suporte Limitado para Dispositivos Móveis
Embora robusto para testes web, o Cypress apresenta limitações em testes para dispositivos móveis.

#### 2.2.2 Suporte Experimental para Navegadores Remotos
A funcionalidade de testes em navegadores remotos é experimental e pode não ser totalmente estável.

#### 2.2.3 Requer Conhecimento de JavaScript
É necessário conhecimento prévio de JavaScript para escrever testes eficazes no Cypress.

#### 2.2.4 Custo
Embora o Cypress seja uma ferramenta de código aberto, a versão Enterprise, que oferece recursos adicionais, possui um custo associado.

## 3. Arquitetura do Cypress

O Cypress possui uma arquitetura simples composta por três componentes principais:

### 3.1 Cypress Test Runner
Uma interface gráfica que facilita a escrita, visualização e depuração de testes.

### 3.2 Cypress CLI
Uma ferramenta de linha de comando que permite a execução de testes, gravação de vídeos e geração de relatórios.

### 3.3 Cypress Dashboard (Opcional)
Um serviço baseado em nuvem que armazena e exibe resultados de testes, proporcionando uma visão centralizada.

## 4. Seletores de Elementos no Cypress

O Cypress suporta vários seletores de elementos, incluindo seletores CSS, seletores jQuery e seletores personalizados.

Exemplo de uso de seletor CSS:

```javascript
cy.get('button').click();
```

## 5. Comandos e Assertivas no Cypress

O Cypress oferece uma variedade de comandos e assertivas para interagir com elementos da página e verificar seu estado.

Exemplo de comando de clique e assertiva de visibilidade:

```javascript
cy.get('button').click();
cy.get('div').should('be.visible');
```

## 6. Preparação, Execução e Verificação de Testes

### 6.1 Preparação do Teste

1. Instalar o Cypress usando npm ou yarn.
2. Criar um arquivo de teste spec.js.
3. Escrever testes usando a API do Cypress.

### 6.2 Execução do Teste

1. Abrir o Cypress Test Runner.
2. Selecionar o arquivo de teste a ser executado.
3. Executar o teste e observar os resultados em tempo real.

### 6.3 Verificação do Teste

1. Verificar se os testes passaram ou falharam.
2. Analisar os logs e vídeos gerados pelo Cypress.
3. Corrigir quaisquer problemas identificados nos testes.

## 7. Estrutura Eficiente de Testes no Cypress

Para estruturar testes de forma eficiente no Cypress, é ideal seguir as seguintes práticas recomendadas:

- Organizar os testes em pastas e subpastas com base nas funcionalidades.
- Utilizar beforeEach e afterEach para configurar o estado inicial e limpar após cada teste.
- Dividir os testes em cenários pequenos e específicos.
- Reutilizar código comum usando funções e comandos personalizados.

## 8. Aplicando os conceitos aprendidos na instrução 

As fotos e a documentação abaixo se referem à aplicação prática do Cypress conforme a instruções fornecida pelo Hernano. Serão comentados brevemente os testes e os processos de execução desses testes, tanto no terminal quanto no navegador Chrome.

![commands_support.png](./assets/commands_support.png)

- Esta imagem mostra a definição de uma função customizada para o Cypress, chamada byTestId.
- A função byTestId é uma abstração que permite selecionar elementos DOM pelo atributo data-testid, facilitando a identificação de elementos na realização de testes end-to-end.
- A função é definida dentro do namespace Cypress e é adicionada aos comandos do Cypress usando Cypress.Commands.add.
- O código também define a interface para a função, especificando que ela aceita um id (string) e um objeto options, e retorna um Cypress.Chainable<JQuery<E>>, o que permite a encadeação de comandos do Cypress.

![tests_spec.png](./assets/tests_spec.png)

- Esta imagem mostra o arquivo de especificação de testes do Cypress, spec.cy.ts.
- O arquivo contém uma suite de testes chamada 'Counter (with helpers)' e define vários testes (it blocks) que verificam o título da página, incrementam e decrementam um contador, e resetam o contador para um valor específico.
- Os testes utilizam a função byTestId que foi definida anteriormente para selecionar elementos específicos pelo seu data-testid e realizar ações como cliques e verificações de texto.

![tests_terminal.png](./assets/tests_terminal.png)

- Esta é uma captura de tela do terminal, mostrando os resultados da execução do arquivo spec.cy.ts.
- Os resultados indicam que todos os quatro testes definidos passaram com sucesso. Não há falhas, pendências ou testes pulados.
- O Cypress também fornece informações sobre a execução dos testes, como duração (1 segundo) e confirmação de que o vídeo da sessão de teste foi gravado (Video: true).

![tests_navegador.png](./assets/tests_navegador.png)

- Esta captura de tela mostra o navegador Chrome sendo controlado pelo software de teste automatizado Cypress durante a execução de testes.
- A interface do Cypress exibe a lista de testes especificados no arquivo spec.cy.ts, e todos eles estão marcados como passados (com uma marca de verificação verde).
- O navegador mostra a aplicação Angular que esta sendo testada.

As imagens documentam a criação e uso de uma função customizada no Cypress para selecionar elementos por ID de teste, a execução bem-sucedida de testes em uma interface de usuário de uma aplicação Angular, e a verificação dos resultados dos testes no Cypress, tanto na interface web quanto no terminal.

## 9. Referências

- Documentação oficial do Cypress: [docs.cypress.io](https://docs.cypress.io/)
- Por que usar o Cypress: [Why Cypress](https://docs.cypress.io/guides/overview/why-cypress)
