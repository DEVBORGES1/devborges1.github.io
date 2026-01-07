# 📘 Documentação Técnica

Este documento serve como um guia mais aprofundado sobre como o **Portfólio** foi construído e como as coisas funcionam nos bastidores.

## 🏗️ Estrutura do Projeto

A organização de pastas segue um padrão intuitivo para facilitar a manutenção:

*   **`src/components/`**: Aqui vivem os blocos de construção. Cada parte da página (Hero, About, Projects, etc.) é um componente isolado. Isso ajuda a manter o código limpo e fácil de debugar.
*   **`src/styles/`**:
    *   `global.css`: Onde defino as regras gerais, como reset de CSS e variáveis de cores.
    *   `components.css`: Estilização específica de cada componente. Preferi separar assim para não ter um arquivo CSS gigante e incontrolável.
*   **`src/assets/`**: Imagens, ícones e outros arquivos estáticos.

## 🎨 Estilização e Design

O design foi pensado para ser **clean** e **moderno**.

*   **Variáveis CSS (`var(--...)`):** Uso variáveis para cores e fontes. Isso significa que se eu quiser mudar a cor principal do site de vermelho para azul, mudo em um lugar só e o site inteiro atualiza. Sem gambiarra.
*   **Responsividade:** Tudo foi feito usando Flexbox e Grid. O site se adapta a celulares, tablets e desktops sem quebrar o layout. O menu de navegação, por exemplo, vira um hambúrguer em telas pequenas.

## ✨ Animações

Para as animações, não usei CSS puro para tudo porque queria um controle maior sobre o tempo e a sequência de entrada.

*   **Framer Motion:** É a biblioteca que cuida das entradas suaves.
    *   *Exemplo:* O componente `StaggeredReveal` faz os itens aparecerem um de cada vez em cascata, ao invés de aparecerem todos de uma vez de forma bruta.
*   **Tilt Effect:** Nos cards de projetos, usei `react-tilt` para dar aquela sensação de profundidade quando você passa o mouse. É um detalhe sutil, mas que adiciona valor à experiência.

## 🚀 Deploy

O deploy é automatizado via **GitHub Pages**.
O script `npm run deploy` faz o build da aplicação (gera a pasta `dist` otimizada) e empurra essa pasta para uma branch especial chamada `gh-pages`, que o GitHub usa para servir o site.

## 🔧 Manutenção

Se precisar adicionar um novo projeto:
1.  Vá em `src/components/Projects.jsx`.
2.  Adicione um novo objeto na lista `projects`.
3.  Coloque a imagem do projeto na pasta `assets` e importe ela.
4.  Pronto! O resto o código resolve sozinho.
