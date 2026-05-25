# Honda Consórcio — WebAR Experience
## Hondinho & Hondinha · Mind AR · GitHub Pages

---

## Estrutura do projeto

```
honda-ar/
├── index.html          ← experiência completa
├── assets/
│   ├── targets.mind    ← marcador compilado (você gera — ver abaixo)
│   └── hondinha.mp4    ← vídeo dos personagens
└── README.md
```

---

## PASSO 1 — Gerar o arquivo de marcador (.mind)

O Mind AR precisa compilar a imagem âncora (logo/capa do PDF) em um arquivo `.mind`.

**Ferramenta online gratuita:**
👉 https://hiukim.github.io/mind-ar-js-doc/tools/compile

1. Acesse o link acima
2. Clique em **"Upload Image"**
3. Envie a imagem do PDF que será o marcador
   - Use a **capa do PDF** ou o **logo Honda Consórcio**
   - Resolução mínima recomendada: 800px de largura
   - Evite imagens com pouco contraste ou muito simples
4. Clique em **"Compile"**
5. Baixe o arquivo gerado → renomeie para **`targets.mind`**
6. Coloque na pasta `assets/`

**Dica:** imagens com mais detalhes visuais (textura, contraste, bordas) geram rastreamento mais preciso.

---

## PASSO 2 — Colocar o vídeo na pasta assets

Renomeie o arquivo `Hondinha_e_Hondinho_Teste_1.mp4` para **`hondinha.mp4`**
e coloque em `assets/`.

---

## PASSO 3 — Publicar no GitHub Pages

### 3a. Criar repositório

1. Acesse https://github.com/new
2. Nome sugerido: `honda-consorcio-ar`
3. Deixe **Public**
4. Clique em **Create repository**

### 3b. Fazer upload dos arquivos

**Opção simples (sem terminal):**
1. Na página do repositório, clique em **"uploading an existing file"**
2. Arraste todos os arquivos e a pasta `assets/`
3. Clique em **Commit changes**

**Opção via terminal:**
```bash
cd honda-ar/
git init
git add .
git commit -m "Honda AR experience"
git branch -M main
git remote add origin https://github.com/SEU_USUARIO/honda-consorcio-ar.git
git push -u origin main
```

### 3c. Ativar GitHub Pages

1. No repositório → **Settings** → **Pages**
2. Em "Source" selecione **Deploy from a branch**
3. Branch: **main** · Folder: **/ (root)**
4. Clique em **Save**
5. Aguarde ~2 minutos
6. URL final: `https://SEU_USUARIO.github.io/honda-consorcio-ar/`

---

## PASSO 4 — Gerar o QR Code

Use qualquer gerador gratuito:
- https://qr.io
- https://www.qrcode-monkey.com

**URL para o QR Code:**
```
https://SEU_USUARIO.github.io/honda-consorcio-ar/
```

Exporte em SVG ou PNG em alta resolução para inserir no PDF.

---

## Personalização no index.html

No bloco `CONFIG` do `index.html` você pode ajustar:

```javascript
const CONFIG = {
  targetSrc:     'assets/targets.mind',         // não alterar
  videoSrc:      'assets/hondinha.mp4',         // não alterar
  ctaURL:        'https://www.honda.com.br/consorcio', // URL do botão final
  videoDuration: 5000,   // duração do vídeo em ms
  ctaDelay:      4000,   // tempo (ms) até mostrar o botão CTA
};
```

---

## Compatibilidade

| Dispositivo | Navegador | Status |
|---|---|---|
| iPhone (iOS 12+) | Safari | ✅ Funciona |
| Android | Chrome | ✅ Funciona |
| Desktop | Chrome | ✅ Funciona (webcam) |
| iPhone | Chrome iOS | ⚠️ Limitado |

**Recomendação:** Teste primeiro no Safari (iOS) — é o browser nativo do iPhone e tem melhor suporte a WebAR.

---

## Suporte

Projeto desenvolvido por **Grifado Agência de Comunicação**
