# 🏥 Proposta de Implementação de Serviços AWS

## 📊 Etapa 1: Otimização de Custos e Infraestrutura

**🛠️ Ferramenta:** AWS Cost Explorer e AWS Trusted Advisor

**🎯 Foco da ferramenta:** Gerenciamento e otimização de custos e uso de recursos na nuvem.

Descrição de caso de uso: Inicialmente, a Abstergo Industries não tem infraestrutura na nuvem, o que exige um planejamento cuidadoso para evitar gastos desnecessários. O AWS Cost Explorer permite visualizar, entender e gerenciar os custos e o uso da AWS ao longo do tempo, fornecendo relatórios que exibem os principais gastos. Já o AWS Trusted Advisor oferece recomendações para aderir às melhores práticas e reduzir custos, identificando, por exemplo, instâncias ociosas do EC2 ou endereços IP elásticos não associados. A implementação dessas ferramentas de monitoramento e análise é crucial para garantir que a empresa pague apenas pelo que realmente usa e para obter descontos com modelos flexíveis como Savings Plans e instâncias reservadas.

## ⚡ Etapa 2: Automação e Escalabilidade de Infraestrutura

**🛠️ Ferramenta:** Amazon EC2 (Elastic Compute Cloud) com Auto Scaling

**🎯 Foco da ferramenta:** Fornecer servidores virtuais escaláveis sob demanda para hospedar aplicações e sistemas.

Descrição de caso de uso: Como um hub de distribuição e revenda, a Abstergo Industries precisa de uma infraestrutura flexível que se adapte às variações de demanda, especialmente em picos de vendas. O Amazon EC2 oferece servidores virtuais (instâncias) que substituem a infraestrutura física, permitindo ajustar os recursos de forma eficiente e flexível. A integração com o AWS Auto Scaling ajusta a capacidade de computação automaticamente, garantindo que a empresa não pague por recursos em horários de baixa demanda e, ao mesmo tempo, evite problemas de desempenho em momentos de alta atividade. O modelo de pagamento flexível do EC2, onde se paga apenas pelo uso, contribui diretamente para a redução de custos.

## 💾 Etapa 3: Armazenamento e Gerenciamento de Dados

**🛠️ Ferramentas:** Amazon S3 (Simple Storage Service) e Amazon RDS (Relational Database Service)

**🎯 Foco das ferramentas:** Armazenamento de dados escalável, seguro e gerenciado, separando dados não estruturados de dados transacionais.

Descrição de caso de uso: A Abstergo Industries gerencia um grande volume de dados de naturezas distintas. Para uma arquitetura robusta e escalável, é crucial utilizar o serviço correto para cada tipo de dado:

**📦 Amazon S3:** Ideal para armazenar dados não estruturados (objetos) de forma centralizada, segura e com alta durabilidade. Será utilizado para hospedar imagens e arquivos de produtos para o site de e-commerce, backups de bancos de dados e documentos importantes. Seu modelo de precificação baseado no uso é econômico e elimina a necessidade de provisionar armazenamento antecipadamente.

**🗄️ Amazon RDS:** Essencial para dados estruturados e transacionais, como informações de clientes, catálogos de produtos e processamento de pedidos. O RDS automatiza tarefas de gerenciamento de banco de dados, como provisionamento, patches e backups, garantindo alta disponibilidade e permitindo que a equipe foque na aplicação. Utilizar um serviço gerenciado como o RDS é fundamental para a segurança e a consistência dos dados críticos do negócio.

## 🎯 Principais Ganhos com a Implementação
A implementação dos serviços AWS propostos trará os seguintes benefícios para a Abstergo Industries:

**💰 Redução de custos:** Através do monitoramento com o AWS Cost Explorer e as recomendações do AWS Trusted Advisor, a empresa terá visibilidade total dos gastos e poderá otimizar o uso de recursos, eliminando desperdícios. O uso de instâncias sob demanda e o auto-escalonamento do Amazon EC2 garantem que a empresa pague apenas pela capacidade de computação utilizada, evitando o custo fixo de servidores físicos.

**📈 Escalabilidade e Agilidade:** A infraestrutura na nuvem permite que a empresa expanda ou diminua a capacidade de computação (Amazon EC2) e armazenamento (Amazon S3 e RDS) de forma automática e instantânea, adaptando-se à demanda do negócio sem a necessidade de aquisição de hardware. Isso é fundamental para um hub de distribuição que lida com volumes variáveis de pedidos.

**⚙️ Eficiência Operacional:** Ao migrar para a nuvem, a empresa pode modernizar sua cadeia de suprimentos e obter maior agilidade e resiliência. A automação de processos, como o ajuste de capacidade do EC2 e o gerenciamento do RDS, libera a equipe de TI para focar em iniciativas estratégicas. A separação dos dados no S3 e RDS facilita o acesso, a gestão e a segurança da informação.

## 🏗️ Conclusão e Arquitetura Final

A análise inicial da proposta revelou uma base sólida, mas com uma lacuna crítica: a ausência de um banco de dados transacional para gerenciar dados estruturados como pedidos e clientes. A proposta original focava no S3 para todos os tipos de dados, o que não é uma prática recomendada para aplicações de e-commerce.

A arquitetura final, refletida no diagrama atualizado, corrige essa divergência ao incorporar tanto o Amazon RDS quanto o Amazon S3. Essa abordagem híbrida é fundamental para o sucesso da aplicação:

- **🗄️ Amazon RDS:** Garante a integridade, consistência e performance das operações transacionais (vendas, cadastros).
- **📦 Amazon S3:** Serve como um repositório econômico e altamente durável para dados não estruturados (imagens de produtos, backups).

Essa arquitetura alinhada não só segue as melhores práticas da AWS, mas também fornece à Abstergo Industries uma fundação segura, escalável e com custos otimizados para o seu crescimento futuro.