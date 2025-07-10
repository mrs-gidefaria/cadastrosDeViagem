## 📄Automação com Robot Framework

Este arquivo contém um **exemplo de automação de testes com Robot Framework**, utilizando a sintaxe no formato `.robot` e aplicando a **abordagem BDD (Behavior-Driven Development)**.

### 🔧 Estrutura e Finalidade

O objetivo do teste é **simular uma pesquisa por voos de ida e volta** em um site de viagens, preenchendo campos essenciais e validando que os resultados aparecem corretamente.

O script está dividido em três seções principais:

1. **Settings (Configurações):**

   * Importa a biblioteca `SeleniumLibrary`, necessária para automação de navegadores.
   * Define o caminho do resource `travel.resource`, onde estão definidos os keywords reutilizáveis.

2. **Test Cases (Casos de Teste):**

   * Contém um único caso de teste com nome descritivo no estilo BDD:
     `Dado que acesso o site Blazedemo, Quando seleciono os dados da viagem, Então a lista de voos de ida e volta é apresentada`
   * O teste executa os seguintes passos:

     * Acessa o site do [Blazedemo](https://blazedemo.com/).
     * Seleciona a cidade de origem e destino.
     * Clica no botão de busca.
     * Verifica se a lista de voos está visível.

3. **Keywords (Palavras-chave personalizadas):**

   * As palavras-chave utilizadas no caso de teste estão centralizadas no arquivo `travel.resource`, promovendo **reutilização** e **organização** do código.

### ✅ Benefícios desta abordagem

* **Didática clara e legível:** A utilização de frases em português no padrão BDD torna o teste autoexplicativo.
* **Separação de responsabilidades:** As ações estão abstraídas em keywords, melhorando a manutenção.
* **Foco em comportamento do usuário:** Reflete o fluxo de navegação esperado por um usuário comum ao buscar passagens.

<!-- 
---

## 🔁 Descrição do Arquivo `travel.resource`

O arquivo `travel.resource` complementa o script `travel.robot` ao **centralizar e organizar as palavras-chave (keywords)** utilizadas no teste. Ele segue boas práticas de modularização no Robot Framework.

### 📚 Estrutura e Função

1. **Library**

   * Importa a `SeleniumLibrary`, necessária para interagir com elementos do navegador.

2. **Variables**

   * Define variáveis reutilizáveis, como:

     * `${URL}`: endereço do site a ser testado (`https://blazedemo.com`)
     * Seletores dos elementos HTML, como campos de origem, destino, botão de busca e títulos das páginas

3. **Keywords**

   * Contém definições de ações reutilizáveis que representam passos do teste no estilo BDD:

     * **Dado que acesso o site Blazedemo:** abre o navegador e acessa a URL definida.
     * **Quando seleciono os dados da viagem:** escolhe as cidades de origem e destino e clica em "Find Flights".
     * **Então a lista de voos de ida e volta é apresentada:** verifica se o título da página seguinte está correto e se há voos listados.

### 🧠 Por que usar um arquivo `.resource`?

* **Organização:** separa a lógica dos testes (ações) da definição dos casos de teste.
* **Reusabilidade:** keywords podem ser usadas em múltiplos testes.
* **Facilidade de manutenção:** alterações em elementos ou ações são feitas em um único lugar.
