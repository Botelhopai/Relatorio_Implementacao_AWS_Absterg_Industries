# RELATÓRIO DE IMPLEMENTAÇÃO DE SERVIÇOS AWS

**Data:** 01/03/2026  
**Empresa:** Abstergo Industries  
**Responsável:** Gabriel Botelho

---

## Introdução

Este relatório apresenta o projeto de implantação inicial de Cloud Computing na empresa **Abstergo Industries**, uma empresa farmacêutica que atua como **hub de distribuição**, integrando-se com múltiplos parceiros (laboratórios, distribuidores regionais, operadoras logísticas e redes varejistas).

Ao ingressar na empresa, foi identificado que **não havia qualquer serviço em cloud implementado**, com toda a operação baseada em servidores on‑premises, alto custo de manutenção, baixa escalabilidade e riscos operacionais.

O objetivo deste projeto foi **implementar três serviços AWS estratégicos**, priorizando:
- Redução imediata de custos operacionais
- Aumento de disponibilidade e segurança
- Base para futuras integrações B2B e crescimento do negócio

---

## Descrição do Projeto

O projeto foi dividido em **3 etapas**, cada uma focada em uma dor crítica da empresa e com impacto direto na redução de custos.

---

### Etapa 1 – Armazenamento Centralizado e Seguro

- **Ferramenta:** Amazon S3 (Simple Storage Service)  
- **Foco:** Redução de custos com armazenamento e backup

#### Caso de Uso

A Abstergo Industries armazenava:
- Notas fiscais
- Laudos farmacêuticos
- Ordens de distribuição
- Relatórios regulatórios (ANVISA)

Esses arquivos estavam distribuídos em servidores locais, com alto custo de hardware, backup manual e risco de perda de dados.

#### Por que o Amazon S3?
- Custo significativamente menor comparado a storage on‑premises
- Alta durabilidade (11 noves)
- Integração nativa com outros serviços AWS
- Possibilidade de versionamento e criptografia

#### Como foi implementado
1. Criação de buckets S3 separados por domínio (Financeiro, Logística, Regulatórios)
2. Ativação de **Versionamento** para proteção contra exclusão acidental
3. Criptografia automática com **SSE‑S3**
4. Política de **Lifecycle** movendo arquivos antigos para S3 Glacier

**Resultado esperado:**
- Redução imediata de custos com servidores físicos
- Backup automatizado
- Maior segurança e compliance

---

### Etapa 2 – Otimização de Custos Computacionais

- **Ferramenta:** Amazon EC2 + AWS Auto Scaling  
- **Foco:** Redução de custos com servidores e elasticidade

#### Caso de Uso

A empresa utilizava servidores locais superdimensionados para:
- ERP logístico
- Integrações com parceiros
- Processamento de pedidos

Esses servidores ficavam ociosos fora do horário de pico, gerando custos desnecessários.

#### Por que Amazon EC2 com Auto Scaling?
- Pagamento apenas pelo uso
- Escalabilidade automática conforme demanda
- Eliminação de custos com hardware e manutenção

#### Como foi implementado
1. Migração gradual das aplicações para instâncias EC2
2. Criação de **Auto Scaling Groups** para ajustar capacidade conforme volume de pedidos
3. Uso de instâncias **t3/t4g** para workloads leves
4. Agendamento de desligamento automático fora do horário comercial

**Resultado esperado:**
- Redução de custos com infraestrutura
- Melhor performance em períodos de pico
- Maior disponibilidade para parceiros B2B

---

### Etapa 3 – Governança e Controle de Custos

- **Ferramenta:** AWS Cost Explorer + AWS Budgets  
- **Foco:** Controle financeiro e previsibilidade de gastos

#### Caso de Uso

Antes da cloud, não havia visibilidade clara de custos de TI. Com a migração, tornou‑se essencial evitar desperdícios e surpresas na fatura AWS.

#### Por que AWS Cost Explorer e Budgets?
- Visibilidade detalhada dos custos por serviço
- Alertas proativos de gastos
- Apoio à tomada de decisão

#### Como foi implementado
1. Criação de **tags de custo** por área (Logística, Financeiro, TI)
2. Configuração de **AWS Budgets** com alertas por e‑mail
3. Análise semanal de consumo via Cost Explorer

**Resultado esperado:**
- Controle rigoroso dos gastos
- Identificação rápida de desperdícios
- Cultura de FinOps na empresa

---

## Conclusão

A implementação dos serviços AWS na **Abstergo Industries** trouxe benefícios imediatos, como:
- Redução de custos operacionais
- Maior segurança e confiabilidade dos dados
- Escalabilidade para atender o crescimento do hub de distribuição

Este projeto estabelece uma base sólida para futuras evoluções, como:
- Integrações via APIs
- Data analytics
- Machine Learning para previsão de demanda

Recomenda‑se a continuidade da migração para a nuvem e a adoção de novos serviços AWS alinhados à estratégia do negócio.

---

## Anexos

- Arquitetura inicial em diagrama
- Políticas de segurança S3
- Relatório de custos comparativo (On‑premises x AWS)

---

**Assinatura do Responsável pelo Projeto:**  

Gabriel Botelho

