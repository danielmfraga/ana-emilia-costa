# Ana Emilia Costa — Site

Landing page editorial para a Ana Emilia Costa, psicóloga clínica e
psicoterapeuta. Site estático em HTML/CSS/JS puros, sem dependências
de build.

## Estrutura

```
site/
├── index.html         — o CARTÃO (a página inicial do domínio; noindex)
├── emconstrucao.html  — o site completo, enquanto não fica pronto
│                        (em /emconstrucao; noindex, sem link de lugar nenhum)
├── assets/
│   └── ana.jpg        — retrato da Ana
├── README.md
├── .gitignore
└── vercel.json        — URLs limpas, /cartao → /, cabeçalho noindex do /emconstrucao
```

> **Estado atual (nov/2026):** o site ainda não está pronto, então o domínio
> mostra só o cartão. Para lançar o site: troque os nomes (`index.html` →
> `cartao.html`, `emconstrucao.html` → `index.html`), tire o `noindex` da
> página nova e o redirecionamento/cabeçalho do `vercel.json`.

## Como rodar localmente

Não há build. Basta servir o diretório com qualquer servidor estático:

```bash
# opção 1 — Python
python3 -m http.server 8080

# opção 2 — Node (npx)
npx serve .

# opção 3 — VS Code: extensão "Live Server"
```

Abra `http://localhost:8080` no navegador.

## Deploy

### Vercel (recomendado, gratuito)

1. Faça push do repositório para o GitHub.
2. Em [vercel.com](https://vercel.com), clique em **Add New → Project**
   e selecione o repositório.
3. Mantenha as configurações padrão (a Vercel detecta como estático
   automaticamente) e clique **Deploy**.
4. Para domínio customizado (ex.: `anaemiliacosta.com`), vá em
   **Settings → Domains** dentro do projeto.

### Netlify

1. Push para o GitHub.
2. Em [netlify.com](https://netlify.com), **Add new site → Import an
   existing project** → selecione o repo.
3. Build command: vazio. Publish directory: `./` (raiz).

### GitHub Pages

1. Repositório → **Settings → Pages**.
2. Source: **Deploy from a branch**, branch `main`, pasta `/ (root)`.
3. Aguarde alguns minutos. O endereço será
   `https://<seu-usuario>.github.io/<nome-do-repo>/`.

## Fontes

O site carrega **Archivo** e **Newsreader** do Google Fonts via
`<link>` no `<head>`. Não é preciso hospedar nada.

## Conteúdo a substituir

- **Foto** — `assets/ana.jpg` (atual: foto da Ana lendo Freud)
- **WhatsApp** — em `emconstrucao.html`, o link
  `https://wa.me/5500000000000` é placeholder. Substituir pelo número
  real, formato internacional sem `+` ou espaços (ex.:
  `5532999998888`).
- **Bio** — o parágrafo curto na seção "Quem sou" é provisório.

## Cor de acento

A paleta usa terracota (`#B45414`) como acento. Para trocar, basta
alterar a variável `--accent` no topo do `<style>` em `emconstrucao.html`.
Sugestões testadas: tijolo `#9A3216`, mostarda `#8E6F08`, musgo
`#5C6622`, grafite `#3A352D`.

## Formulário "Receba um contato" (cartão)

No último cartão, o botão **Receba um contato** abre um formulário (nome, WhatsApp
e mensagem opcional). **Ainda não grava em planilha**: enquanto a constante
`FORM_ENDPOINT` (no fim do `index.html`) estiver vazia, o envio abre o WhatsApp da Ana
com a mensagem pronta, então o contato não se perde. Para ligar o Google Planilhas:
crie a planilha, cole o código do Apps Script (está comentado junto da constante),
publique como App da Web ("Qualquer pessoa") e cole a URL `/exec` em `FORM_ENDPOINT`.

## Licença

© 2026 Ana Emilia Costa. Todos os direitos reservados.
