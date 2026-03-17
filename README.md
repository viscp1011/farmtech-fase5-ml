# 🌾 FarmTech Solutions – Machine Learning & Cloud Computing
### FIAP – Fase 5 | Tratores Digitais | PBL Cap 1

**Aluno:** Vitório Stevanatto Compri Paciulo  
**Curso:** Inteligência Artificial – FIAP  
**Grupo:** 17  

---

## 📋 Descrição do Projeto

Este repositório contém as entregas obrigatórias da **Fase 5** do curso de IA da FIAP, desenvolvido pela **FarmTech Solutions** – empresa de consultoria de IA para o agronegócio.

O projeto analisa dados de condições de solo e clima de uma fazenda de médio porte (200 hectares) para:
1. **Entrega 1:** Prever o rendimento de safras com Machine Learning
2. 2. **Entrega 2:** Estimar e comparar custos de infraestrutura em nuvem AWS
  
   3. ---
  
   4. ## 📁 Estrutura do Repositório
  
   5. ```
      farmtech-fase5-ml/
      │
      ├── VitorioStevanatto_pbl_fase4.ipynb   # Notebook principal (Entrega 1)
      └── README.md                            # Este arquivo (Entrega 1 + Entrega 2)
      ```

      ---

      ## 🤖 Entrega 1 – Machine Learning

      ### Dataset

      O arquivo `crop_yield.csv` contém dados de condições climáticas e rendimento de diferentes culturas:

      | Variável | Descrição |
      |---|---|
      | **Crop** | Cultura agrícola |
      | **Precipitation (mm day-1)** | Precipitação diária em mm |
      | **Specific Humidity at 2 Meters (g/kg)** | Umidade específica a 2m |
      | **Relative Humidity at 2 Meters (%)** | Umidade relativa a 2m |
      | **Temperature at 2 Meters (C)** | Temperatura a 2m acima do solo |
      | **Yield** | Rendimento em toneladas/hectare (variável alvo) |

      ### 📓 Notebook Jupyter

      O notebook completo com toda a solução está disponível aqui:

      👉 **[VitorioStevanatto_pbl_fase4.ipynb](./VitorioStevanatto_pbl_fase4.ipynb)**

      O notebook contém:
      - ✅ Análise Exploratória de Dados (EDA)
      - - ✅ Clusterização K-Means com Método do Cotovelo
        - - ✅ Detecção de Outliers via IQR
          - - ✅ 5 Modelos Preditivos de Regressão Supervisionada
            - - ✅ Comparação de Métricas (MAE, RMSE, R²)
              - - ✅ Células Markdown com análise e conclusões
               
                - ### 🏆 Resultados dos Modelos
               
                - | Modelo | MAE | RMSE | R² |
                - |---|---|---|---|
                - | Regressão Linear | 53724.49 | 65364.57 | -0.10 |
                - | Decision Tree | 2896.38 | 4888.37 | **0.9938** |
                - | **Random Forest** ⭐ | **2744.58** | **4656.11** | **0.9944** |
                - | Gradient Boosting | 3052.78 | 5176.01 | 0.9931 |
                - | SVR (RBF) | 38837.31 | 71234.82 | -0.31 |
               
                - > O **Random Forest** obteve o melhor desempenho com R² = 0.9944.
                  >
                  > ### 🎬 Vídeo Demonstrativo – Entrega 1
                  >
                  > > ⚠️ **Link do vídeo será adicionado aqui após a gravação**
                  > > >
                  > > >> 📹 YouTube (não listado): `[LINK_DO_VIDEO_AQUI]`
                  > > >>
                  > > >> ---
                  > > >>
                  > > >> ## ☁️ Entrega 2 – Computação em Nuvem AWS
                  > > >>
                  > > >> ### Objetivo
                  > > >>
                  > > >> Estimar custos de uma instância EC2 Linux para hospedar a API com o modelo de ML, comparando duas regiões AWS.
                  > > >>
                  > > >> ### Configurações da Instância
                  > > >>
                  > > >> - **CPUs:** 2 vCPUs
                  > > >> - - **Memória RAM:** 1 GiB
                  > > >>   - - **Rede:** Até 5 Gigabit
                  > > >>     - - **Armazenamento:** 50 GB (HD)
                  > > >>       - - **Tipo de preço:** On-Demand (100%)
                  > > >>         - - **Sistema Operacional:** Linux
                  > > >>          
                  > > >>           - ### 📊 Comparativo de Custos AWS (On-Demand)
                  > > >>          
                  > > >>           - | Região | Instância | vCPU | RAM | Preço/hora | Preço/mês (est.) |
                  > > >>           - |---|---|---|---|---|---|
                  > > >>           - | 🇧🇷 São Paulo (sa-east-1) | t3.micro | 2 | 1 GiB | ~$0.0136 | ~$9.85 |
                  > > >> | 🇺🇸 Virgínia do Norte (us-east-1) | t3.micro | 2 | 1 GiB | ~$0.0104 | ~$7.59 |
                  > > >>
                  > > >> > Valores estimados via [AWS Pricing Calculator](https://calculator.aws/pricing/2/home). Consultar calculadora para valores atualizados.
                  > > >> >
                  > > >> > ### 🏆 Escolha Recomendada: São Paulo (BR)
                  > > >> >
                  > > >> > Apesar de a região da **Virgínia do Norte ser ~23% mais barata**, a escolha recomendada é **São Paulo (sa-east-1)** pelos seguintes motivos:
                  > > >> >
                  > > >> > **1. Restrições Legais (LGPD)**
                  > > >> > A Lei Geral de Proteção de Dados (Lei 13.709/2018) restringe a transferência de dados pessoais para o exterior sem garantias adequadas. Como os sensores coletam dados de produção agrícola que podem estar vinculados a pessoas (produtores rurais), manter os dados no Brasil garante conformidade com a LGPD.
                  > > >> >
                  > > >> > **2. Latência e Acesso Rápido**
                  > > >> > Com os sensores físicos localizados no Brasil, armazenar e processar os dados na região de São Paulo minimiza a latência de comunicação entre os sensores e a API de ML, garantindo respostas mais rápidas e confiáveis.
                  > > >> >
                  > > >> > **3. Soberania de Dados**
                  > > >> > Manter os dados em território nacional garante que estejam sujeitos à jurisdição brasileira, evitando riscos legais de exposição a legislações estrangeiras (ex: Patriot Act nos EUA).
                  > > >> >
                  > > >> > ### 🎬 Vídeo Demonstrativo – Entrega 2
                  > > >> >
                  > > >> > > ⚠️ **Link do vídeo será adicionado aqui após a gravação**
                  > > >> > > >
                  > > >> > > >> 📹 YouTube (não listado): `[LINK_DO_VIDEO_AWS_AQUI]`
                  > > >> > > >>
                  > > >> > > >> ---
                  > > >> > > >>
                  > > >> > > >> ## 🚀 Como Executar o Notebook
                  > > >> > > >>
                  > > >> > > >> 1. Clique no botão **"Open in Colab"** no topo do notebook
                  > > >> > > >> 2. 2. No Google Colab, vá em **Ambiente de execução > Executar tudo**
                  > > >> > > >>    3. 3. O dataset é carregado automaticamente do Google Drive
                  > > >> > > >>      
                  > > >> > > >>       4. ---
                  > > >> > > >>      
                  > > >> > > >>       5. ## 📚 Tecnologias Utilizadas
                  > > >> > > >>      
                  > > >> > > >>       6. - **Python 3.x**
                  > > >> > > >> - **Pandas / NumPy** – Manipulação de dados
                  > > >> > > >> - - **Matplotlib / Seaborn** – Visualização
                  > > >> > > >>   - - **Scikit-learn** – Machine Learning (KMeans, Regressão, Métricas)
                  > > >> > > >>     - - **Google Colab** – Ambiente de execução
                  > > >> > > >>       - - **AWS** – Infraestrutura em nuvem
                  > > >> > > >>        
                  > > >> > > >>         - ---
                  > > >> > > >>
                  > > >> > > >> *FIAP – Inteligência Artificial | Fase 5 – 2026*
