# Especificação do Serviço de Conversões

## Descrição
Backend que fornece tipos de medida e unidades disponíveis, e executa conversões entre unidades compatíveis.

Fluxo:
1. Listar tipos de medida (ex.: Peso, Moeda, Temperatura).
2. Obter unidades válidas para um tipo.
3. Solicitar conversão entre duas unidades daquele tipo.

## Stack
- Node.js
- NestJS
- Axios

## Endpoints

### Listar tipos de medida
GET /api/unidades

Exemplo de resposta:
```json
[
  "Peso",
  "Moeda",
  "Temperatura"
]
```

### Listar unidades de um tipo
O tipo deve ser passado na URL.

GET /api/unidades/:tipo

Exemplo:
GET /api/unidades/peso

Exemplo de resposta:
```json
[
  "Libras",
  "Kg",
  "Gramas"
]
```

### Converter um valor entre duas unidades compatíveis
Recomendação de query params: from, to e value.

GET /api/unidades/:tipo/convert?from=Kg&to=Libras&value=1

Exemplo:
GET /api/unidades/peso/convert?from=Kg&to=Libras&value=1

Exemplo de resposta:
```json
{
  "resultado": 2.20462
}
```

## Boas práticas sugeridas
- Validar parâmetros (tipo e unidades) no backend para evitar conversões incompatíveis.
- Tratar unidades e tipos de forma case-insensitive.
- Para moedas: buscar taxas externas e aplicar cache (TTL) para reduzir chamadas e melhorar latência.
- Padronizar respostas de erro com mensagens claras e HTTP status apropriados (400 para parâmetros inválidos, 404 para tipo/unidade não encontrado, 500 para erros internos).
- Adicionar testes unitários para funções de conversão (especialmente para temperatura e pesos).
- Documentar unidades suportadas e limitações (por exemplo, precisão/rounding).
