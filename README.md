# DataWareHousing — consultas SQL sobre programas sociais

Conjunto de **9 consultas SQL** sobre pagamentos de programas de transferência de renda (**Bolsa Família**, **Auxílio Brasil** e **BPC**), desenvolvido como trabalho de faculdade na **UFRJ** em julho de 2023.

O repositório contém apenas as consultas. Não inclui os dados, o esquema do banco nem os resultados das execuções.

## Tabelas e campos usados

O esquema não está documentado no repositório; as informações abaixo foram deduzidas das consultas:

| Tabela | Campos usados |
| --- | --- |
| `Pagamento` | `NIS`, `Valor`, `mes`, `ano`, `tipo_auxilio` (valores usados: `Bolsa Familia`, `Auxilio Brasil`, `BPC`) |
| `Beneficiario` | `NIS`, `Qtd_Dependentes` |

Nas consultas, o número de pessoas de uma família é calculado como `Qtd_Dependentes + 1`.

## Consultas

Cada arquivo contém um comentário com o objetivo e a consulta SQL. Os arquivos não têm extensão.

| Arquivo | O que calcula |
| --- | --- |
| `cadastrados Bolsa Familia` | Total de cadastrados contemplados pelo Bolsa Família |
| `cadastrados Auxilio Brasil` | Total de cadastrados contemplados pelo Auxílio Brasil |
| `bolsa familia + auxilio brasil` | Beneficiários que receberam Bolsa Família e Auxílio Brasil em qualquer momento (não necessariamente ao mesmo tempo) |
| `bpc + bolsa familia` | Beneficiários que receberam BPC e Bolsa Família em qualquer momento |
| `avg pessoas por familia` | Média de pessoas por família (apenas Bolsa Família, pois os outros auxílios são individuais) |
| `avg mensal por familia` | Média da renda mensal por família |
| `base de dados renda + nis + qtd de dependentes ao longo tempo` | Base com renda, NIS e quantidade de pessoas na família por mês e ano |
| `dependentes+cadastrados bolsa familia` | Total de pessoas (cadastrados e dependentes) contempladas pelo Bolsa Família |
| `bolsa familia no ano 2021` | Total de pessoas contempladas pelo Bolsa Família em 2021 |

## Técnicas SQL utilizadas

Agregações (`COUNT`, `SUM`, `AVG`), `GROUP BY`, `DISTINCT`, subconsultas, `INNER JOIN` e `LEFT JOIN`.

## Observações e limitações

- A consulta do arquivo `bpc + bolsa familia` tem um `;` logo depois de `from` na primeira linha (`select count(*) from;`), o que provavelmente é um erro de digitação; ela não executa como está.
- Os arquivos não têm extensão `.sql`.
- As consultas não foram executadas nesta documentação, pois o repositório não contém os dados.

## Pendente de confirmação

- Disciplina e ano acadêmico do trabalho.
- Origem dos dados e esquema completo do banco.

## Autor

Willian Gomes — https://github.com/wiUl
