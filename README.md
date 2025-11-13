# Codename Generator — Gerador de Tabuleiro

Este pequeno projeto gera um tabuleiro inspirado no jogo Codenames para testes e prototipagem.

Ao contrário do jogo completo, aqui você configura a grade (largura × altura), escolhe quantos itens coloridos e exclusões (pretos) e o sistema gera uma distribuição visual do tabuleiro.

## Principais recursos

- Configuração simples de largura/altura (2–8).
- Itens coloridos sempre em número ímpar (3..max) — padrão tenta usar 17 quando possível.
- Exclusões (pretos) com valor padrão 1 quando possível.
- Pré-visualização do grid e botão para gerar o tabuleiro final.
- Modo noturno (dark mode) com persistência via `localStorage`.
- Clique em células vazias (cinza) para escurecê-las mais; células coloridas exibem ícones centrais (círculo = azul, X = vermelho, triângulo = preto).

## Arquivos importantes

- `index.html` — página de configuração, seleção de parâmetros e toggle de tema.
- `board.html` — página que gera o tabuleiro a partir da configuração salva em `localStorage`.
- `icons/` — pasta com SVGs usados (moon, sun, circle, cross, triangle, etc.).

## Como testar localmente

Opções rápidas:

- Abrir arquivos diretamente no navegador: dê um duplo-clique em `index.html` (funciona, mas alguns navegadores podem restringir fetch de arquivos locais).

- Servidor local (recomendado): usando `npx serve` ou qualquer servidor estático. Exemplo (no Bash do Windows):

```bash
# no diretório do projeto
npx serve -l 5500
# depois abra https://localhost:5500 ou http://localhost:5500 conforme o output
```

## Observações de implementação

- O estado do tema é salvo em `localStorage` sob a chave `siteTheme`.
- Ao gerar o tabuleiro, a configuração é salva em `tabuleiroConfig` (JSON) e `board.html` a consome.
- Os ícones nas células são SVGs (em `icons/`) inseridos como `<img>` ou em alguns casos inline (para herdar `currentColor`) — ver comentários no código.

## Sugestões rápidas

- Para que os ícones herdem cor do tema, prefira SVGs com `fill="currentColor"` ou injetar o SVG inline.
- Ajuste `img.style.width` / `height` em `board.html` se quiser ícones maiores/menores nas células.

## Licença

Use livremente — este projeto é um protótipo. Se pretende redistribuir, adicione a licença que preferir.

---

## Agradecimentos

Este projeto foi gerado e desenvolvido por Luiz Claudio com a ajuda das seguintes ferramentas:

- GitHub Copilot — auxílio no código e sugestões.
- ChatGPT — assistência na implementação, ajustes de UX e sugestões de CSS/JS.

