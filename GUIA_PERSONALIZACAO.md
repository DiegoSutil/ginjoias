# 📝 Guia de Personalização - Gin Pratas

Este guia vai te ajudar a personalizar o site de acordo com suas necessidades.

## 🎨 Alterando as Cores

### Cor Principal (Vermelho)
Para mudar a cor vermelha dos destaques, procure por `#ef4444` e `#dc2626` no arquivo `index.html` e substitua por sua cor preferida.

**Onde encontrar:**
```css
/* No <style> do index.html */
.btn-primary {
    background: linear-gradient(90deg, #ef4444 0%, #dc2626 100%);
}
```

### Cor de Fundo
O fundo é preto (`#000000`). Para alterar:
```css
body {
    background-color: #000000; /* Mude aqui */
}
```

## 📸 Substituindo Imagens

### Imagens de Produtos
As imagens atuais são do Unsplash. Substitua as URLs:

```html
<!-- Exemplo de produto -->
<img src="https://images.unsplash.com/photo-..." alt="Produto">

<!-- Substitua por: -->
<img src="images/seu-produto.jpg" alt="Produto">
```

**Dica:** Coloque suas imagens na pasta `images/` do projeto.

### Imagens de Categorias
Mesma lógica para as categorias:
```html
<img src="https://images.unsplash.com/photo-..." alt="Correntes">
```

## 🛍️ Adicionando Novos Produtos

Copie este bloco e modifique os valores:

```html
<div class="product-card rounded-lg overflow-hidden group">
    <div class="relative bg-black p-6 h-64 flex items-center justify-center">
        <span class="absolute top-4 left-4 bg-red-500 text-white text-xs font-bold px-3 py-1 rounded-full">-25%</span>
        <img src="images/seu-produto.jpg" alt="Nome do Produto" class="h-full w-auto object-contain">
    </div>
    <div class="p-4">
        <h3 class="text-sm font-semibold text-white mb-2">Nome do Produto - Prata Italiana</h3>
        <div class="flex items-center gap-2 mb-2">
            <span class="text-gray-400 line-through text-sm">R$ 200,00</span>
            <span class="text-red-500 font-bold text-lg">R$ 150,00</span>
        </div>
        <p class="text-green-400 text-xs font-semibold mb-3">R$ 142,50 com Pix</p>
        <button class="w-full bg-gray-800 hover:bg-red-500 text-white font-semibold py-2 px-4 rounded-full transition-all duration-300">Comprar</button>
    </div>
</div>
```

## 📝 Alterando Textos

### Banner Principal
```html
<h1 class="font-heading text-5xl md:text-7xl font-bold text-white leading-tight mb-6">
    O MENOR PREÇO<br><span class="text-red-500">DO ANO!</span>
</h1>
```

### Barra de Promoção (Topo)
```html
<p>🔥 ANTECIPA BLACK: ATÉ 40% OFF + 5% DE DESCONTO NO PIX | FRETE GRÁTIS E ATÉ 5X SEM JUROS</p>
```

### Seção de Benefícios
```html
<h3 class="font-bold text-xl text-white mb-2">100% Prata Italiana</h3>
<p class="text-gray-400 text-sm leading-relaxed">Todas as nossas peças são confeccionadas em prata italiana 925 certificada.</p>
```

## 🔗 Adicionando Novas Categorias

Para adicionar uma nova categoria no menu:

```html
<li>
    <a href="#nova-categoria" class="nav-link font-semibold text-gray-300 hover:text-white transition-colors duration-300 relative py-2 px-3 block">
        NOVA CATEGORIA
    </a>
</li>
```

E no grid de categorias:

```html
<a href="#nova-categoria" class="category-card block h-80 relative group overflow-hidden rounded-lg">
    <img src="images/nova-categoria.jpg" alt="Nova Categoria" class="w-full h-full object-cover transition-transform duration-500 group-hover:scale-110">
    <div class="absolute inset-0 flex flex-col items-center justify-center z-10">
        <h3 class="font-heading text-4xl font-bold text-white mb-2">NOVA CATEGORIA</h3>
        <p class="text-white/90 font-semibold">VER MAIS...</p>
    </div>
</a>
```

## 📱 Informações de Contato (Footer)

```html
<li class="flex items-center gap-2">
    <i data-feather="mail" class="w-4 h-4"></i> seuemail@exemplo.com.br
</li>
<li class="flex items-center gap-2">
    <i data-feather="phone" class="w-4 h-4"></i> (11) 99999-9999
</li>
<li class="flex items-center gap-2">
    <i data-feather="instagram" class="w-4 h-4"></i> @seuinstagram
</li>
```

## 🎯 Dicas Importantes

### 1. Sempre faça backup
Antes de fazer alterações, copie o arquivo original.

### 2. Teste em diferentes dispositivos
O site é responsivo, mas sempre teste em:
- Desktop
- Tablet
- Celular

### 3. Otimize as imagens
- Use formatos modernos (WebP, AVIF)
- Comprima as imagens antes de usar
- Tamanho recomendado: 800x800px para produtos

### 4. Mantenha a consistência
- Use sempre as mesmas cores
- Mantenha o padrão de nomenclatura
- Siga a estrutura existente

## 🚀 Próximos Passos

Para tornar o site funcional, você precisará:

1. **Integrar com backend** (Node.js, PHP, Python, etc.)
2. **Adicionar banco de dados** (MySQL, PostgreSQL, MongoDB)
3. **Implementar carrinho de compras** funcional
4. **Integrar gateway de pagamento** (Mercado Pago, PagSeguro, Stripe)
5. **Sistema de autenticação** (login/cadastro)
6. **Painel administrativo** para gerenciar produtos
7. **Sistema de envio de e-mails**
8. **Integração com correios** para cálculo de frete

## 📚 Recursos Úteis

- **Tailwind CSS**: https://tailwindcss.com/docs
- **Feather Icons**: https://feathericons.com/
- **AOS Library**: https://michalsnik.github.io/aos/
- **Unsplash (Imagens)**: https://unsplash.com/

## 💡 Suporte

Se precisar de ajuda adicional, consulte:
- Documentação do Tailwind CSS
- Stack Overflow
- MDN Web Docs

---

**Boa sorte com seu projeto! 🚀**
