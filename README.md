# Coração em Alerta: Classificação de Doença Arterial Coronariana com IA

Projeto da disciplina de Inteligência Artificial (7º CC, turma 7N), Faculdade de Computação e
Informática, Universidade Presbiteriana Mackenzie. Prof. Dr. Ivan Carlos Alcântara de Oliveira.
**Parte 3 (N2): artigo final, código completo e vídeo.**

**Repositório:** https://github.com/Tiago300803/projeto-ia-coracao-em-alerta
**Vídeo (até 5 min):** https://youtu.be/Or3BiLCbvEQ

## Integrante

| Nome | RA | Turma |
|---|---|---|
| Tiago Caspirro Cardoso | 10390562 | 7N |

## Sobre o projeto

Estudo acadêmico de **apoio à triagem** que classifica a **presença** de doença arterial coronariana
(DAC) a partir de dados clínicos transversais. Não é previsão de risco futuro (a base não tem
acompanhamento no tempo) e **não é diagnóstico**. Alinhado ao ODS 3 (Saúde e Bem-Estar).

## Principais resultados (detalhes e ressalvas no artigo)

- Três modelos (Regressão Logística, Random Forest, XGBoost) comparados por **validação cruzada
  aninhada**, com pré-processamento reajustado em cada partição e hiperparâmetros ajustados só no treino.
- **Regra de seleção definida antes da avaliação** escolheu a Regressão Logística nos três cenários.
- Cenário completo: ROC-AUC aninhada 0,898 ± 0,055; teste 0,952 (IC 95% 0,894–0,993), mas 200 divisões
  treino/teste alternativas indicam desempenho esperado de ≈ 0,91.
- Limiar de decisão (0,26) escolhido só com dados de treino (sensibilidade-alvo 0,90).
- Sem fluoroscopia e teste de tálio, ROC-AUC no teste = 0,917; só com dados de consulta básica = 0,845.
- Um limiar único tem perfis de erro diferentes por sexo (análise exploratória).
- **Os resultados não sustentam uso clínico.**

## Dataset

[UCI Heart Disease (Cleveland)](https://archive.ics.uci.edu/dataset/45/heart+disease), 303 pacientes,
13 preditores + rótulo, CC BY 4.0. Descrição em [`dataset/README.md`](dataset/README.md).

## Como reproduzir

```bash
pip install -r codigo/requirements.txt
cd codigo
jupyter nbconvert --to notebook --execute --inplace --ExecutePreprocessor.timeout=-1 analise_final_heart_disease.ipynb
```

O notebook usa caminhos relativos (`../dataset`, `../figuras`), semente 42 e leva cerca de 10 minutos
(a validação cruzada aninhada nos três cenários é a parte mais demorada). Versões testadas: Python 3.14,
scikit-learn 1.9.1, XGBoost 3.4.1, SHAP 0.52.

## Estrutura

```
├── README.md
├── artigo/
│   ├── projetoDeIA_parte3_artigoFinal_CoracaoEmAlerta.docx / .pdf   # ARTIGO FINAL (Parte 3, template SBC)
│   └── projetoDeIA_parte2_artigoParcial_CoracaoEmAlerta.docx / .pdf # artigo parcial (Parte 2)
├── codigo/
│   ├── analise_final_heart_disease.ipynb      # Parte 3: protocolo final (executado)
│   ├── analise_heart_disease_parte2.ipynb     # Parte 2: EDA e primeiro protocolo (histórico)
│   └── requirements.txt
├── dataset/                                   # base UCI + descrição
├── figuras/                                   # figuras do notebook final (Parte 3)
│   └── parte2/                                # figuras da Parte 2 (artigo parcial)
├── rubrica/                                   # rubricas preenchidas (Partes 2 e 3)
└── video/roteiro_video.md                     # roteiro do vídeo de até 5 minutos
```

## Histórico

| Data | Autor | Descrição |
|---|---|---|
| 2026-08 | Tiago Caspirro Cardoso | Parte 1: proposta do projeto. |
| 2026-09-25 | Tiago Caspirro Cardoso | Parte 2 (N1): EDA, preparação, baseline, Random Forest, XGBoost, SHAP; artigo parcial. |
| 2026-11-20 | Tiago Caspirro Cardoso | Parte 3 (N2): protocolo final (validação aninhada, regra de seleção e limiar a priori, IC, 200 divisões, cenários de atributos, erros, equidade, calibração), artigo final, vídeo. |

## Status

- [x] N1: artigo parcial.
- [x] N2: protocolo final, artigo final, README, roteiro do vídeo.
- [x] Vídeo gravado e link inserido na Seção 4.3 do artigo: https://youtu.be/Or3BiLCbvEQ

