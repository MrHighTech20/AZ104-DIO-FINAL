# AZ104-DIO-FINAL
Projeto de fim de curso da AZ-104 da DIO

# 📊 Monitoramento de Máquinas Virtuais no Azure

Este repositório documenta as etapas realizadas para configurar o monitoramento de máquinas virtuais (VMs) no Microsoft Azure, com foco na criação de alertas para eventos críticos como a **exclusão de VM** e o **uso elevado de CPU**.

Este projeto foi desenvolvido como parte do desafio prático da plataforma **DIO (Digital Innovation One)**.

---

## ✅ Objetivos do Projeto

- Demonstrar, na prática, como configurar o monitoramento de uma VM no Azure.
- Criar alertas baseados em logs e métricas do sistema.
- Documentar o processo técnico de forma clara e reprodutível.
- Utilizar o GitHub como repositório público de conhecimento.

---

## 🧰 Tecnologias e Serviços Utilizados

- Microsoft Azure
- Azure Monitor
- Log Analytics Workspace
- Azure Alerts
- Azure Activity Log

---

## 🖥️ Etapas Realizadas

### 1. Criação da Máquina Virtual (VM)

- Criada uma VM Linux/Windows no portal do Azure.
- Região, grupo de recursos e opções padrão selecionadas.
- Monitoramento e diagnósticos ativados durante a criação.

### 2. Ativação do Monitoramento

- Ativado o **diagnóstico de inicialização** da VM.
- Instalado o **Azure Monitor Agent** na VM via "Extensões + aplicativos".
- Criado e vinculado um **Log Analytics Workspace**.

### 3. Criação de Alerta de Exclusão da VM

- Criada uma **nova regra de alerta** no Azure Monitor.
- **Recurso**: assinatura do Azure.
- **Condição**: `Delete Virtual Machine (Microsoft.Compute/virtualMachines/delete)`
- **Grupo de Ações**: e-mail de notificação configurado.
- Resultado: se a VM for excluída, um e-mail é enviado imediatamente.

### 4. Criação de Alerta por Uso de CPU

- Nova regra de alerta configurada com a métrica:
  - `Percentual de uso da CPU`
  - Condição: **maior que 80% por 5 minutos**
- Ações: notificação por e-mail.
- Resultado: caso a CPU da VM esteja sobrecarregada, o alerta é disparado.

---
