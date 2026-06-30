# AI Executive Portrait System™ — Página de Vendas

Landing page de vendas (arquivo único, autossuficiente) já configurada com checkout do **Hotmart** em overlay, contador regressivo, popup de notificações de compra e slots de rastreamento (Pixel da Meta + GA4).

---

## 🚀 Publicar no GitHub Pages (passo a passo)

1. Crie um repositório novo no GitHub (ex.: `pagina-ai-executive`).
2. Envie **todos os arquivos desta pasta** para o repositório (incluindo `index.html`).
3. No repositório, vá em **Settings → Pages**.
4. Em **Source**, selecione a branch **`main`** e a pasta **`/ (root)`** e clique em **Save**.
5. Aguarde ~1 minuto. O GitHub vai gerar o endereço:
   `https://SEU-USUARIO.github.io/NOME-DO-REPOSITORIO/`
6. Pronto — a página está no ar. 🎉

> Dica: para enviar pelo navegador, use **Add file → Upload files**, arraste todos os arquivos e clique em **Commit changes**.

---

## ⚙️ Configuração (edite no topo do `<script>`, no fim do `index.html`)

```js
const CONFIG = {
  checkoutUrl: "https://pay.hotmart.com/G106551026C",  // seu checkout Hotmart
  hotmartOverlay: true,   // true: checkout em overlay na página · false: redireciona
  ofertaAte: "",          // "" = contador de 24h por visitante · "2026-12-31T23:59:59" = data fixa
  timerHoras: 24,         // duração do contador (modo por visitante)
  salesPop: true,         // popup de notificações de compra
  salesPopSom: true,      // som de caixa registradora
  metaPixelId: "",        // ID do Pixel da Meta (ex.: "1234567890123456") · "" = desativado
  ga4Id: ""               // ID do Google Analytics 4 (ex.: "G-XXXXXXX") · "" = desativado
};
```

- **Checkout já configurado** — o link do Hotmart está embutido; os botões abrem o checkout em overlay.
- **Rastreamento (tráfego pago):** cole `metaPixelId` e/ou `ga4Id` para medir conversões. Ao clicar em comprar, a página dispara `InitiateCheckout` (Meta) e `begin_checkout` (GA4).
- **Importante:** confirme no Hotmart que o **preço do produto é R$47**, para bater com a página.

---

## 🌐 Domínio personalizado (opcional)

Se você tem um domínio próprio (ex.: `suamarca.com.br`):

1. Crie um arquivo chamado **`CNAME`** (sem extensão) na raiz do repositório, contendo só o domínio:
   ```
   suamarca.com.br
   ```
2. No seu provedor de domínio, aponte o DNS para o GitHub Pages (registros `A` para os IPs do GitHub ou um `CNAME` para `SEU-USUARIO.github.io`).
3. Em **Settings → Pages → Custom domain**, informe o domínio e ative **Enforce HTTPS**.

---

## 📁 Arquivos

| Arquivo | Função |
|---|---|
| `index.html` | A página de vendas completa (tudo embutido: imagens, CSS, JS) |
| `404.html` | Redireciona qualquer caminho inválido para a página principal |
| `.nojekyll` | Faz o GitHub Pages servir os arquivos como estão (sem processamento) |
| `robots.txt` | Permite indexação pelos buscadores |
| `README.md` | Este guia |

---

© 2026 AI Executive Portrait System™ · @marquin017
