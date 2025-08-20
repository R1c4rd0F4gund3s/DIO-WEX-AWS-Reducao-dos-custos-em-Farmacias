# Precificação do Projeto AWS - Abstergo Industries

## Resumo Executivo

**Investimento Mensal Estimado: USD $85-120**  
**Economia Anual Projetada: 60-70% vs. infraestrutura física**

---

## Detalhamento de Custos por Serviço

### 1. Amazon EC2 (Compute) - Automação e Escalabilidade
**Configuração:** 2-3 instâncias t3.micro com Auto Scaling

**Descrição:** O Amazon EC2 fornece servidores virtuais escaláveis sob demanda para hospedar as aplicações da farmácia. Como hub de distribuição e revenda, a Abstergo Industries precisa de infraestrutura flexível que se adapte às variações de demanda, especialmente em picos de vendas. O EC2 oferece instâncias que substituem a infraestrutura física, permitindo ajustar recursos de forma eficiente. A integração com AWS Auto Scaling ajusta a capacidade automaticamente, garantindo que a empresa não pague por recursos em horários de baixa demanda e evite problemas de performance em momentos de alta atividade.

**Benefícios de Custo:**
- Modelo pay-as-you-use elimina custos fixos de servidores físicos
- Auto Scaling reduz custos em períodos de baixa demanda
- Instâncias t3.micro oferecem melhor custo-benefício para cargas moderadas
- Eliminação de custos de manutenção e energia de hardware físico

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Instâncias t3.micro | 2 instâncias (24/7) | $16.56 |
| Instância adicional | Picos de demanda (50% do tempo) | $8.28 |
| **Subtotal EC2** | | **$24.84** |

### 2. Application Load Balancer - Otimização de Custos e Performance
**Configuração:** ALB para distribuição de tráfego

**Descrição:** O Application Load Balancer é essencial para distribuir o tráfego entre as instâncias EC2, garantindo alta disponibilidade e performance otimizada. Funciona como ponto de entrada único para os usuários (B2B/B2C), direcionando automaticamente as requisições para instâncias saudáveis. Integra-se com o AWS Cost Explorer e Trusted Advisor para monitoramento contínuo de custos e otimização de recursos.

**Benefícios de Custo:**
- Elimina necessidade de hardware dedicado para balanceamento
- Reduz downtime e custos associados a indisponibilidade
- Otimiza uso de recursos distribuindo carga eficientemente
- Integração nativa com ferramentas de monitoramento de custos AWS
- Escalabilidade automática sem investimento adicional em infraestrutura

**Monitoramento de Custos:** O ALB trabalha em conjunto com AWS Cost Explorer para fornecer visibilidade total dos gastos de rede e processamento, permitindo identificar padrões de uso e otimizar custos através de relatórios detalhados de tráfego e performance.

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Load Balancer | 1 ALB ativo | $22.50 |
| Processamento | ~10GB/mês | $0.80 |
| **Subtotal ALB** | | **$23.30** |

### 3. Amazon RDS (Database)
**Configuração:** MySQL db.t3.micro com backup

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Instância db.t3.micro | MySQL 8.0, 20GB | $15.84 |
| Backup Storage | 7 dias retenção, ~5GB | $0.50 |
| **Subtotal RDS** | | **$16.34** |

### 4. Amazon S3 (Storage)
**Configuração:** Armazenamento de imagens e backups

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Standard Storage | 50GB imagens produtos | $1.15 |
| Requests | ~1000 PUT/GET por mês | $0.05 |
| **Subtotal S3** | | **$1.20** |

### 5. CloudWatch (Monitoring)
**Configuração:** Métricas e alarmes para Auto Scaling

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Métricas customizadas | 10 métricas | $3.00 |
| Alarmes | 5 alarmes | $0.50 |
| **Subtotal CloudWatch** | | **$3.50** |

### 6. Data Transfer & Outros
**Configuração:** Transferência de dados e custos diversos

| Item | Especificação | Custo Mensal |
|------|---------------|--------------|
| Data Transfer Out | ~20GB/mês | $1.80 |
| NAT Gateway | Para subnets privadas | $32.40 |
| **Subtotal Outros** | | **$34.20** |

---

## Resumo de Custos

| Serviço | Custo Mensal (USD) | % do Total |
|---------|-------------------|------------|
| EC2 Instances | $24.84 | 24% |
| Load Balancer | $23.30 | 23% |
| RDS Database | $16.34 | 16% |
| NAT Gateway | $32.40 | 31% |
| CloudWatch | $3.50 | 3% |
| S3 Storage | $1.20 | 1% |
| Data Transfer | $1.80 | 2% |
| **TOTAL MENSAL** | **$103.38** | **100%** |

---

## Cenários de Uso

### Cenário Conservador (Baixa Demanda)
- **Custo Mensal:** $85
- 2 instâncias EC2 na maior parte do tempo
- Tráfego reduzido

### Cenário Padrão (Demanda Normal)
- **Custo Mensal:** $103
- Auto Scaling ativo com 2-3 instâncias
- Tráfego moderado

### Cenário Pico (Alta Demanda)
- **Custo Mensal:** $120
- 3 instâncias EC2 constantemente ativas
- Alto volume de transações

---

## Comparação com Infraestrutura Tradicional

### Custos Infraestrutura Física (Estimativa)

| Item | Custo Inicial | Custo Mensal |
|------|---------------|--------------|
| Servidores (3x) | $15,000 | $200 (energia/manutenção) |
| Storage/Backup | $5,000 | $50 |
| Rede/Firewall | $3,000 | $30 |
| Licenças Software | $2,000 | $100 |
| Pessoal TI | - | $2,000 |
| **TOTAL** | **$25,000** | **$2,380** |

### Economia com AWS
- **Investimento inicial:** $0 vs $25,000
- **Custo operacional:** $103/mês vs $2,380/mês
- **Economia mensal:** $2,277 (95%)
- **ROI:** Imediato

---

## Otimizações de Custo Recomendadas

### Curto Prazo (0-3 meses)
1. **Reserved Instances:** Economia de 30-40% no EC2
2. **S3 Intelligent Tiering:** Redução automática de custos de storage
3. **CloudWatch Logs Retention:** Configurar retenção otimizada

### Médio Prazo (3-12 meses)
1. **Savings Plans:** Economia de até 72% em compute
2. **Spot Instances:** Para workloads não críticos
3. **S3 Lifecycle Policies:** Migração automática para classes mais baratas

### Estimativa com Otimizações
- **Economia adicional:** 30-50%
- **Custo otimizado:** $50-70/mês

---

## Projeção Anual

| Ano | Sem Otimização | Com Otimização | Economia |
|-----|----------------|----------------|----------|
| Ano 1 | $1,240 | $840 | $400 |
| Ano 2 | $1,240 | $720 | $520 |
| Ano 3 | $1,240 | $600 | $640 |

---

## Benefícios Financeiros Adicionais

### Redução de Custos Operacionais
- **Eliminação de CAPEX:** Sem investimento inicial em hardware
- **Redução de OPEX:** Menor custo de manutenção e energia
- **Eficiência de TI:** Equipe focada em desenvolvimento vs. infraestrutura

### Flexibilidade Financeira
- **Pay-as-you-use:** Pagamento apenas pelo consumo real
- **Escalabilidade:** Crescimento sem grandes investimentos
- **Previsibilidade:** Custos mensais controlados

---

## Recomendações de Implementação

### Fase 1 (Mês 1-2): Setup Básico
- **Orçamento:** $103/mês
- Implementação da arquitetura base
- Monitoramento inicial de custos

### Fase 2 (Mês 3-6): Otimização
- **Orçamento:** $70/mês
- Implementação de Reserved Instances
- Configuração de políticas de lifecycle

### Fase 3 (Mês 6+): Expansão
- **Orçamento:** Variável conforme crescimento
- Scaling baseado em demanda real
- Implementação de Savings Plans

---

## Conclusão

A migração para AWS representa uma **economia imediata de 95%** comparada à infraestrutura tradicional, com investimento mensal de apenas **$85-120** versus **$2,380** do modelo físico.

**Principais vantagens financeiras:**
- Zero investimento inicial
- Custos operacionais 95% menores
- Escalabilidade sem grandes investimentos
- ROI imediato

**Recomendação:** Iniciar com a configuração padrão e implementar otimizações progressivamente para maximizar a economia.