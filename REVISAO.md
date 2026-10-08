# Revisão dos dados do Farol do Mandato

Levantamento: 08/10/2026. Arquivo revisado: `data.json` (mesmo formato do site, pode substituir o atual).

## Resumo

- Antes da revisão, 198 dos 251 valores estavam marcados como "valor de memória, a confirmar". Agora 224 valores vêm de séries oficiais conferidas e 31 continuam a confirmar.
- 12 cores mudaram: 3 pioraram (Temer, Lula 3 e Bolsonaro), 2 melhoraram (Temer e Bolsonaro) e 7 saíram do cinza porque agora existe série comparável.
- Cada métrica agora usa uma única série do primeiro ao último governo, ou indica onde a série muda.

## Cores que mudaram

| Governo | Métrica | Antes | Agora | Motivo |
|---|---|---|---|---|
| Temer | Mortalidade infantil | verde | amarelo | Série única da ONU (13,7 → 13,1, queda de 4,4%). Pelas tábuas do IBGE seria verde |
| FHC 1 | Vacina (sarampo, 1ª dose) | cinza | verde | Série OMS/UNICEF existe desde antes de 1994 (77% → 95%) |
| FHC 2 | Vacina (sarampo, 1ª dose) | cinza | amarelo | 95% → 96% |
| Temer | Homicídios | amarelo | verde | Série única do SIM: 28,9 → 27,2, queda de 5,9% |
| Lula 3 | Homicídios | verde | amarelo | Série do SIM só vai até 2023 (20,1 → 19,3). Pelo Fórum (MVI) 2022 a 2025 seria verde |
| Bolsonaro | Informalidade | verde | amarelo | Dado oficial do 4º tri de 2018 é 40,8%, não 41%. Queda de 4,7% |
| Bolsonaro | Renda per capita | cinza | amarelo | A série do IBGE é contínua de 2012 a 2025: R$ 1.879 → R$ 1.809 |
| FHC 1 | Extrema pobreza | cinza | verde | Linha de US$ 3,00 do Banco Mundial cobre os anos 90 (28,2% → 19,1%) |
| FHC 2 | Extrema pobreza | cinza | verde | 19,1% → 16,2% |
| Lula 1 | Extrema pobreza | cinza | verde | 16,2% → 11,4% |
| Lula 2 | Extrema pobreza | cinza | verde | 11,4% → 8,4% (2009, não houve PNAD em 2010) |
| Bolsonaro | Gini | amarelo | verde | IBGE revisou 2022 de 0,518 para 0,517. Queda passa de 4,95% para 5,1% |

## Fonte de cada métrica

| Métrica | Fonte e série |
|---|---|
| Mortalidade infantil | UN IGME via Banco Mundial (SP.DYN.IMRT.IN) |
| Expectativa de vida | ONU World Population Prospects via Banco Mundial (SP.DYN.LE00.IN) |
| Vacina | OMS/UNICEF WUENIC, sarampo 1ª dose, via Banco Mundial (SH.IMM.MEAS) |
| IDEB | INEP. 2023 e 2025 conferidos na divulgação de 05/08/2026 |
| Homicídios | UNODC via Banco Mundial (VC.IHR.PSRC.P5), base SIM/DATASUS |
| Mortes por intervenção policial | Anuário Brasileiro de Segurança Pública (FBSP). 2025 = 6.602, 2024 = 6.237 |
| Desemprego | IBGE SIDRA 4099 (PNAD Contínua, 4º tri) de Dilma 2 em diante. PME antes |
| Informalidade | IBGE SIDRA 8529 (PNAD Contínua) |
| PIB per capita real | IBGE contas nacionais via Banco Mundial (NY.GDP.PCAP.KN) |
| IPCA contra a meta | BCB SGS 13522 e metas do CMN |
| Investimento / PIB | IBGE contas nacionais via Banco Mundial (NE.GDI.FTOT.ZS) |
| Renda domiciliar per capita | IBGE SIDRA 7533 (PNAD Contínua), em R$ de 2025 |
| Extrema pobreza | Banco Mundial PIP, linha de US$ 3,00 PPC 2021 |
| Gini | IBGE SIDRA 7435 a partir de 2012. Banco Mundial PIP (PNAD anual) antes |
| Dívida bruta / PIB | BCB SGS 13762 (DBGG) |
| Resultado primário | BCB SGS 5793 (NFSP primário, setor público consolidado, 12 meses) |
| Juro real ~10 anos | Tesouro Transparente, histórico de taxas do Tesouro Direto (Tesouro IPCA+ com Juros Semestrais) |
| Desmatamento | INPE Prodes, taxas consolidadas. 2024 = 6.518 km², 2025 = 5.796 km² |

## Decisões que o grupo precisa validar

1. **Saúde pela ONU ou pelo IBGE.** Usei UN IGME e ONU WPP porque cobrem 1994 a 2024 numa série só. O IBGE tem números próprios nas tábuas de mortalidade, com níveis diferentes. A única cor afetada é a mortalidade infantil de Temer.
2. **Homicídios pelo SIM ou pelo Fórum.** O SIM é a única série que vai de FHC a Lula 3 sem trocar de definição, mas termina em 2023. O Fórum (MVI) é mais recente, mas só começa nos anos 2010. Misturar as duas muda cores.
3. **Desemprego antes de 2015.** FHC até Dilma 1 usam a PME, que cobre só 6 regiões metropolitanas. É outra pesquisa e fica indicada no nome da linha.
4. **Quebras de série.** Não houve PNAD em 1994 nem em 2010, então FHC 1 começa em 1993 e Lula 2 termina em 2009. Em 2012 a PNAD vira PNAD Contínua, então Dilma 1 mede 2012 a 2014 em renda, pobreza e Gini.
5. **Regra dos 5%.** Duas cores dependem de casas decimais: o Gini de Bolsonaro muda com uma revisão de 0,001, e o primário de Temer fica verde com melhora de 0,3 ponto. Sugestão: limiar em pontos para Gini, primário, inflação e taxas em percentual.
6. **IDEB 2021.** O próprio INEP pediu cautela com o IDEB 2021 por causa da pandemia. Vale uma nota na linha de Bolsonaro.
7. **Juro de 2018.** O título mais próximo de 10 anos disponível no fim de 2018 vencia em 7,6 anos.

## Ainda a confirmar (31 valores)

- Desemprego pela PME: FHC 1, FHC 2, Lula 1, Lula 2 e Dilma 1.
- Renda pela PNAD anual: FHC 1, FHC 2, Lula 1 e Lula 2.
- Resultado primário de FHC (a série do BCB usada aqui começa em novembro de 2002).
- IDEB de 2005 a 2021.
- Mortes por intervenção policial de 2014 a 2022.

## Ajustes no site (index.html)

- Cada indicador tem um número ao lado do nome que leva à fonte.
- Nova seção "Fontes e método" no fim da página, com a série usada, o link para a fonte oficial e as quebras de série de cada indicador.
- O texto de abertura não diz mais que as métricas foram fixadas antes de olhar os resultados. Agora diz que as métricas e regras são as mesmas para todos os governos.
- A legenda do † passa a dizer "valor ainda a confirmar na fonte oficial".
- Fontes e notas ficam no `data.json`, nos campos `fonte`, `links` e `nota` de cada métrica. Para trocar uma fonte, basta editar o `data.json`.

## Nota

Cada cor é a variação de uma série oficial nomeada entre duas datas nomeadas. Nenhuma cor mede o que o governo causou, e nenhuma substitui a leitura do contexto de cada período.
