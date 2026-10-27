# Sorriso Metálico

## Introdução

Este repositório é destinado ao cliente Dr. Roberto, responsável pela clínica odontológica Sorriso Metálico.

O objetivo do sistema é auxiliar no gerenciamento da clínica, permitindo cadastrar pacientes e dentistas, controlar a agenda de consultas, registrar pagamentos e manter o histórico de procedimentos realizados.

#MER
### **1\. Paciente**

* id\_paciente — SERIAL PRIMARY KEY  
* nome — VARCHAR(100)  
* cpf — CHAR(11)  
* telefone — VARCHAR(11)

### **2\. Dentista**

* id\_dentista — SERIAL PRIMARY KEY  
* nome — VARCHAR(100)  
* cro — VARCHAR(20)  
* telefone — VARCHAR(11)

### **3\. Consulta**

* id\_consulta — SERIAL PRIMARY KEY  
* data\_consulta — DATE  
* horario — TIME  
* status — ENUM('Agendada', 'Cancelada', 'Realizada', 'Remarcada')  
* procedimento — TEXT  
* forma\_pagamento — ENUM('PIX', 'Dinheiro', 'Débito', 'Crédito')  
* valor — NUMERIC(10,2)  
* tipo\_paciente — ENUM('Normal', 'VIP')  
* id\_paciente — INTEGER FOREIGN KEY  
* id\_dentista — INTEGER FOREIGN KEY

## **Relacionamentos**

* Paciente — Consulta (1:N): um paciente pode realizar várias consultas, mas cada consulta pertence a um único paciente.  
* Dentista — Consulta (1:N): um dentista pode atender várias consultas, mas cada consulta está associada a um único dentista.
  <img width="1345" height="752" alt="image" src="https://github.com/user-attachments/assets/7896d3b9-a869-4a8b-86ec-40b71576864d" />
