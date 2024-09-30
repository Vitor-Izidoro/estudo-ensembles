# Avaliação do Impacto de Técnicas de Seleção de Instâncias em Ensembles Orientados a Fluxos de Dados

**Relatório Final apresentado ao Programa Institucional de Bolsas de Iniciação Científica (PIBIC) Pró-Reitoria de Pesquisa Pós-Graduação e Inovação da Pontifícia Universidade Católica do Paraná.**

**Orientador: Prof. Dr. Fabricio Enembreck**

**Bolsa: CNPq**

---

## Resumo

A crescente geração de dados em tempo real por dispositivos móveis e sensores realça a importância da mineração de fluxo de dados (Data Stream Mining – DSM). A classificação desses fluxos enfrenta desafios significativos como conceitos em constante mudança, alta frequência de novos exemplos e recursos computacionais limitados. Algoritmos baseados em ensembles, como o "Random Forest", têm mostrado bons resultados, mas consomem muitos recursos.

Inspirado pelo "Random Forest", foi desenvolvido o "Adaptive Random Forest" (ARF), um algoritmo de ensemble com capacidade de aprendizagem online. Esta pesquisa visa estudar como técnicas de Seleção de Instâncias podem mitigar a complexidade computacional envolvida na classificação de fluxos de dados.

**Palavras-chave**: 1. Mineração de fluxo de dados; 2. Algoritmos de ensemble; 3. Instance-Based Learning; 4. Random Forest; 5. Boosting; 6. Recursos computacionais.

---

## Objetivo Geral

Avaliar e desenvolver técnicas de seleção de instâncias para ensembles orientados a fluxos de dados, viabilizando a aplicação desses algoritmos em cenários de larga escala.

### Objetivos Específicos

- Estudar técnicas de seleção de instâncias para ambientes batch e stream;
- Avaliar o impacto das técnicas de seleção de instâncias nos algoritmos estado-da-arte para classificação de fluxos de dados (ARF e SRP);
- Propor e avaliar técnicas simples de seleção de instâncias baseadas em performance de classificação.

---

## Materiais e Método

Neste projeto, utilizou-se um computador rodando Windows 10, com 16GB de memória RAM, a IDE Eclipse e o aplicativo MOA (Massive Online Analysis). O MOA é um software dedicado à mineração de dados em streaming, desenvolvido para lidar com grandes volumes de dados em tempo real.

A revisão da literatura focou nas técnicas de Instance-Based Learning (IBL), que armazenam instâncias de treinamento na memória e têm como desafios selecionar quais pontos armazenar e quais métricas utilizar. A pesquisa considerou tanto técnicas de batch quanto de stream para otimizar o uso de recursos computacionais.

---

## Resultados

As técnicas de Seleção de Instâncias reduziram a precisão dos algoritmos, mas melhoraram significativamente o consumo de tempo e de recursos computacionais. O "Adaptive Random Forest" (ARF) sem a Seleção de Instâncias teve a melhor taxa de acertos, porém com maior custo de memória e tempo de processamento. Em contrapartida, o "OzaBoost" com a Seleção de Instâncias apresentou o pior desempenho em acurácia, mas teve uma redução considerável no tempo de processamento.

### Tabela de Classificação:

| Dataset   | Levering | IS-Levering | ARF    | IS-ARF | OzaBoost | IS-OzaBoost | SRP    | IS-SRP |
| --------- | -------- | ----------- | ------ | ------ | -------- | ----------- | ------ | ------ |
| airlines  | 63.50%   | 59.75%      | 66.72% | 61.78% | 64.93%   | 61.03%      | 68.56% | 62.44% |
| kdd99     | 99.95%   | 99.96%      | 99.97% | 99.97% | 99.91%   | 99.97%      | 99.98% | 99.98% |
| keystroke | 87.43%   | 81.00%      | 91.81% | 88.37% | 82.56%   | 82.25%      | 94.68% | 89.25% |

---

### Gráfico do Tempo:

| Dataset   | Levering   | IS-Levering | ARF      | IS-ARF   | OzaBoost | IS-OzaBoost | SRP      | IS-SRP   |
| --------- | ---------- | ----------- | -------- | -------- | -------- | ----------- | -------- | -------- |
| airlines  | 2439.12s   | 1235.46s    | 2297.03s | 1008.04s | 19.39s   | 13.32s      | 2503.48s | 1054.01s |
| kdd99     | 426.98s    | 619.26s     | 4929.87s | 6450.29s | 296.09s  | 874.79s     | 7663.54s | 6231.06s |
| keystroke | 2.98s      | 0.89s       | 4.45s    | 1.54s    | 0.29s    | 0.15s       | 4.50s    | 1.84s    |

---

### Tabela de Custo de Memória:

| Dataset   | Levering | IS-Levering | ARF    | IS-ARF | OzaBoost | IS-OzaBoost | SRP    | IS-SRP |
| --------- | -------- | ----------- | ------ | ------ | -------- | ----------- | ------ | ------ |
| airlines  | 0.02662  | 0.02988     | 0.04495| 0.02014| 0.00001  | 0.00003     | 0.05422| 0.02355|
| kdd99     | 0.05200  | 0.014799    | 0.18297| 0.19728| 0.00023  | 0.00183     | 0.26704| 0.17254|
| keystroke | 0.00003  | 0.00002     | 0.00009| 0.00003| 0.00000  | 0.00000     | 0.00009| 0.00003|

---

## Discussão

A análise mostra que a Seleção de Instâncias sacrifica a precisão em troca de melhorias no tempo de execução e custo de memória. Algoritmos como o "Adaptive Random Forest" mantêm alta precisão sem a seleção de instâncias, mas com custo computacional elevado. A Seleção de Instâncias reduz significativamente o tempo e o custo de memória, tornando-se uma opção viável para aplicações em larga escala, onde a velocidade é uma prioridade maior que a precisão.

---

## Conclusão

O uso de ensembles para cenários de larga escala ainda é inviável para casos que priorizam a velocidade computacional, mas é viável em condições onde a prioridade é a taxa de acerto. A Seleção de Instâncias mostrou-se capaz de reduzir o consumo de recursos computacionais, abrindo caminho para pesquisas futuras com técnicas mais avançadas. 

---

## Uso de IA Generativa

**Ferramentas utilizadas**: ChatGPT

---

## Referências

- Heitor Murilo Gomes, Jean Paul Barddal, Fabrício Enembreck, and Albert Bifet. 2017. A Survey on Ensemble Learning for Data Stream Classification. ACM Comput. Surv. 50, 2 (March 2017), 1-36. [DOI: 10.1145/3054925](https://doi.org/10.1145/3054925)
- Sérgio Ramírez-Gallego, Bartosz Krawczyk, Salvador García, Michał Woźniak, Francisco Herrera. A Survey on Data Preprocessing for Data Stream Mining: Current Status and Future Directions. Neurocomputing, 2017. [DOI: 10.1016/j.neucom.2017.01.078](https://doi.org/10.1016/j.neucom.2017.01.078)

---

**Pontifícia Universidade Católica do Paraná**
**Pró-Reitoria de Pesquisa Pós-Graduação e Inovação**
