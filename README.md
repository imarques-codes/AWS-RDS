# AWS-RDS
WS Lab: Implementação de Banco de Dados Gerenciado com Amazon RDS 

Este repositório contém registro técnico. O foco do projeto foi a criação de uma infraestrutura de banco de dados relacional resiliente, segura e integrada a uma aplicação web real.

## Visão Geral
O objetivo principal foi reforçar o conceito de utilização do **Amazon Relational Database Service (Amazon RDS)** para atender necessidades de bancos de dados relacionais, delegando tarefas administrativas pesadas (backups, patches e replicação) para a AWS.

## Objetivos do Aprendizado
* **Alta Disponibilidade:** Lançamento de instância RDS com configuração Multi-AZ.
* **Segurança e Conectividade:** Configuração de Security Groups para isolamento de rede.
* **Integração de Aplicação:** Conexão de um Web Server a uma camada de dados persistente.

---

## Cenário da Infraestrutura
Atuei como Administrador de Nuvem para hospedar uma aplicação web, separando a **Camada de Aplicação** (EC2) da **Camada de Dados** (RDS), seguindo as melhores práticas de arquitetura em nuvem.

### Componentes Técnicos:
* **Motor de Banco de Dados:** MySQL.
* **Modelo de Implantação:** Desenvolvimento/Teste com Multi-AZ.
* **Segurança:** Firewall configurado na porta `3306`, aceitando tráfego apenas do SG do Servidor Web.

---

## Etapas do Projeto

1.  **Segurança de Rede:** Criação de um Grupo de Segurança específico para o banco de dados, restringindo o acesso apenas ao servidor web.
2.  ![Security group](./screenshots/rds sg.png)
3.  **Configuração de Sub-redes:** Definição de um Grupo de Sub-redes de Banco de Dados para determinar em quais zonas da VPC o RDS poderia operar.
4.  **Provisionamento do RDS:** Instalação de uma instância MySQL com **Alta Disponibilidade (Multi-AZ)**, garantindo que, em caso de falha em uma Zona de Disponibilidade, uma instância de reserva assuma automaticamente (**Failover**).
5.  **Integração e Teste:**
    * Acesso ao aplicativo via IP público do servidor web.
    * Configuração do *Endpoint* do banco de dados na aplicação.
    * Realização de testes de persistência (leitura e escrita de dados).

---

## Benefícios do Amazon RDS Observados
* **Gerenciamento Simplificado:** Foco no aplicativo, enquanto a AWS cuida da infraestrutura e manutenção.
* **Resiliência:** O mecanismo de failover automático minimiza o tempo de inatividade e evita perda de dados.
* **Escalabilidade:** Capacidade de redimensionar recursos conforme a demanda da aplicação.

---

## Conclusão
Este laboratório demonstrou a importância de utilizar serviços gerenciados para aumentar a confiabilidade de sistemas. A separação entre servidor web e banco de dados é um pilar fundamental para arquiteturas escaláveis e seguras na nuvem.

---
**Curso:** AWS Cloud Foundations  
**Ferramentas:** AWS Management Console, Amazon RDS, Amazon EC2, VPC.
