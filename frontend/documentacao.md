# Documentação — Frontend (Conversor-de-Unidades)

Versão: 1.0  
Autor do repositório: danilolps01  
Diretório documentado: frontend

---

## Visão geral

O frontend deste projeto é uma aplicação estática em HTML/CSS que fornece páginas separadas para conversões de:
- Valores monetários
- Peso
- Medidas (comprimento/volume/etc.)

Não há dependências externas ou build step — são arquivos HTML simples estilizados por um arquivo CSS. Pode ser usado abrindo os arquivos diretamente no navegador ou servindo a pasta `frontend` por um servidor estático.

---

## Estrutura de arquivos

- README/Documentação:
  - documentacao.md (este arquivo)

- Páginas HTML:
  - Monetário: https://github.com/danilolps01/Conversor-de-Unidades/blob/main/frontend/monetario.html
  - Peso: https://github.com/danilolps01/Conversor-de-Unidades/blob/main/frontend/peso.html
  - Medida: https://github.com/danilolps01/Conversor-de-Unidades/blob/main/frontend/medida.html

- Estilos:
  - CSS: https://github.com/danilolps01/Conversor-de-Unidades/blob/main/frontend/style.css

(Links apontam para os arquivos no repositório)

---

## Como usar (local)

Opção A — Abrir direto no navegador:
1. Clone o repositório ou faça download da pasta `frontend`.
2. Dê um duplo-clique em qualquer um dos arquivos HTML (por exemplo `monetario.html`) para abrir no navegador.

Opção B — Servir por um servidor HTTP (recomendado para evitar problemas com políticas de arquivo do navegador):
- Com Python 3:
  - No terminal, dentro da pasta `frontend`:
    - Python 3.x: `python -m http.server 8000`
  - Abra http://localhost:8000/ e clique no arquivo desejado.
- Com Node (http-server):
  - Instale: `npm install -g http-server`
  - Rode: `http-server -p 8000`
  - Abra http://localhost:8000/

---

## Uso das páginas

Cada página HTML contém um formulário/interface para:
1. Inserir o valor a ser convertido.
2. Selecionar a unidade/condição de origem e destino.
3. Acionar a conversão (botão).
4. Visualizar o resultado exibido na própria página.

Fluxo típico:
- Abra a página desejada (ex.: `monetario.html`).
- Insira o valor.
- Selecione as unidades.
- Clique em "Converter" (ou equivalente) e verifique o resultado mostrado.

Observação: como estas são páginas estáticas, verifique o código caso queira adaptar regras de conversão (por exemplo, taxas de câmbio dinâmicas).

---

## Como editar / estender

- Estilos:
  - Edite `style.css` para alterar cores, layouts e tipografia.
- Páginas:
  - Edite os arquivos `.html` para ajustar elementos, nomes de unidades ou lógica de conversão.
- Adicionar nova conversão:
  1. Criar um novo arquivo HTML baseado nos existentes (copiar & colar).
  2. Ajustar selects/inputs e a função de conversão em JavaScript (se existir dentro do HTML).
  3. Adicionar link para o novo arquivo onde for necessário (ou criar um índice).

---

## Boas práticas e recomendações

- Valide entradas do usuário (números, campos obrigatórios) antes de fazer a conversão.
- Para conversões que dependem de dados dinâmicos (ex.: câmbio), considere integrar uma API e um backend ou atualizar as taxas via JavaScript com requests CORS adequados.
- Mantenha estilos reutilizáveis no `style.css` e evite duplicação entre páginas.

---

## Testes rápidos

- Teste 1: inserir valores válidos (ex.: 100) e verificar se o resultado é plausível.
- Teste 2: inserir valores inválidos (texto, vazio) e validar que a interface não quebre.
- Teste 3: alterar unidades e confirmar que a relação entre origem/destino está correta.

---

## Troubleshooting

- Página em branco: verifique se o caminho para `style.css` ou quaisquer scripts está correto.
- Conversões incorretas: abra o HTML no editor e revise a lógica de cálculo/constantes utilizadas.
- Problemas ao abrir localmente: rode um servidor estático conforme instruções acima.

---

## Deploy (GitHub Pages)

Para publicar como site estático:
1. Opcional: mover os arquivos para a pasta `docs/` na branch `main`, ou manter em `frontend` e configurar GitHub Pages para servir a partir de `main` → `/ (root)` ou `/docs` conforme preferir.
2. Nas configurações do repositório → Pages, selecione a branch e a pasta desejada.
3. Salve e aguarde alguns minutos; o site ficará disponível no domínio fornecido pelo GitHub Pages.

---

## Contato e Créditos

Projeto hospedado em: https://github.com/danilolps01/Conversor-de-Unidades
Autor/Responsável: danilolps01