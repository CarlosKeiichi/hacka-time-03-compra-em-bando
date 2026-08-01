# Dados de EXEMPLO · Compra em Bando

> **Estes dados são inventados.** Foram gerados para o time conseguir construir antes de os
> restaurantes parceiros entregarem suas listas reais. Quando as reais chegarem, vão para
> `dados/` e esta pasta pode ser apagada.

## O grupo que estes dados descrevem

Cinco restaurantes pequenos de São Paulo, de tipos diferentes, comprando cada um por si.
Uma semana de compras de cada. Nenhum deles sabe o que o outro paga.

| restaurante | tipo | região | refeições/dia |
|---|---|---|---|
| Restaurante A | Comida por quilo | Zona Sul | 320 |
| Restaurante B | Bistrô / à la carte | Zona Oeste | 145 |
| Restaurante C | Pizzaria | Zona Sul | 210 |
| Restaurante D | Comida caseira / PF | Zona Leste | 280 |
| Restaurante E | Hamburgueria | Zona Oeste | 190 |

## Os arquivos

### `restaurantes.csv` — 5 linhas
Quem é cada um. Serve para agrupar por região e para explicar por que um compra mais que o outro.

| coluna | o que é |
|---|---|
| `restaurante` | Anonimizado: Restaurante A até E |
| `tipo` | O tipo de operação |
| `regiao` / `bairro` | Para consolidar por região — frete e entrega dependem disso |
| `refeicoes_dia` | Porte da operação |
| `dias_semana_aberto` | Quantos dias por semana abre |

### `listas-compras-semana.csv` — 167 linhas
A lista de compras da semana de cada restaurante, com o preço que **cada um** pagou.
40 itens no catálogo; nem todo restaurante compra tudo (pizzaria não compra pão de hambúrguer).

| coluna | o que é |
|---|---|
| `semana_referencia` | Segunda-feira da semana |
| `restaurante` | Quem comprou |
| `categoria` | Carnes, Mercearia, Hortifruti, Laticinios, Padaria, Bebidas, Descartaveis, Limpeza |
| `item` | Nome do item — **escrito igual entre os restaurantes**, de propósito |
| `unidade_medida` | kg, L, un, dz |
| `quantidade` | Quanto comprou na semana |
| `preco_unitario_pago_brl` | **O preço que aquele restaurante pagou.** É o coração do desafio. |
| `valor_total_brl` | quantidade × preço |

Um aviso honesto: aqui os nomes dos itens já vêm padronizados. Na vida real cada restaurante
escreve de um jeito ("mussarela", "queijo mussarela", "muçarela peça"), e casar esses nomes é
metade do trabalho do produto. Se o time quiser encarar isso, é um bom uso da IA — e o dado
real vai trazer essa bagunça de brinde.

## Confira se você leu certo

- Compra semanal somada do grupo: **R$ 42.775,30**
- 167 linhas, 5 restaurantes, 40 itens no catálogo

## O que dá pra provar com este dado

O mesmo item, na mesma semana, na mesma cidade, sai por preços bem diferentes conforme quem
compra. O menor volume paga mais caro — sempre. Alguns exemplos que estão no arquivo:

| item | mais barato | mais caro | diferença |
|---|---|---|---|
| Queijo mussarela | R$ 40,39 | R$ 47,96 | +19% |
| Batata | R$ 4,89 | R$ 5,72 | +17% |
| Óleo de soja | R$ 7,96 | R$ 9,05 | +14% |
| Contrafilé | R$ 47,73 | R$ 53,84 | +13% |

A conta do pitch sai daí: se todo mundo comprasse pelo melhor preço do grupo — ou por um
preço negociado com o volume somado — quanto o grupo economizaria por mês? O dado responde.

## Como o dado real substitui este

Peça a cada restaurante parceiro **a lista de compras de uma semana com os preços pagos**.
Nota fiscal serve, planilha serve, foto do caderno serve (a IA transcreve).

O nome do restaurante tem que ser trocado por "Restaurante A", "Restaurante B" antes de subir.
Preço pago é informação sensível de negócio: nenhum dono quer o concorrente sabendo quanto ele paga.
