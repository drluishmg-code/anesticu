# Site institucional — AnestICU

Site estático (HTML + CSS + JS puro, sem frameworks, sem build) pronto para publicação no **GitHub Pages**.

## Estrutura

```
├── index.html          → página principal
├── privacy.html         → Política de Privacidade
├── terms.html            → Termos de Uso
├── contact.html          → Contato
├── style.css             → todos os estilos (tokens de cor/tipografia no topo)
├── script.js              → menu mobile, carrossel, animações de scroll, botão "voltar ao topo"
├── manifest.json          → metadados PWA
├── robots.txt
├── sitemap.xml
└── assets/
    ├── logo.png           → logo do app (usado no header, rodapé e logo.png)
    ├── logo.png.svg
    └── screenshots/       → pasta reservada para as capturas reais do app
```

## Antes de publicar — o que trocar

1. **Domínio real**: troque `https://drluishmg-code.github.io/anesticu` por seu domínio definitivo em:
   - `index.html`, `privacy.html`, `terms.html`, `contact.html` (tags `canonical` e Open Graph)
   - `robots.txt` e `sitemap.xml`

2. **E-mail de contato**: em `contact.html`, troque `drluishmg@gmail.com` pelo e-mail real.

3. **Instagram**: troque os links `https://instagram.com/anesticu` (aparecem em `contact.html` e nos rodapés de todas as páginas) pelo perfil real.

4. **Link da App Store**: os botões "Baixar na App Store" (em `index.html`) usam `href="#"` como placeholder. Assim que o app for publicado, troque pelo link real da App Store.

5. **Capturas de tela reais**: a seção "Capturas" usa mockups em CSS/HTML como placeholder (fáceis de reconhecer e substituir). Para usar screenshots reais:
   - Exporte 8 capturas do app (proporção iPhone, ex. 1170×2532px), salve em `assets/screenshots/01.png` a `08.png`.
   - Em `index.html`, dentro de cada `.phone-mock`, substitua o conteúdo de `.phone-screen` por `<img src="assets/screenshots/01.png" alt="Tela de protocolos do AnestICU" loading="lazy" />` (repita para as demais).

6. **Ícone de app (logo.png/apple-touch-icon)**: o projeto usa um ícone SVG (`assets/logo.png.svg`), compatível com a maioria dos navegadores modernos. Se quiser garantir suporte total (inclusive navegadores mais antigos), gere também `logo.png.ico` (32×32) e `apple-touch-icon.png` (180×180) a partir do mesmo logo, e adicione as tags correspondentes no `<head>`.

7. **Imagem de compartilhamento (Open Graph)**: as tags `og:image`/`twitter:image` apontam para `assets/social-preview.png` (1200×630px) — adicione esse arquivo em `assets/`.

## Publicando no GitHub Pages

1. Crie um repositório no GitHub e envie todos os arquivos deste diretório para a raiz (ou para a pasta `/docs`, se preferir).
2. Em **Settings → Pages**, selecione a branch (ex. `main`) e a pasta (`/root` ou `/docs`).
3. O GitHub Pages publicará o site automaticamente em `https://usuario.github.io/repositorio/`.
4. Se estiver usando um domínio próprio, adicione um arquivo `CNAME` na raiz com o domínio desejado e configure o DNS (registro CNAME apontando para `usuario.github.io`).

Nenhuma instalação, `npm install` ou processo de build é necessário — o site funciona apenas abrindo `index.html`.

## Compatibilidade

Testado visualmente para funcionar em Safari, Chrome, Edge e Firefox, em iPhone, iPad, Mac e Windows. O layout é totalmente responsivo (mobile → desktop) e respeita a preferência de "reduzir movimento" do sistema operacional.

## Personalização de cores e tipografia

Todos os tokens de design (cores, espaçamentos, raios, fontes) estão centralizados no topo de `style.css`, na seção `:root`. Alterar esses valores atualiza o site inteiro de forma consistente.
