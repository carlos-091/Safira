# Safira Jóias - Landing Page

Este é um site institucional de página única (Landing Page) focado em divulgação direta de produtos de alto padrão e conversão através do WhatsApp. O projeto foi desenvolvido com foco em performance máxima, código minimalista e abordagem *Mobile-First*.

## 🌟 Características do Projeto

- **Página Única (Landing Page):** Estrutura limpa contendo apenas Header, Hero, Vitrine de Produtos e Rodapé.
- **Mobile-First:** Design totalmente otimizado para navegação intuitiva em smartphones por usuários leigos.
- **Foco em Conversão:** Sem carrinhos, cadastros ou formulários complexos. Cada produto possui um link direto que abre o WhatsApp com uma mensagem personalizada do item de interesse.
- **Paleta de Cores Rígida:** Branco, Preto e Dourado.

## 📁 Estrutura de Arquivos

O repositório está estruturado de forma simples e sem dependências de frameworks (HTML e CSS puros):


```
Safira/
│
├── index.html      # Estrutura e conteúdo da Landing Page
├── style.css       # Estilização completa e variáveis de design
└── Safira.jpeg     # Logotipo oficial da marca
```

## 🛠️ Detalhes Técnicos e Integração do Logo

O logotipo `Safira.jpeg` possui um fundo preto sólido. Para que ele se integre perfeitamente ao layout sem a necessidade de edição de imagem, foram aplicadas duas soluções técnicas:

1. **Preto Puro:** A variável `--black` no arquivo `style.css` está configurada como `#000000` para coincidir exatamente com o fundo do arquivo JPEG.
2. **Modo de Mesclagem:** No CSS, as classes `.header-logo` e `.footer-logo` utilizam a propriedade `mix-blend-mode: screen;`. Isso instrui o navegador a neutralizar a cor preta da imagem, exibindo apenas as partes claras (texto e diamantes dourados/brancos) de forma transparente sobre o fundo.

## 🚀 Como Fazer Alterações

### 1. Adicionar ou Editar Produtos
Para alterar os produtos da vitrine, localize a seção `` no arquivo `index.html`. Cada produto é encapsulado por uma tag `<article class="card">`. 

Ao atualizar o preço ou nome do produto, lembre-se de atualizar também o texto do link do WhatsApp no atributo `href`:
```html
<a class="btn-whatsapp" href="[https://wa.me/556796470917?text=Olá](https://wa.me/556796470917?text=Olá)! Tenho interesse no *Novo Produto* (R$ XX,XX)" target="_blank" rel="noopener">
```

### 2. Alterar o Número do WhatsApp

Atualmente, os links de conversão estão apontando para o número institucional configurado no código (`556796470917`). Caso o cliente mude de número, basta fazer uma busca global por este número nos arquivos e substituí-lo pelo novo (mantendo o código do país `55` e o DDD).

### 3. Ajustar Cores e Fontes

Todas as configurações de design estão centralizadas em variáveis no topo do arquivo `style.css` dentro do seletor `:root`. Se precisar ajustar os tons de dourado ou espaçamentos, modifique diretamente ali:

```css
:root {
  --black:      #000000;
  --gold:       #C9A84C;
  --font-body:    'Inter', system-ui, sans-serif;
  /* ... */
}
```

## 📈 Boas Práticas para Manutenção

* **Performance:** Mantenha o carregamento preguiçoso (`loading="lazy"`) em todas as imagens de novos produtos adicionados à vitrine.
* **Animações:** Caso decida adicionar novas interações, respeite a diretiva `@media (prefers-reduced-motion: reduce)` já configurada no CSS para garantir a acessibilidade de usuários que desativaram animações no sistema operacional.
* **Simplicidade:** Evite incluir bibliotecas externas ou frameworks pesados para garantir que a página continue abrindo instantaneamente em redes móveis 3G/4G.