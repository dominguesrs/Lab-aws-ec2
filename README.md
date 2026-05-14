# Lab AWS: Gerenciamento de Instâncias EC2, AMIs e Snapshots EBS

## 📋 Descrição do Projeto
Este repositório contém a documentação técnica, anotações e insights adquiridos durante o laboratório prático de gerenciamento de infraestrutura computacional na AWS. O objetivo principal foi entender o ciclo de vida de instâncias EC2, garantindo a persistência de dados com Snapshots EBS e a escalabilidade/padronização com a criação de AMIs personalizadas.

## 🚀 Tecnologias Utilizadas
* **Cloud Provider:** Amazon Web Services (AWS)
* **Serviços:** Amazon EC2 (Elastic Compute Cloud), EBS (Elastic Block Store), AMI (Amazon Machine Image).
* **Documentação & Controle de Versão:** Git e GitHub.

---

## 🛠️ Passo a Passo do Laboratório & Insights

### 1. Inicialização da Instância EC2
* **O que foi feito:** Criação de uma instância EC2 (`t3.micro`) utilizando o sistema operacional [Amazon Linux 2023 - Free tier].
* **Configuração:** Instalação e inicialização de um servidor básico .
* **Insight Técnico:** Configurar o *Security Group* corretamente (liberando a porta 22 para SSH), seguindo o princípio do privilégio mínimo.
* **Print da criação da AMI: `![Criando EC2](imagens/ec2-instance-00.png)`*
* <img width="1099" height="483" alt="ec2-instance-00" src="https://github.com/user-attachments/assets/73164d95-ea4f-4cb2-aebc-da9f83504dba" />

* **Print da criação da AMI: `![Criando EC2](imagens/ec2-instance-01.png)`*
* <img width="1341" height="523" alt="ec2-instance-01" src="https://github.com/user-attachments/assets/8578ffd8-3c45-4b04-b9c2-0c6501844045" />

* **Print da criação da AMI: `![Criando EC2](imagens/ec2-instance-02.png)`*
* <img width="1312" height="531" alt="ec2-instance-02" src="https://github.com/user-attachments/assets/7b7a0655-a20a-45c2-a4a3-d8a13684a145" />


### 2. Criação de Snapshot EBS
* **O que foi feito:** Criação de um backup estático (Snapshot) a partir do volume de armazenamento (EBS) da instância principal.
* **Insight Técnico:** O uso do Snapshot da AWS. Ele é ideal para backups de dados, pode ser transformado em um novo volume a qualquer momento, garantindo resiliência contra falhas ou perda de dados.
* **Print do snapshot: `![Snapshot EBS](imagens/snapshot-created.png)`*
* <img width="1329" height="531" alt="snapshot-created" src="https://github.com/user-attachments/assets/1bc7cd31-34a0-47e0-99e1-518fc7fe4df1" />


### 3. Criação e Validação de AMI Personalizada
* **O que foi feito:** Criação de uma Amazon Machine Image (AMI) a partir da instância EC2 configurada no passo 1. Em seguida, uma nova instância foi provisionada utilizando essa nova AMI como base.
* **Insight Técnico:** A AMI funciona como um "template" completo (SO + Aplicação + Configurações). Ao lançar a nova instância, o servidor já subiu funcionando perfeitamente, sem necessidade de reconfiguração manual. 
* **Print da criação da AMI: `![Criando AMI](imagens/restore-instance-00.png)`*
* <img width="1329" height="531" alt="restore-instance-00" src="https://github.com/user-attachments/assets/b237888e-7b62-4f3e-b176-0ac2e6d01e65" />

* **Print da criação da AMI: `![Criando AMI](imagens/restore-instance-01.png)`*
* <img width="1340" height="549" alt="restore-instance-01" src="https://github.com/user-attachments/assets/f80fda0c-a973-483f-95bc-b0cf877b117a" />


---

## 🧠 Conclusões e Aprendizados
* **Diferença entre Snapshot e AMI:** O Snapshot foca no backup do **volume de dados** (disco rígido), enquanto a AMI é um **pacote de inicialização completo** que inclui o mapeamento de blocos, informações do sistema operacional e permissões de boot para criar novas máquinas.
