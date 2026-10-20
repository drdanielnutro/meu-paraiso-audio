# Meu Paraíso · Narração

Página pública com o tocador da narração do livro, publicada pelo GitHub Pages em:

https://drdanielnutro.github.io/meu-paraiso-audio/

O QR code impresso no livro aponta para esse endereço. **Não renomeie este repositório nem a conta**, senão o QR code deixa de funcionar.

## Arquivos

| Arquivo | O que é |
|---|---|
| `index.html` | O tocador (play/pause, barra de progresso, voltar/avançar 10 s) |
| `narracao.mp3` | A narração do livro (um único arquivo) |
| `capa.jpg` | Foto da capa do livro. Aparece inteira (sem cortes) no topo da página, na tela de bloqueio do celular e na prévia do link no WhatsApp |

Enquanto `narracao.mp3` não existir, a página mostra "A narração estará disponível em breve". Enquanto `capa.jpg` não existir, aparece uma ilustração simples no lugar.

## Enviar ou trocar os arquivos

Add file → Upload files → arraste o arquivo **com exatamente este nome** → Commit changes. Em 1 a 2 minutos a página já mostra a versão nova.

- **Narração:** `narracao.mp3`, mono, **64 kbps CBR** (cerca de 0,47 MB por minuto). O site do GitHub aceita até 25 MB por arquivo: a narração completa tem cerca de 37 min, o que dá 17,5 MB a 64 kbps, mas passaria do limite a 96 kbps (26,2 MB). Para gerar a partir do WAV da montagem final:
  ```bash
  ffmpeg -i <montagem_final>.wav -ac 1 -ar 44100 -c:a libmp3lame -b:a 64k \
    -metadata title="Meu Paraíso" -metadata artist="Narração do livro" narracao.mp3
  ```
- **Capa:** `capa.jpg` (minúsculas, extensão .jpg), com 1200–1600 px no lado maior e menos de 500 KB. Pode ser vertical, horizontal ou quadrada. A versão pronta, tirada da capa do livro (990 × 1400 px, 197 KB), já está nesta pasta.

## O QR code no livro

- `qrcode_meu_paraiso.svg` (vetorial) é o que vai para a gráfica; o PNG serve para conferência. Os dois apontam para https://drdanielnutro.github.io/meu-paraiso-audio/ (conferido em 2026-10-19).
- Na contracapa: pelo menos 25 mm de lado, com margem branca de 4 módulos em volta, e testado no exemplar impresso, com mais de um celular.
- **A narração é a da edição dos pais.** Se a edição dos leitores for impressa, ela terá um áudio próprio (a fala da PC3 muda), numa subpasta deste repositório e com outro QR; este endereço continua sendo o da edição dos pais.
