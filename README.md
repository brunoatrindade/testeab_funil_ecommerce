Otimização de Receita: Priorização de Hipóteses e Análise de Teste A/B 📈
Este projeto simula um cenário real onde atuei como Analista de Dados em uma grande loja online. O objetivo foi identificar, priorizar e testar hipóteses para aumentar a receita do e-commerce através de rigor estatístico e visão de negócio.

🛠️ Tecnologias e Metodologias
Linguagem: Python

Bibliotecas: Pandas, Matplotlib, Seaborn, SciPy (Stats)

Frameworks de Priorização: ICE e RICE

Testes Estatísticos: Teste de Mann-Whitney U (U-Test)

Conceitos: Conversão acumulada, Ticket Médio, Outliers (Percentis) e Significância Estatística.

🎯 Parte 1: Priorização de Hipóteses
Trabalhei com o departamento de Marketing para avaliar 9 hipóteses. A transição do framework ICE para o RICE foi fundamental para a estratégia.

O "Pulo do Gato": Enquanto a hipótese de "Promoções de Desconto" liderava no ICE, ela caiu no ranking RICE.

Vencedora: A hipótese "Adicionar um formulário de inscrição em todas as páginas principais" assumiu a liderança (RICE: 112.0) devido ao seu alcance máximo (Reach 10), garantindo que o esforço fosse aplicado onde afetaria o maior número de usuários.

🧪 Parte 2: Análise do Teste A/B
Após rodar o experimento, realizei um saneamento rigoroso nos dados, removendo 181 pedidos de usuários que estavam em ambos os grupos (contaminados), garantindo a integridade do teste.

1. Desempenho Acumulado
Analisei a receita e o tamanho médio do pedido (Ticket Médio) ao longo do tempo.

Receita: O Grupo B apresentou um salto significativo em determinado ponto, sugerindo a presença de pedidos anômalos ou uma vantagem competitiva real.

Conversão: A taxa de conversão do Grupo B estabilizou em um nível superior ao do Grupo A, indicando maior eficiência no funil de vendas.

2. Tratamento de Anomalias (Outliers)
Para não distorcer os resultados, calculei os percentis 95 e 99:

Número de pedidos: Defini o ponto de corte para usuários com comportamento atípico.

Preço dos pedidos: Identifiquei pedidos de valor extremo que estavam "puxando" a média para cima artificialmente.

3. Testes de Significância Estatística (Mann-Whitney U)
Utilizei o teste não-paramétrico de Mann-Whitney para comparar os grupos A e B, tanto com dados brutos quanto com dados filtrados:

Conversão: Encontrei diferença estatisticamente significativa em ambos os cenários (p-value < 0.05). O Grupo B é o líder claro em conversão.

Ticket Médio: Não houve diferença estatisticamente significativa após a remoção dos outliers, indicando que o aumento na receita veio do volume de vendas (conversão) e não de pedidos mais caros.

🏆 Conclusão de Negócio
Decisão: Parar o teste e declarar o Grupo B como vencedor.

O teste demonstrou que as alterações implementadas no Grupo B aumentaram significativamente a taxa de conversão da loja online. Embora o ticket médio tenha permanecido estável, o ganho em escala de usuários convertidos justifica a implementação definitiva da hipótese testada.

📂 Como visualizar o projeto
O código completo está no arquivo .ipynb deste repositório.

Os dados utilizados (processados) estão em visits_us.csv.
