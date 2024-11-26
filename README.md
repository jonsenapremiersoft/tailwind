# Guia Tailwind CSS

## Introdução
O Tailwind CSS é um framework CSS que utiliza uma abordagem utility-first, permitindo construir interfaces personalizadas diretamente no HTML usando classes predefinidas. Em vez de escrever CSS tradicional, você compõe seus estilos combinando pequenas classes utilitárias.

## Layout Básico

### Container
O container é fundamental para criar layouts responsivos no Tailwind. Ele automaticamente centraliza e define larguras máximas para seu conteúdo.

```html
<!-- Container básico -->
<div class="container mx-auto px-4">
  <!-- Seu conteúdo aqui -->
</div>

<!-- Container com largura personalizada -->
<div class="container mx-auto px-4 max-w-4xl">
  <!-- Conteúdo com largura máxima -->
</div>
```

### Spacing (Espaçamento)
O Tailwind usa um sistema de escala consistente para espaçamento. Os números representam unidades de 0.25rem (4px).

```html
<!-- Margem -->
<div class="m-4">  <!-- 1rem (16px) de margem em todos os lados -->
<div class="mt-4"> <!-- 1rem de margem no topo -->
<div class="mb-4"> <!-- 1rem de margem na base -->
<div class="my-4"> <!-- 1rem de margem vertical (topo e base) -->
<div class="mx-4"> <!-- 1rem de margem horizontal (esquerda e direita) -->

<!-- Padding -->
<div class="p-4">  <!-- 1rem de padding em todos os lados -->
<div class="pt-4"> <!-- 1rem de padding no topo -->
<div class="pb-4"> <!-- 1rem de padding na base -->
<div class="py-4"> <!-- 1rem de padding vertical -->
<div class="px-4"> <!-- 1rem de padding horizontal -->

<!-- Exemplo prático de card com espaçamento -->
<div class="bg-white rounded-lg shadow-md p-6 mb-4">
  <h2 class="text-xl font-bold mb-4">Título do Card</h2>
  <p class="mb-2">Primeiro parágrafo com margem inferior.</p>
  <p>Último parágrafo sem margem inferior.</p>
</div>
```

### Flexbox
O Flexbox é uma das ferramentas mais poderosas para layout no Tailwind. Aqui está um guia detalhado:

```html
<!-- Container Flex Básico -->
<div class="flex">
  <div>Item 1</div>
  <div>Item 2</div>
</div>

<!-- Direção -->
<div class="flex flex-row">      <!-- Horizontal (padrão) -->
<div class="flex flex-col">      <!-- Vertical -->
<div class="flex flex-row-reverse"> <!-- Horizontal invertido -->
<div class="flex flex-col-reverse"> <!-- Vertical invertido -->

<!-- Alinhamento - Eixo Principal (justify) -->
<div class="flex justify-start">     <!-- Início (padrão) -->
<div class="flex justify-center">    <!-- Centro -->
<div class="flex justify-end">       <!-- Fim -->
<div class="flex justify-between">   <!-- Espaço entre -->
<div class="flex justify-around">    <!-- Espaço ao redor -->
<div class="flex justify-evenly">    <!-- Espaço igual -->

<!-- Alinhamento - Eixo Cruzado (items) -->
<div class="flex items-start">    <!-- Topo -->
<div class="flex items-center">   <!-- Centro -->
<div class="flex items-end">      <!-- Base -->
<div class="flex items-stretch">  <!-- Esticar (padrão) -->

<!-- Exemplo prático: Navbar -->
<nav class="flex justify-between items-center p-4 bg-white shadow">
  <div class="flex items-center space-x-4">
    <img src="logo.png" class="h-8" alt="Logo">
    <span class="font-bold text-xl">Minha App</span>
  </div>
  <div class="flex items-center space-x-4">
    <a href="#" class="px-4 py-2 hover:text-blue-600">Home</a>
    <a href="#" class="px-4 py-2 hover:text-blue-600">Sobre</a>
    <button class="px-4 py-2 bg-blue-500 text-white rounded hover:bg-blue-600">
      Login
    </button>
  </div>
</nav>
```

### Grid
O sistema de grid do Tailwind é baseado em CSS Grid e oferece grande flexibilidade:

```html
<!-- Grid Básico -->
<div class="grid grid-cols-3 gap-4">
  <div>Item 1</div>
  <div>Item 2</div>
  <div>Item 3</div>
</div>

<!-- Grid Responsivo -->
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3 gap-4">
  <!-- Items se ajustam conforme tamanho da tela -->
</div>

<!-- Grid com Items de Tamanhos Diferentes -->
<div class="grid grid-cols-3 gap-4">
  <div class="col-span-2">Ocupa 2 colunas</div>
  <div>Ocupa 1 coluna</div>
  <div>Ocupa 1 coluna</div>
  <div class="col-span-3">Ocupa todas as colunas</div>
</div>

<!-- Exemplo prático: Gallery -->
<div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-4 p-4">
  <div class="bg-white rounded-lg shadow-md overflow-hidden">
    <img src="image1.jpg" class="w-full h-48 object-cover" alt="Image 1">
    <div class="p-4">
      <h3 class="font-bold mb-2">Título da Imagem</h3>
      <p class="text-gray-600">Descrição da imagem</p>
    </div>
  </div>
  <!-- Repetir para outras imagens -->
</div>
```

## Tipografia

### Sistema de Fontes
O Tailwind oferece controle preciso sobre a tipografia:

```html
<!-- Tamanhos de Fonte -->
<p class="text-xs">Texto muito pequeno</p>    <!-- 12px -->
<p class="text-sm">Texto pequeno</p>          <!-- 14px -->
<p class="text-base">Texto base</p>           <!-- 16px -->
<p class="text-lg">Texto grande</p>           <!-- 18px -->
<p class="text-xl">Texto extra grande</p>     <!-- 20px -->
<p class="text-2xl">Título menor</p>          <!-- 24px -->
<p class="text-3xl">Título médio</p>          <!-- 30px -->
<p class="text-4xl">Título grande</p>         <!-- 36px -->

<!-- Peso da Fonte -->
<p class="font-thin">Texto fino</p>           <!-- 100 -->
<p class="font-normal">Texto normal</p>       <!-- 400 -->
<p class="font-medium">Texto médio</p>        <!-- 500 -->
<p class="font-semibold">Texto semibold</p>   <!-- 600 -->
<p class="font-bold">Texto bold</p>           <!-- 700 -->

<!-- Exemplo prático: Article -->
<article class="max-w-2xl mx-auto p-4">
  <h1 class="text-4xl font-bold mb-6">
    Título Principal do Artigo
  </h1>
  <p class="text-xl text-gray-600 mb-8">
    Subtítulo ou descrição do artigo com destaque.
  </p>
  <div class="prose lg:prose-xl">
    <h2 class="text-2xl font-semibold mb-4">
      Seção do Artigo
    </h2>
    <p class="mb-4 text-gray-700 leading-relaxed">
      Parágrafo com texto normal e espaçamento adequado.
    </p>
    <blockquote class="border-l-4 border-gray-300 pl-4 my-4 italic">
      Citação importante no artigo
    </blockquote>
  </div>
</article>
```

## Cores e Backgrounds

### Sistema de Cores
O Tailwind possui um sistema de cores extensivo com diferentes intensidades:

```html
<!-- Cores de Texto -->
<p class="text-blue-500">Texto azul médio</p>
<p class="text-red-600">Texto vermelho forte</p>
<p class="text-gray-700">Texto cinza escuro</p>

<!-- Backgrounds -->
<div class="bg-blue-500">Background azul</div>
<div class="bg-red-100">Background vermelho claro</div>
<div class="bg-gray-200">Background cinza claro</div>

<!-- Exemplo prático: Alert Components -->
<!-- Sucesso -->
<div class="bg-green-100 border-l-4 border-green-500 text-green-700 p-4 mb-4">
  <p class="font-bold">Sucesso!</p>
  <p>Sua operação foi concluída com êxito.</p>
</div>

<!-- Erro -->
<div class="bg-red-100 border-l-4 border-red-500 text-red-700 p-4 mb-4">
  <p class="font-bold">Erro!</p>
  <p>Algo deu errado. Tente novamente.</p>
</div>

<!-- Warning -->
<div class="bg-yellow-100 border-l-4 border-yellow-500 text-yellow-700 p-4">
  <p class="font-bold">Atenção!</p>
  <p>Verifique os dados antes de continuar.</p>
</div>
```

## Responsividade

O Tailwind utiliza uma abordagem mobile-first com breakpoints intuitivos:

```html
<!-- Card Responsivo -->
<div class="
  w-full                /* Mobile: largura total */
  md:w-1/2             /* Tablet: metade da largura */
  lg:w-1/3             /* Desktop: um terço da largura */
  p-4                  /* Padding em todos os tamanhos */
  bg-white 
  rounded-lg 
  shadow-md
">
  <img 
    src="image.jpg" 
    class="
      w-full            /* Largura total em todos os tamanhos */
      h-32             /* Altura fixa em mobile */
      md:h-48          /* Altura maior em tablet */
      lg:h-64          /* Altura ainda maior em desktop */
      object-cover
    "
  >
  <div class="p-4">
    <h3 class="
      text-lg          /* Tamanho base em mobile */
      md:text-xl       /* Maior em tablet */
      lg:text-2xl      /* Ainda maior em desktop */
      font-bold
    ">
      Título do Card
    </h3>
    <p class="
      text-sm          /* Texto pequeno em mobile */
      md:text-base     /* Texto normal em tablet+ */
      text-gray-600
    ">
      Descrição do card que se adapta aos diferentes tamanhos de tela.
    </p>
  </div>
</div>
```

## Componentes Comuns

### Botões

```html
<!-- Botões em diferentes estilos -->
<!-- Primário -->
<button class="
  bg-blue-500 
  hover:bg-blue-600 
  text-white 
  font-bold 
  py-2 
  px-4 
  rounded
  transition 
  duration-200
">
  Botão Primário
</button>

<!-- Secundário -->
<button class="
  bg-gray-200 
  hover:bg-gray-300 
  text-gray-800 
  font-bold 
  py-2 
  px-4 
  rounded
  transition 
  duration-200
">
  Botão Secundário
</button>

<!-- Outline -->
<button class="
  border-2 
  border-blue-500 
  hover:bg-blue-500 
  hover:text-white 
  text-blue-500 
  font-bold 
  py-2 
  px-4 
  rounded
  transition 
  duration-200
">
  Botão Outline
</button>

<!-- Disabled -->
<button class="
  bg-blue-500 
  text-white 
  font-bold 
  py-2 
  px-4 
  rounded
  opacity-50 
  cursor-not-allowed
" disabled>
  Botão Desabilitado
</button>
```

### Forms

```html
<!-- Form com estilo completo -->
<form class="max-w-md mx-auto p-6 bg-white rounded-lg shadow-md">
  <!-- Campo de texto -->
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="username">
      Username
    </label>
    <input 
      type="text" 
      id="username"
      class="
        shadow 
        appearance-none 
        border 
        rounded 
        w-full 
        py-2 
        px-3 
        text-gray-700 
        leading-tight
        focus:outline-none 
        focus:shadow-outline 
        focus:border-blue-500
      "
    >
  </div>

  <!-- Select -->
  <div class="mb-4">
    <label class="block text-gray-700 text-sm font-bold mb-2" for="country">
      País
    </label>
    <select 
      id="country"
      class="
        block 
        w-full 
        py-2 
        px-3 
        border 
        border-gray-300 
        rounded 
        shadow-sm 
        focus:outline-none 
        focus:ring-blue-500 
        focus:border-blue-500
      "
    >
      <option>Brasil</option>
      <option>Portugal</option>
      <option>Angola</option>
    </select>
  </div>

  <!-- Checkbox -->
  <div class="mb-4">
    <label class="flex items-center">
      <input 
        type="checkbox"
        class="
          form-checkbox 
          h-5 
          w-5 
          text-blue-600
        "
      >
      <span class="ml-2 text-gray-700">Lembrar-me</span>
    </label>
  </div>

  <!-- Botão Submit -->
  <div class="flex items-center justify-between">
    <button 
      type="submit"
      class="
        bg-blue-500 
        hover:bg-blue-700 
        text-white 
        font-bold 
        py-2 
        px-4 
        rounded 
        focus:outline-none 
        focus:shadow-outline
      "
    >
      Enviar
    </button>
  </div>
</form>
```

### Cards

```html
<!-- Card Básico -->
<div class="bg-white rounded-lg shadow-md overflow-hidden">
  <div class="p-6">
    <h2 class="text-xl font-bold mb-2">Título do Card</h2>
    <p class="text-gray-600">Conteúdo do card aqui.</p>
  </div>
</div>

<!-- Card com Imagem -->
<div class="bg-white rounded-lg shadow-md overflow-hidden max-w-sm">
  <img 
    src="imagem.jpg" 
    class="w-full h-48 object-cover"
    alt="Descrição da imagem"
  >
  <div class="p-6">
    <h2 class="text-xl font-bold mb-2">Título do Card</h2>
    <p class="text-gray-600 mb-4">Descrição mais longa do conteúdo do card, 
    que pode ocupar várias linhas.</p>
    <button class="bg-blue-500 text-white px-4 py-2 rounded hover:bg-blue-600 transition">
      Ler mais
    </button>
  </div>
</div>

<!-- Card com Badge e Footer -->
<div class="bg-white rounded-lg shadow-md overflow-hidden max-w-sm">
  <div class="p-6">
    <div class="flex justify-between items-center mb-4">
      <h2 class="text-xl font-bold">Título do Card</h2>
      <span class="bg-green-100 text-green-800 text-xs font-semibold px-2.5 py-0.5 rounded">
        Novo
      </span>
    </div>
    <p class="text-gray-600 mb-4">Conteúdo principal do card.</p>
    <div class="border-t pt-4 mt-4">
      <div class="flex justify-between items-center">
        <div class="flex items-center">
          <img 
            class="w-8 h-8 rounded-full mr-2" 
            src="avatar.jpg" 
            alt="Avatar"
          >
          <span class="text-sm text-gray-600">João Silva</span>
        </div>
        <span class="text-sm text-gray-500">Há 2 dias</span>
      </div>
    </div>
  </div>
</div>

<!-- Card Interativo -->
<div class="bg-white rounded-lg shadow-md overflow-hidden max-w-sm 
            transform transition duration-300 hover:scale-105 hover:shadow-xl">
  <div class="relative">
    <img 
      src="imagem.jpg" 
      class="w-full h-48 object-cover"
      alt="Descrição da imagem"
    >
    <div class="absolute top-0 right-0 m-2">
      <button class="bg-white p-2 rounded-full shadow hover:bg-gray-100">
        <svg class="w-5 h-5 text-red-500" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                d="M4.318 6.318a4.5 4.5 0 000 6.364L12 20.364l7.682-7.682a4.5 4.5 0 00-6.364-6.364L12 7.636l-1.318-1.318a4.5 4.5 0 00-6.364 0z">
          </path>
        </svg>
      </button>
    </div>
  </div>
  <div class="p-6">
    <div class="flex justify-between items-center mb-3">
      <h2 class="text-xl font-bold">Título Interativo</h2>
      <span class="bg-blue-100 text-blue-800 text-xs font-semibold px-2.5 py-0.5 rounded-full">
        Destaque
      </span>
    </div>
    <p class="text-gray-600 mb-4">Descrição do card com animações e interações.</p>
    <div class="flex justify-between items-center">
      <button class="bg-blue-500 text-white px-4 py-2 rounded 
                     hover:bg-blue-600 transition transform hover:scale-105">
        Ver detalhes
      </button>
      <div class="flex items-center">
        <span class="text-yellow-400 mr-1">★</span>
        <span class="text-gray-600">4.5</span>
      </div>
    </div>
  </div>
</div>
```

### Navegação

```html
<!-- Navbar Responsiva -->
<nav class="bg-white shadow">
  <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8">
    <div class="flex justify-between h-16">
      <!-- Logo e Menu Principal -->
      <div class="flex">
        <div class="flex-shrink-0 flex items-center">
          <img class="h-8 w-auto" src="logo.svg" alt="Logo">
        </div>
        <!-- Menu Desktop -->
        <div class="hidden md:flex md:items-center md:space-x-4 ml-8">
          <a href="#" class="text-gray-700 hover:text-blue-500 px-3 py-2 rounded-md 
                            font-medium transition">Home</a>
          <a href="#" class="text-gray-700 hover:text-blue-500 px-3 py-2 rounded-md 
                            font-medium transition">Produtos</a>
          <a href="#" class="text-gray-700 hover:text-blue-500 px-3 py-2 rounded-md 
                            font-medium transition">Sobre</a>
          <a href="#" class="text-gray-700 hover:text-blue-500 px-3 py-2 rounded-md 
                            font-medium transition">Contato</a>
        </div>
      </div>
      
      <!-- Botões de Ação -->
      <div class="flex items-center">
        <!-- Botão de Pesquisa -->
        <button class="p-2 rounded-md text-gray-400 hover:text-gray-500 
                       hover:bg-gray-100 focus:outline-none focus:ring-2 
                       focus:ring-blue-500">
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                  d="M21 21l-6-6m2-5a7 7 0 11-14 0 7 7 0 0114 0z"></path>
          </svg>
        </button>
        
        <!-- Botão de Notificações -->
        <button class="ml-4 p-2 rounded-md text-gray-400 hover:text-gray-500 
                       hover:bg-gray-100 focus:outline-none focus:ring-2 
                       focus:ring-blue-500">
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                  d="M15 17h5l-1.405-1.405A2.032 2.032 0 0118 14.158V11a6.002 6.002 0 00-4-5.659V5a2 2 0 10-4 0v.341C7.67 6.165 6 8.388 6 11v3.159c0 .538-.214 1.055-.595 1.436L4 17h5m6 0v1a3 3 0 11-6 0v-1m6 0H9"></path>
          </svg>
        </button>
        
        <!-- Avatar e Menu Dropdown -->
        <div class="ml-4 relative">
          <button class="flex items-center">
            <img class="h-8 w-8 rounded-full" src="avatar.jpg" alt="Avatar">
            <svg class="ml-2 h-5 w-5 text-gray-400" fill="none" stroke="currentColor" 
                 viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                    d="M19 9l-7 7-7-7"></path>
            </svg>
          </button>
        </div>
      </div>
      
      <!-- Botão Menu Mobile -->
      <div class="flex items-center md:hidden">
        <button class="p-2 rounded-md text-gray-400 hover:text-gray-500 
                       hover:bg-gray-100 focus:outline-none focus:ring-2 
                       focus:ring-blue-500">
          <svg class="h-6 w-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" 
                  d="M4 6h16M4 12h16M4 18h16"></path>
          </svg>
        </button>
      </div>
    </div>
  </div>
  
  <!-- Menu Mobile -->
  <div class="md:hidden">
    <div class="px-2 pt-2 pb-3 space-y-1">
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium 
                        text-gray-700 hover:text-gray-900 hover:bg-gray-50">Home</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium 
                        text-gray-700 hover:text-gray-900 hover:bg-gray-50">Produtos</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium 
                        text-gray-700 hover:text-gray-900 hover:bg-gray-50">Sobre</a>
      <a href="#" class="block px-3 py-2 rounded-md text-base font-medium 
                        text-gray-700 hover:text-gray-900 hover:bg-gray-50">Contato</a>
    </div>
  </div>
</nav>
```

### Tabelas

```html
<!-- Tabela Responsiva -->
<div class="overflow-x-auto">
  <table class="min-w-full bg-white">
    <!-- Cabeçalho -->
    <thead class="bg-gray-50">
      <tr>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
          Nome
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
          Cargo
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
          Status
        </th>
        <th class="px-6 py-3 text-left text-xs font-medium text-gray-500 uppercase tracking-wider">
          Ações
        </th>
      </tr>
    </thead>
    
    <!-- Corpo -->
    <tbody class="bg-white divide-y divide-gray-200">
      <tr class="hover:bg-gray-50">
        <td class="px-6 py-4 whitespace-nowrap">
          <div class="flex items-center">
            <div class="flex-shrink-0 h-10 w-10">
              <img class="h-10 w-10 rounded-full" src="avatar.jpg" alt="Avatar">
            </div>
            <div class="ml-4">
              <div class="text-sm font-medium text-gray-900">João Silva</div>
              <div class="text-sm text-gray-500">joao@exemplo.com</div>
            </div>
          </div>
        </td>
        <td class="px-6 py-4 whitespace-nowrap">
          <div class="text-sm text-gray-900">Desenvolvedor Senior</div>
          <div class="text-sm text-gray-500">Tech</div>
        </td>
        <td class="px-6 py-4 whitespace-nowrap">
          <span class="px-2 inline-flex text-xs leading-5 font-semibold rounded-full 
                       bg-green-100 text-green-800">
            Ativo
          </span>
        </td>
        <td class="px-6 py-4 whitespace-nowrap text-sm text-gray-500">
          <button class="text-blue-600 hover:text-blue-900">Editar</button>
          <button class="ml-4 text-red-600 hover:text-red-900">Excluir</button>
        </td>
      </tr>
      <!-- Repetir para outras linhas -->
    </tbody>
  </table>
</div>
```

## Dicas Avançadas

### Customização de Hover/Focus
```html
<!-- Efeitos de Hover Complexos -->
<button class="
  bg-blue-500 
  hover:bg-blue-600 
  text-white 
  px-4 
  py-2 
  rounded
  transform 
  hover:scale-105 
  hover:shadow-lg 
  transition 
  duration-300
">
  Botão com Múltiplos Efeitos
</button>

<!-- Focus com Ring -->
<input type="text" class="
  border 
  rounded 
  px-4 
  py-2
  focus:outline-none 
  focus:ring-2 
  focus:ring-blue-500 
  focus:border-transparent
">
```

### Animações
```html
<!-- Fade In -->
<div class="
  opacity-0 
  hover:opacity-100 
  transition-opacity 
  duration-300
">
  Conteúdo com Fade
</div>

<!-- Slide e Fade -->
<div class="
  transform 
  translate-y-4 
  opacity-0
  hover:translate-y-0 
  hover:opacity-100 
  transition 
  duration-300
">
  Conteúdo com Slide e Fade
</div>
```

### Dark Mode
```html
<!-- Suporte a Dark Mode -->
<div class="
  bg-white 
  dark:bg-gray-800 
  text-gray-900 
  dark:text-white
">
  <h1 class="text-2xl font-bold">
    Título Adaptável
  </h1>
  <p class="text-gray-600 dark:text-gray-300">
    Conteúdo que se adapta ao tema escuro
  </p>
</div>
```

## Considerações de Performance

1. **Purge CSS em Produção**
```js
// tailwind.config.js
module.exports = {
  purge: [
    './src/**/*.html',
    './src/**/*.jsx',
    './src/**/*.js',
    './src/**/*.tsx',
    './src/**/*.ts',
  ],
  // ... outras configurações
}
```

2. **Agrupamento de Classes**
```html
<!-- Ruim: Repetição de classes -->
<div class="bg-blue-500 p-4 mb-4">
  <button class="bg-blue-500 p-4 mb-4">Botão 1</button>
  <button class="bg-blue-500 p-4 mb-4">Botão 2</button>
</div>

<!-- Bom: Usando componentes ou @apply -->
<!-- styles.css -->
.btn-primary {
  @apply bg-blue-500 p-4 mb-4;
}

<!-- HTML -->
<div class="btn-primary">
  <button class="btn-primary">Botão 1</button>
  <button class="btn-primary">Botão 2</button>
</div>
```

3. **Lazy Loading com Classes Condicionais**
```html
<div class="
  /* Classes base sempre carregadas */
  bg-white p-4 rounded-lg
  
  /* Classes carregadas apenas em telas maiores */
  md:flex md:space-x-4
  lg:max-w-4xl lg:mx-auto
">
  <!-- Conteúdo -->
</div>
```

## Boas Práticas

### 1. Organização de Classes

```html
<!-- Ruim: Classes misturadas -->
<div class="p-4 hover:bg-blue-600 flex bg-blue-500 items-center rounded text-white justify-between">

<!-- Bom: Classes organizadas por categoria -->
<div class="
  /* Layout */
  flex items-center justify-between
  
  /* Espaçamento */
  p-4
  
  /* Visual */
  bg-blue-500
  rounded
  text-white
  
  /* Estados */
  hover:bg-blue-600
">
```

### 2. Componentização

```html
<!-- Componente Base -->
<button class="
  /* Classes base */
  px-4 
  py-2 
  rounded 
  font-medium 
  focus:outline-none 
  focus:ring-2 
  transition
  
  /* Variantes */
  ${variant === 'primary' && 'bg-blue-500 text-white hover:bg-blue-600'}
  ${variant === 'secondary' && 'bg-gray-200 text-gray-800 hover:bg-gray-300'}
  ${variant === 'danger' && 'bg-red-500 text-white hover:bg-red-600'}
">
  <!-- Conteúdo do botão -->
</button>
```

### 3. Responsividade Progressiva

```html
<!-- Abordagem mobile-first -->
<div class="
  /* Mobile (padrão) */
  w-full 
  p-4
  
  /* Tablet */
  md:w-1/2 
  md:p-6
  
  /* Desktop */
  lg:w-1/3 
  lg:p-8
  
  /* Large Desktop */
  xl:w-1/4 
  xl:p-10
">
```

### 4. Reutilização de Padrões

```html
<!-- Definindo padrões consistentes -->
<div class="space-y-4"> <!-- Container com espaçamento vertical consistente -->
  <!-- Card com padrão consistente -->
  <div class="bg-white rounded-lg shadow-md p-6">
    <h2 class="text-xl font-bold mb-4">Título 1</h2>
    <p class="text-gray-600">Conteúdo 1</p>
  </div>
  
  <div class="bg-white rounded-lg shadow-md p-6">
    <h2 class="text-xl font-bold mb-4">Título 2</h2>
    <p class="text-gray-600">Conteúdo 2</p>
  </div>
</div>
```

### 5. Acessibilidade

```html
<!-- Exemplo de card acessível -->
<div 
  role="article"
  class="
    bg-white 
    rounded-lg 
    shadow-md 
    p-6
    focus-within:ring-2 
    focus-within:ring-blue-500
  "
>
  <h2 id="card-title" class="text-xl font-bold mb-4">Título Acessível</h2>
  <p aria-labelledby="card-title" class="text-gray-600">
    Conteúdo relacionado ao título.
  </p>
  <button 
    aria-label="Ler mais sobre o título"
    class="
      mt-4 
      px-4 
      py-2 
      bg-blue-500 
      text-white 
      rounded
      hover:bg-blue-600
      focus:outline-none 
      focus:ring-2 
      focus:ring-offset-2 
      focus:ring-blue-500
    "
  >
    Ler mais
  </button>
</div>
```

## Dicas de Debug

1. **Outline para Visualização**
```html
<div class="outline outline-1 outline-red-500">
  <!-- O outline ajuda a visualizar as dimensões do elemento -->
</div>
```

2. **Background Colorido para Debug**
```html
<div class="bg-red-200">
  <!-- Background colorido para identificar áreas -->
</div>
```

3. **Classes de Debug do Tailwind**
```html
<!-- Adicione ao seu HTML durante o desenvolvimento -->
<div class="debug-screens">
  <!-- Mostra o breakpoint atual -->
</div>
```

## Recursos Adicionais

1. **Plugins Recomendados**
   - `@tailwindcss/forms`: Estilos de formulário melhorados
   - `@tailwindcss/typography`: Estilos de tipografia para conteúdo rico
   - `@tailwindcss/aspect-ratio`: Helpers para relação de aspecto
   - `@tailwindcss/line-clamp`: Truncamento de texto multi-linha

2. **Extensões VSCode**
   - Tailwind CSS IntelliSense
   - Headwind (ordenação de classes)
   - PostCSS Language Support

3. **Ferramentas Online**
   - Tailwind Play (playground online)
   - Tailwind UI (componentes premium)
   - Tailwind Components (comunidade)
