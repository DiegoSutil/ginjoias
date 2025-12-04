# Gin Pratas - Site de Joias em Prata Italiana

Este projeto foi adaptado de um site de perfumes para criar uma loja online de joias em prata italiana, inspirado no design do site **Gin Prata**.

## 🎨 Características do Design

### Paleta de Cores
- **Fundo Principal**: Preto (#000000) - elegância e sofisticação
- **Texto Primário**: Branco (#FFFFFF)
- **Destaques e CTAs**: Vermelho (#ef4444) - urgência e destaque
- **Elementos Secundários**: Cinza escuro (#1a1a1a, #333) para cards

### Estilo Visual
- **Dark Theme**: Fundo preto com elementos claros para alto contraste
- **Tipografia**: 
  - Inter (sans-serif) para texto geral
  - Playfair Display (serif) para títulos
- **Animações**: Hover effects, transições suaves, AOS (Animate on Scroll)
- **Layout Responsivo**: Mobile-first design com Tailwind CSS

## 📦 Estrutura do Projeto

```
joias-imperio/
├── index.html          # Página principal
├── admin.html          # Painel administrativo
├── checkout.html       # Página de checkout
├── sobre.html          # Página sobre nós
├── images/             # Diretório de imagens
├── js/                 # Scripts JavaScript
│   ├── script.js
│   ├── cart.js
│   ├── auth.js
│   └── ...
├── admin/              # Área administrativa
│   ├── css/
│   └── js/
└── README.md           # Este arquivo
```

## 🚀 Como Usar

### Visualização Local

1. Abra o arquivo `index.html` diretamente no navegador
2. Ou use um servidor local:
   ```bash
   python3 -m http.server 8000
   ```
   Depois acesse: `http://localhost:8000`

### Personalização

#### Alterar Cores
Edite as variáveis CSS no `<style>` do `index.html`:
```css
.btn-primary {
    background: linear-gradient(90deg, #ef4444 0%, #dc2626 100%);
}
```

#### Adicionar Produtos
Os produtos estão hardcoded no HTML. Para adicionar novos produtos, copie e modifique as divs com classe `.product-card`:
```html
<div class="product-card rounded-lg overflow-hidden group">
    <!-- Conteúdo do produto -->
</div>
```

#### Alterar Imagens
As imagens atuais são do Unsplash. Substitua as URLs pelas suas próprias imagens:
```html
<img src="SUA_IMAGEM_AQUI" alt="Descrição">
```

## 🎯 Seções Principais

1. **Hero Section**: Banner principal com promoção em destaque
2. **Promoção**: Grid de produtos em promoção
3. **Categorias**: Cards grandes com categorias de joias
4. **Benefícios**: Ícones com diferenciais da loja
5. **Footer**: Informações de contato e links úteis

## 📱 Categorias de Produtos

- Correntes
- Pulseiras
- Conjuntos
- Anéis
- Brincos
- Pingentes

## 🛠️ Tecnologias Utilizadas

- **HTML5**: Estrutura semântica
- **Tailwind CSS**: Framework CSS utility-first
- **JavaScript**: Interatividade
- **Feather Icons**: Ícones SVG
- **AOS Library**: Animações on scroll
- **Google Fonts**: Tipografia (Inter & Playfair Display)

## 🎨 Inspiração de Design

O design foi inspirado no site **Gin Prata** (imperiodasprata.com), adaptando os seguintes elementos:

- Esquema de cores dark (preto + vermelho)
- Layout de produtos em grid
- Hero section com promoção em destaque
- Cards de categoria com overlay
- Badges de desconto e benefícios
- Tipografia bold e impactante

## 📝 Próximos Passos

Para tornar o site funcional, você precisará:

1. **Backend**: Implementar servidor para gerenciar produtos
2. **Banco de Dados**: Armazenar produtos, pedidos e usuários
3. **Carrinho**: Funcionalidade completa de e-commerce
4. **Pagamento**: Integração com gateway de pagamento
5. **Autenticação**: Sistema de login e cadastro
6. **Admin**: Painel para gerenciar produtos e pedidos

## 📄 Licença

Este é um projeto de demonstração. Adapte conforme necessário para seu uso.

---

**Desenvolvido com base no template Sansei Decants, adaptado para Gin Pratas**
