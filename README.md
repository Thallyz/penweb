# 🌐 PenWeb — Landing Page

Site oficial do **PenWeb** (extensão para Chrome). Página estática em HTML + CSS puros,
pronta para hospedar **de graça** no **GitHub Pages**.

## 📁 Estrutura

```
penweb-site/
├── index.html          ← página principal
├── privacidade.html    ← política de privacidade (use esta URL na Chrome Web Store)
├── ofertas.json        ← ofertas remotas do letreiro da extensão (edite aqui!)
├── css/
│   └── style.css       ← todo o estilo
└── img/
    ├── banner.png      ← banner para redes sociais / Open Graph
    └── poster.png      ← cartaz usado no hero e como favicon
```

---

## 🚀 Como hospedar no GitHub Pages (passo a passo para iniciantes)

> Sua conta no GitHub é **Thallyz**. O site vai ficar em:
> `https://thallyz.github.io/penweb/`

### Passo 1 — Criar o repositório
1. Acesse https://github.com e clique em **New repository** (canto superior direito, ícone `+`).
2. Em **Repository name** digite: `penweb`
3. Deixe marcado **Public** (obrigatório para o GitHub Pages gratuito).
4. **Não** marque "Add a README" (vamos subir os arquivos prontos).
5. Clique em **Create repository**.

### Passo 2 — Enviar os arquivos
Na tela do repositório vazio, clique em **uploading an existing file** (ou em *Add file → Upload files*).
1. Arraste para a janela **todo o conteúdo da pasta `penweb-site`**:
   - `index.html`
   - `privacidade.html`
   - a pasta `css/` (com o `style.css` dentro)
   - a pasta `img/` (com `banner.png` e `poster.png` dentro)
2. Espere terminar o upload.
3. Em **Commit changes**, escreva algo como `Publica landing page do PenWeb` e clique em **Commit changes**.

> 💡 O GitHub aceita arrastar pastas inteiras. Certifique-se de que `css` e `img`
> foram como **pastas**, não como arquivos soltos.

### Passo 3 — Ativar o GitHub Pages
1. No repositório, clique na aba **Settings** (Configurações).
2. No menu lateral esquerdo, clique em **Pages**.
3. Em **Build and deployment → Source**, selecione **Deploy from a branch**.
4. Em **Branch**, escolha **`main`** e a pasta **`/ (root)`**. Clique em **Save**.
5. Aguarde ~1 minuto. Recarregue a página de *Settings → Pages*: no topo aparecerá
   a mensagem verde com o link do seu site:
   **`https://thallyz.github.io/penweb/`** 🎉

### Passo 4 — Testar
Abra o link no navegador. Se algo parecer sem estilo, espere 1–2 minutos e recarregue
(o GitHub Pages demora um pouco para publicar a primeira versão).

---

## 🔗 Onde usar este site

- **Chrome Web Store** → campo *Privacy policy URL*: cole
  `https://thallyz.github.io/penweb/privacidade.html`
- **Divulgação** (fóruns, Reddit, Product Hunt) → link do site principal.
- **Bio do GitHub** → coloque o link do site para dar credibilidade.

---

## ⚙️ Ajustes que você pode querer fazer

### 1. Link da lista de espera (PenWeb AI) — já configurado ✅
O botão "Entrar na lista de espera" do `index.html` já aponta para o Google Forms
"Lista de espera — PenWeb AI". Para trocar no futuro, edite o `href` desse botão
no `index.html` (procure por `docs.google.com/forms`).

### 2. Trocar as ofertas de afiliado SEM atualizar a extensão
As ofertas do letreiro dentro da extensão agora vêm do arquivo **`ofertas.json`**
deste repositório. Para adicionar/trocar uma oferta:
1. Abra `ofertas.json` aqui no GitHub e clique no lápis (editar).
2. Adicione um objeto com `emoji`, `texto`, `cta` e `link` (seu link de afiliado).
3. Faça o commit. Pronto: em até **6 horas** (cache) todas as instalações do
   PenWeb passam a mostrar a oferta nova — **sem publicar versão nova na loja**.
   (Se a rede falhar, a extensão usa a lista embutida de fallback.)

Os cards de recomendação do site também podem ser editados em `index.html`,
na seção `id="recomendacoes"`. Mantenha o aviso de divulgação — é exigência
legal e dá credibilidade.

### 3. Domínio próprio (penweb.com) — no futuro
Quando comprar o domínio:
1. **Settings → Pages → Custom domain** → digite `penweb.com` → Save.
2. No painel do registrador (onde comprou o domínio), crie um **CNAME** apontando
   `penweb.com` e `www` para `thallyz.github.io`.
3. Marque **Enforce HTTPS** depois que o certificado for gerado (leva alguns minutos).

### 4. Adsterra / anúncios — SIM, aqui pode!
Este site é **seu**, então aqui você **pode** colocar um snippet do Adsterra
(ou Google AdSense) **legalmente**, sem risco para a extensão. Basta colar o
`<script>` do Adsterra antes de `</body>` no `index.html`.

> ⚠️ **Nunca** coloque Adsterra dentro da extensão (`content.js`) — isso viola a
> política da Chrome Web Store e pode banir sua conta. No site próprio, tudo bem.

---

## 🖌️ Personalização rápida

Todas as cores estão nas variáveis no topo do `css/style.css`:

```css
:root {
  --fundo: #1f2430;      /* fundo principal */
  --primaria: #ffd441;   /* amarelo dos botões e destaques */
  ...
}
```

Mude os valores e salve — o site inteiro se ajusta.

---

Feito com dedicação no Brasil 🇧🇷 · [PenWeb na Chrome Web Store](https://chromewebstore.google.com/detail/mmbhcihaiiamenkcagobpnkopbhdcmppd)
