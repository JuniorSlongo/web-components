# Alternador de Tema Web Component

Este Web Component permite alternar entre um tema claro e escuro em uma página web. É uma maneira simples e eficaz de melhorar a experiência do usuário permitindo que eles escolham o tema visual que preferirem.

## Como Usar

Para usar este Web Component em sua página web, siga os passos abaixo:

### 1. Inclua o Template e o Script

Adicione o seguinte código dentro da tag `<head>` do seu arquivo HTML:

```html
<template id="alternador-tema">
  <style>
    :host {
      display: block;
      margin: 10px;
      padding: 10px;
      border: 1px solid #ccc;
      border-radius: 5px;
    }
    button {
      padding: 5px 10px;
      cursor: pointer;
    }
  </style>
  <button id="toggle">Alternar Tema</button>
</template>

<script>
  class AlternadorTema extends HTMLElement {
    constructor() {
      super();
      const shadowRoot = this.attachShadow({mode: 'open'});
      const template = document.getElementById('alternador-tema').content;
      shadowRoot.appendChild(template.cloneNode(true));
      this.btn = shadowRoot.querySelector('#toggle');
      this.btn.addEventListener('click', () => {
        document.body.classList.toggle('tema-escuro');
      });
    }
  }
  customElements.define('alternador-tema', AlternadorTema);
</script>
```

### 2. Defina os Estilos dos Temas

No seu arquivo CSS principal ou dentro de uma tag `<style>` no seu HTML, adicione os estilos para os temas claro e escuro:

```css
body {
  /* Estilos para o tema claro */
  background-color: #fff;
  color: #000;
}

.tema-escuro {
  /* Estilos para o tema escuro */
  background-color: #333;
  color: white;
}
```

### 3. Adicione o Componente ao seu HTML
Use o Web Component como qualquer outra tag HTML:
```html
<alternador-tema></alternador-tema>
```

