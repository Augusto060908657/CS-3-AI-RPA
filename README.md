# CS-3-AI-RPA

**Instituição / Curso:** FIAP / Inteligência Artiicial  
**Disciplina:** RPA 
**Professor:** Orlando  
**Alunos / Equipe:** 
- Octavio Augusto Ramalho Brandão Pires - RM: 555696

--- 
## Link Colab: https://colab.research.google.com/drive/1MmxP_J4VBHB4EkOkJz3kkGim6h6O8qaY?usp=sharing

## Sobre o Projeto

Nesta etapa da sprint, o nosso Digital Twin ganha "vida" e passa da fase analítica para a ação. O objetivo é projetar e implementar automações de RPA que integrem modelos de inteligência (ML/DL) e regras de negócio para automatizar a resposta da planta quando há anomalias em um motor elétrico. 

Para estruturar essa solução com robustez, o projeto foi dividido em dois pilares fundamentais:

*  **Pilar 1: Inteligência Externa (Web Scraping)**
Desenvolvemos um robô explorador que navega em fontes técnicas (tabelas normativas IEC/NEMA) para buscar limites normativos de temperatura e classes de isolamento. O objetivo é enriquecer o contexto do motor além dos dados de placa. Em caso de indisponibilidade da rede, o sistema possui um *fallback* (dataset de contingência) para garantir a continuidade da automação.

*  **Pilar 2: Automação do Ciclo de Eventos (RPA)**
O motor de regras recebe e processa a saída do diagnóstico preditivo. Ao detectar um desvio (Alerta ou Crítico), o sistema não fica parado: ele registra o evento no banco de dados histórico, atualiza dinamicamente o status de saúde do ativo e sugere ações de manutenção, tudo de forma autônoma.

---

## 📂 Estrutura do Repositório

O repositório foi organizado de forma modular e limpa, contendo apenas os arquivos essenciais para a entrega e avaliação da sprint:

```text
meu-repositorio-digital-twin/
│
├── data/
│   ├── scraping_classes_isolamento.csv   # Evidência: Dados tabulares extraídos via scraping
│   └── contexto_tecnico_motor.json       # Evidência: Contexto técnico cruzado e estruturado
│
├── db/
│   └── digital_twin.db                   # Evidência: Banco de dados SQLite com logs e status RPA
│
└── README.md                             # Documentação do projeto
