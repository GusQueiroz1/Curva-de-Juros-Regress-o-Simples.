# Curva-de-Juros-Regress-o-Simples.
Este repositório consolida a rotina de captura, tratamento e modelagem da Estrutura a Termo de Taxa de Juros (ETTJ), utilizando dados da B3/ANBIMA. O projeto foi desenvolvido com foco na extração da curva DI x PRÉ e na aplicação de modelos de regressão para análise de inclinação (slope) e sensibilidade do mercado futuro de juros.

Metodologia e Abordagem Analítica
1. Governança de Dados (Data Sourcing)
Diferente de abordagens manuais ruidosas, implementamos uma função de captura modularizada via API pyettj.

Nota de Ceticismo: Baseamos nossa análise em dados históricos (04/01/2010). É imperativo questionar a liquidez dos contratos em datas específicas, pois outliers em vértices curtos podem distorcer o intercepto do modelo e gerar falsos sinais de política monetária.

2. Otimização Estatística
A modelagem foi migrada de scripts simples para uma implementação robusta utilizando o Scikit-Learn.

Variável Independente (X): Dias Corridos (Tenor/Vencimento).
Variável Dependente (y): Taxa de Juros (DI x PRÉ 252).

📊 Diagnóstico de Output
O modelo entrega métricas fundamentais para a análise macroeconômica:

R² (Coeficiente de Determinação): Mede a aderência do modelo aos pontos da curva.
Intercepto: Estimativa da taxa base teórica no "overnight".
Slope (Inclinação): Representação do prêmio de risco exigido pelo mercado ao longo do horizonte temporal.
