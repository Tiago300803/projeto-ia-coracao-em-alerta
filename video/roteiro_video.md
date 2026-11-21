# Roteiro do vídeo (máximo 5 minutos) – Coração em Alerta

Meta: **4min30** de fala para ter folga. Cerca de 580 palavras em ritmo normal. Gravar a tela
(artigo, notebook e GitHub) e ler o texto abaixo com as suas palavras. **Não ultrapassar 5:00.**

| Tempo | O que aparece na tela | Exigência do enunciado |
|---|---|---|
| 0:00–0:25 | Slide/título ou primeira página do artigo | Título, integrante, professor, disciplina, curso, instituição |
| 0:25–1:00 | Introdução do artigo | Definição do problema |
| 1:00–2:00 | Seção 2 e 3 do artigo | Uso da IA e fundamentos da disciplina |
| 2:00–4:00 | Notebook executado (tabelas e figuras) | Solução e funcionamento do artefato |
| 4:00–4:30 | Página do repositório no GitHub | Área do GitHub |

## Texto sugerido

**[0:00] Abertura.** "Olá. Este é o projeto *Coração em Alerta: classificação de doença arterial
coronariana com aprendizagem de máquina e explicabilidade*. Eu sou Tiago Caspirro Cardoso, RA 10390562,
aluno do curso de Ciência da Computação da Universidade Presbiteriana Mackenzie, na disciplina de
Inteligência Artificial do professor Ivan Carlos Alcântara de Oliveira, turma 7N."

**[0:25] Problema.** "Doenças cardiovasculares são a principal causa de morte no mundo, e a doença
arterial coronariana é a principal delas. O diagnóstico de confirmação exige cateterismo, que é caro e
invasivo. O problema deste projeto é: dados clínicos de rotina conseguem ajudar a **priorizar** quem deve
ser investigado primeiro? É importante dizer: é um estudo acadêmico de apoio à triagem, não um diagnóstico,
e classifica a presença atual da doença, não o risco futuro, porque a base não tem acompanhamento no tempo."

**[1:00] IA e fundamentos.** "Usei aprendizagem supervisionada para classificação binária, com a base
pública UCI Heart Disease, de Cleveland: 297 pacientes completos. Comparei Regressão Logística, Random
Forest e XGBoost. Os fundamentos da disciplina que apliquei foram: preparação de dados, divisão
treino e teste, validação cruzada, ajuste de hiperparâmetros, métricas de saúde como sensibilidade,
especificidade e ROC-AUC, e explicabilidade com SHAP. O ponto principal do trabalho é o protocolo: o
pré-processamento é reajustado em cada partição, a validação cruzada é aninhada, e o critério de escolha do
modelo e do limiar foi definido **antes** de olhar o teste."

**[2:00] Demonstração.** (mostrar o notebook) "Aqui está o notebook final, executado do início ao fim.
Na validação cruzada aninhada, os três modelos ficam praticamente empatados, com ROC-AUC perto de 0,89;
pela regra definida antes, a Regressão Logística foi escolhida. [mostrar a figura do limiar] O limiar
foi escolhido só com dados de treino para ter sensibilidade de pelo menos 90%. [mostrar a Tabela de teste]
No teste, a ROC-AUC foi 0,952, com intervalo de confiança de 0,894 a 0,993. [mostrar a figura das 200
divisões] Mas, repetindo a divisão 200 vezes, a média cai para 0,91: a divisão principal foi favorável.
Esse é um resultado honesto sobre a incerteza de uma base pequena. [mostrar os cenários] Sem fluoroscopia
e sem o teste de tálio, que talvez não existam na triagem, a ROC-AUC cai para 0,917, e só com dados de
consulta, para 0,845. [mostrar equidade e SHAP] Também analisei erros, desempenho por sexo, calibração e
explicabilidade. O limiar único tem custos diferentes para homens e mulheres, e a plausibilidade clínica
do SHAP não prova confiabilidade."

**[4:00] GitHub e fechamento.** (mostrar o repositório) "Todo o material está no repositório público do
GitHub: artigo, dataset com descrição, notebooks com cabeçalho e histórico, figuras e instruções para
reproduzir. A conclusão é que o objetivo acadêmico foi alcançado, mas os resultados não sustentam uso
clínico. Obrigado."

## Checklist antes de gravar

- [ ] Abrir `codigo/analise_final_heart_disease.ipynb` (já executado) e deixar as saídas visíveis.
- [ ] Abrir o PDF do artigo na primeira página e na Seção 4.
- [ ] Abrir a página do repositório no GitHub (público, em janela anônima, para conferir o acesso).
- [ ] Conferir a duração: **máximo 5 minutos**.
- [ ] Publicar no YouTube (público ou não listado), copiar o link e colocá-lo na Seção 4.3 do artigo
      (e regerar o PDF), e na tabela de status do README.
