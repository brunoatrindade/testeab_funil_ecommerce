## Otimização de Receita em e-commerce. Priorização de Hipóteses para aumento de lucro e Análise de Teste A/B.

Este projeto simula um cenário real onde atuei como Analista de Dados em uma grande loja online. O objetivo foi identificar, priorizar e testar hipóteses para aumentar a receita do e-commerce através de rigor estatístico e visão de negócio.

### Tecnologias e Metodologias Usadas.

- Linguagem: Python, SQL
- Bibliotecas: Pandas, Matplotlib, Seaborn, SciPy (Stats)
- Frameworks de Priorização: ICE e RICE
- Testes Estatísticos: Teste de Mann-Whitney U (U-Test)
- Conceitos: Conversão acumulada, Ticket Médio, Outliers (Percentis) e Significância Estatística.

### Parte 1: Priorização de Hipóteses
Trabalhei com o departamento de Marketing para avaliar 9 hipóteses. A transição do framework ICE para o RICE foi fundamental para a estratégia. O "Pulo do Gato": enquanto a hipótese de "Promoções de Desconto" liderava no ICE, ela caiu no ranking RICE.

Vencedora: A hipótese "Adicionar um formulário de inscrição em todas as páginas principais" assumiu a liderança (RICE: 112.0) devido ao seu alcance máximo (Reach 10), garantindo que o esforço fosse aplicado onde afetaria o maior número de usuários.

### Parte 2: Análise do Teste A/B
Após rodar o experimento, realizei um saneamento rigoroso nos dados, removendo 181 pedidos de usuários que estavam em ambos os grupos (contaminados), garantindo a integridade do teste.

#### 1. Desempenho Acumulado
Analisei a receita e o tamanho médio do pedido (Ticket Médio) ao longo do tempo.

Receita: O Grupo B apresentou um salto significativo em determinado ponto, sugerindo a presença de pedidos anômalos ou uma vantagem competitiva real.

Conversão: A taxa de conversão do Grupo B estabilizou em um nível superior ao do Grupo A, indicando maior eficiência no funil de vendas.

<img width="1187" height="590" alt="image" src="https://github.com/user-attachments/assets/9249bce7-76c5-478e-8d45-e9bfa1389763" />

O gráfico AOV ajuda a visulizar se a diferença na receita é impulsionada por um volume maior de pedidos com mais usuários comprando, ou por pedidos mais caros de alguns usuários.

<img width="1187" height="590" alt="image" src="https://github.com/user-attachments/assets/46cfa0f8-558a-4894-8701-830d57397047" />

O resultado do gráfico de Taxa de Conversão demonstra curvas mais suaves, que me parece ser menos afetados a outliers. O grupo B está com suas curvas mais acima em relação ao grupo A, e se mantém. Esse resultado demonstra que o grupo B pode converter mais visitantes em compradores por conta do número maior de usuários. Fato é que o gráfico de Taxa de Conversão Acumulada é fundamentalmente diferente dos gráficos de Receita e AOV.

<img width="1187" height="590" alt="image" src="https://github.com/user-attachments/assets/33b07445-43f5-438a-9448-afe1aa8d6510" />

O gráfico abaixo da direfença relativa acumulada na Taxa de Conversão é a prova visual mais convincente do sucesso da variante B na métrica de comportamento do usuário. A linha da diferença relativa, após a instabilidade inicial, se mantém consistentemente acima do zero durante a maior parte do teste, demonstrando a vitória clara da Variante B em relação ao Controle A. O resultado confirma que a alteração implementada na Variante B é eficaz em incentivar mais visitantes a se tornarem compradores. Isso valida a escolha de priorização feita com RICE, que selecionou uma hipótese de alto alcance. Este gráfico contrasta fortemente com o gráfico da Diferença Relativa do AOV, que era caótico e distorcido por outliers. A diferença clara e estável na conversão sugere que o teste é vencedor na métrica de volume de transações, mas ainda precisamos confirmar o impacto financeiro. A diferença é visualmente clara, mas a decisão final de implementá-lo permanentemente depende da Significância Estatística. Além disso, o Ticket Médio (AOV) ainda está em questão.

<img width="1187" height="590" alt="image" src="https://github.com/user-attachments/assets/43a19abc-b4ae-43ea-91d0-c2eb12e2a7f4" />

#### 2. Tratamento de Anomalias (Outliers)
Para não distorcer os resultados, calculei os percentis 95 e 99:

Número de pedidos: Defini o ponto de corte para usuários com comportamento atípico.

Preço dos pedidos: Identifiquei pedidos de valor extremo que estavam "puxando" a média para cima artificialmente.

#### 3. Testes de Significância Estatística (Mann-Whitney U)
Utilizei o teste não-paramétrico de Mann-Whitney para comparar os grupos A e B, tanto com dados brutos quanto com dados filtrados:

Conversão: Encontrei diferença estatisticamente significativa em ambos os cenários (p-value < 0.05). O Grupo B é o líder claro em conversão.

Ticket Médio: Não houve diferença estatisticamente significativa após a remoção dos outliers, indicando que o aumento na receita veio do volume de vendas (conversão) e não de pedidos mais caros.

## Conclusão de Negócio
Decisão: Parar o teste e declarar o Grupo B como vencedor.

O teste demonstrou que as alterações implementadas no Grupo B aumentaram significativamente a taxa de conversão da loja online. Embora o ticket médio tenha permanecido estável, o ganho em escala de usuários convertidos justifica a implementação definitiva da hipótese testada.

A conclusão final é que o Grupo B é claramente o líder, pois ele melhora drasticamente a conversão sem prejudicar o valor médio do pedido, tornando a sua implementação imediata a escolha mais lucrativa e estatisticamente justificada para o negócio, sendo portanto o Grupo B líder na testagem.

Para essa decisão, minha justificativa é de que a variante B demonstrou um aumento na Taxa de Conversão que é estatisticamente significativo. 

## Ações recomendadas (próximos passos de negócio para o e-commerce).
Para completar o ciclo do Teste A/B, sugiro algumas ações de negócio a serem tomadas. Uma delas é a implementação imediata da variante B para 100% dos usuários, substituindo o Grupo A (Controle). Outro ponto é o monitoramento, o desempenho deve ser monitorado por algumas semanas após a implementação para garantir que o lift (melhoria) de 18.95% se mantenha no ambiente de produção, o que é conhecido como Teste AA pós-implementação.

E por fim, como a variante B resolveu o problema de conversão quanto ao volume de pedidos, a próxima prioridade da loja online no Teste A/B deve focar em aumentar o AOV (Ticket Médio), que ainda está estagnado, aplicando ações como por exemplo, testar novas recomendações de produtos ou ofertas de frete grátis por valor.


## Como visualizar o projeto
- O código completo está no arquivo .ipynb deste repositório.
- Os dados utilizados (processados) estão em visits_us.csv.
