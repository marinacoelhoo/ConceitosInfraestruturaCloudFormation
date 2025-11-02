# ☁️ Infraestrutura Automatizada com AWS CloudFormation  

> Repositório contendo anotações e insights sobre o uso do **AWS CloudFormation** para criação e gerenciamento automatizado de infraestrutura na nuvem.  

---

## 📘 **Descrição**

O **AWS CloudFormation** é um serviço que permite **definir, provisionar e gerenciar recursos da AWS por meio de código** — seguindo o conceito de **Infrastructure as Code (IaC)**.  
Com ele, é possível **automatizar** a criação de instâncias, redes, bancos de dados e outros serviços, garantindo **consistência, segurança e escalabilidade** em todos os ambientes.

---

## 🧠 **Conceitos Fundamentais**

| Conceito | Descrição |
|-----------|------------|
| 🧱 **Stack (Pilha)** | Conjunto de recursos criados e gerenciados como uma unidade única. |
| 📄 **Template** | Arquivo em **YAML ou JSON** que descreve todos os recursos da infraestrutura. |
| 🔁 **Change Set** | Visualização das alterações antes de aplicá-las a uma Stack existente. |
| 🚀 **Provisionamento** | Processo automatizado de criação, atualização ou exclusão de recursos na AWS. |

---

## ⚙️ **Como Funciona o CloudFormation**

1. ✍️ **Criação do Template**  
   Você define toda a infraestrutura desejada (EC2, S3, RDS, IAM, etc.) em um arquivo YAML.  

2. 🧩 **Criação da Stack**  
   O CloudFormation lê o template e cria automaticamente todos os recursos na ordem correta.  

3. 🔄 **Atualizações Controladas**  
   Com Change Sets, é possível visualizar as alterações antes de aplicá-las.  

4. 🧹 **Deleção Segura**  
   Ao excluir uma Stack, todos os recursos são removidos de forma controlada.  

---

## 💡 **Casos de Uso**

- 🏗️ Criação automatizada de ambientes de **desenvolvimento, teste e produção**.  
- 🧰 Padronização da infraestrutura em **múltiplas regiões ou contas AWS**.  
- 🔄 Integração com **pipelines de CI/CD** para implantação contínua.  
- 📦 Montagem de **ambientes completos** (EC2, RDS, VPC, IAM, etc.) com apenas um comando.  
- 🧪 **Ambientes temporários** para experimentação e testes automatizados.  

---

## 🌍 **Importância da Infraestrutura Automatizada**

A automação com **AWS CloudFormation** traz grandes benefícios para organizações e desenvolvedores:

| Benefício | Descrição |
|------------|------------|
| ⚙️ **Automação Completa** | Elimina tarefas manuais e reduz erros humanos. |
| 🧩 **Infraestrutura como Código (IaC)** | Permite versionar e auditar a infraestrutura como um software. |
| 🔁 **Reprodutibilidade** | Criação de ambientes idênticos e previsíveis. |
| 🔒 **Segurança e Controle** | Garante rollback automático em caso de falhas. |
| 💰 **Otimização de Custos** | Facilita a criação e exclusão de recursos conforme a demanda. |
| 🚀 **Integração DevOps** | Perfeito para pipelines de CI/CD e práticas ágeis. |

---

## 🧭 **Arquitetura do CloudFormation**

A imagem abaixo ilustra o funcionamento básico do **AWS CloudFormation**, mostrando como templates são processados e transformados em recursos reais da AWS:


> 🔍 O CloudFormation interpreta o template, cria uma **Stack** e gerencia automaticamente todos os recursos necessários (EC2, S3, RDS, IAM, etc.), garantindo **consistência e automação total**.

---

## 📜 **Exemplo de Template (YAML)**

```yaml
AWSTemplateFormatVersion: "2010-09-09"
Description: Template simples para criar uma instância EC2

Resources:
  MyEC2Instance:
    Type: "AWS::EC2::Instance"
    Properties:
      InstanceType: t2.micro
      ImageId: ami-0c55b159cbfafe1f0
      Tags:
        - Key: Name
          Value: EC2CloudFormationDemo
