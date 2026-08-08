# Inserir QR, Texto ou Formas em PDF

Ferramenta web para inserir QR codes, textos variáveis e formas (retângulos coloridos) em arquivos PDF em lote — tudo roda **localmente no navegador**, sem backend, sem upload de dados para nenhum servidor.

🔗 **Demo:** https://MatheusQuadros.github.io/overplace-pdf-QR-serializer/

## O que faz

- Carrega um PDF base e posiciona visualmente (arrastando) até:
  - 1 QR code
  - 5 caixas de texto variável
  - 5 retângulos coloridos (para tapar logos/áreas ou pintar fundos)
- Gera os dados variáveis de 3 formas: seriais automáticos, lista colada, ou CSV
- Aplica em uma página ou em todas as páginas do PDF
- Exporta como:
  - vários PDFs em um `.zip`
  - um único PDF mesclado (todas as páginas/registros)
  - um único PDF fixo, sem dados variáveis (ex.: só tapar um logo)

## Como usar

1. Abra o `index.html` no navegador (ou acesse a demo acima)
2. Suba o PDF base
3. Posicione QR, textos e formas arrastando na prévia
4. Configure a origem dos dados (seriais / lista / CSV) e o template do QR
5. Escolha o formato de saída e gere

Nenhum arquivo é enviado a servidores — todo o processamento (leitura do PDF, geração do QR, montagem do ZIP) acontece no seu navegador via JavaScript.

## Stack

- [pdf.js](https://mozilla.github.io/pdf.js/) — renderização da prévia do PDF
- [pdf-lib](https://pdf-lib.js.org/) — edição/geração do PDF final
- [qrcode-generator](https://github.com/kazuhikoarase/qrcode-generator) — geração dos QR codes
- [JSZip](https://stuk.github.io/jszip/) — empacotamento em `.zip`

Todas as libs são carregadas via CDN (jsDelivr) — sem `npm install`, sem build step.

## Rodando localmente

Como é um único arquivo HTML, basta abrir `index.html` no navegador. Se o navegador bloquear alguma coisa por política de arquivo local, sirva com um servidor simples:

```bash
python3 -m http.server 8000
# depois acesse http://localhost:8000
```

## Licença

Livre para uso, cópia, modificação e distribuição, sem necessidade de mencionar o autor — veja [LICENSE](LICENSE).
