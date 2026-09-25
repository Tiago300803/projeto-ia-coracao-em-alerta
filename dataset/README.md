# Dataset — UCI Heart Disease (subconjunto Cleveland)

Breve descrição do dataset utilizado no projeto "Coração em Alerta" (ver artigo completo em
`../artigo/` para a descrição detalhada, Seção 3.2).

## Arquivos

- `processed.cleveland.data` — dados clínicos de 303 pacientes, 14 colunas (13 variáveis
  preditoras + 1 rótulo original), sem cabeçalho. Valores ausentes aparecem marcados como `?`.
- `heart-disease.names` — dicionário de dados original do UCI Machine Learning Repository
  (em inglês), com a descrição de cada atributo.

## Origem e licença

- **Origem**: Cleveland Clinic Foundation, doado por Janosi, Steinbrunn, Pfisterer e Detrano
  (1988), disponibilizado publicamente pelo UCI Machine Learning Repository.
- **Link oficial**: https://archive.ics.uci.edu/dataset/45/heart+disease
- **DOI**: 10.24432/C52P4X
- **Licença**: Creative Commons Attribution 4.0 International (CC BY 4.0).

## Variáveis (ordem das colunas em `processed.cleveland.data`)

| # | Coluna (nome usado no notebook) | Significado |
|---|---|---|
| 1 | idade | Idade do paciente (anos) |
| 2 | sexo | Sexo (1 = masculino, 0 = feminino) |
| 3 | tipo_dor_peito | Tipo de dor no peito (1–4) |
| 4 | pressao_repouso | Pressão arterial em repouso (mm Hg) |
| 5 | colesterol | Colesterol sérico (mg/dl) |
| 6 | glicemia_jejum_alta | Glicemia de jejum > 120 mg/dl (1 = sim) |
| 7 | ecg_repouso | Resultado do eletrocardiograma em repouso |
| 8 | freq_card_maxima | Frequência cardíaca máxima atingida |
| 9 | angina_exercicio | Angina induzida por exercício (1 = sim) |
| 10 | depressao_st | Depressão do segmento ST induzida por exercício |
| 11 | inclinacao_st | Inclinação do segmento ST no pico do exercício |
| 12 | num_vasos_fluoroscopia | Nº de vasos principais coloridos por fluoroscopia (0–3) |
| 13 | talassemia | Resultado do teste de tálio |
| 14 | num | Rótulo original: 0 = ausência, 1–4 = graus de severidade de doença arterial coronariana (DAC), diagnosticada por angiografia |

No notebook (`../codigo/analise_heart_disease.ipynb`), o rótulo `num` é binarizado em `alvo`
(0 = ausência, 1 = presença de DAC), que é o que o projeto efetivamente classifica.

## Tamanho e qualidade

- 303 registros brutos; 6 registros (2,0%) têm valor ausente em `num_vasos_fluoroscopia` e/ou
  `talassemia` — removidos na preparação dos dados (ver notebook, Seção 4).
- Distribuição do rótulo binarizado, após limpeza: 46,1% de casos positivos (presença de DAC),
  53,9% de casos negativos — razoavelmente balanceado.
- **Importante**: a base representa pacientes já encaminhados para avaliação cardiológica na
  Cleveland Clinic (Estados Unidos, década de 1980), não uma amostra da população geral.
