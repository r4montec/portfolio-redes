# Laboratório 01 — Comunicação Básica

## 🎯 Objetivo

Realizar a configuração básica de uma rede local e verificar a comunicação entre dois dispositivos utilizando um switch no Cisco Packet Tracer.

## 🖥️ Topologia

A topologia é composta por:

- 1 Switch Cisco 2960-24TT
- 2 computadores (PC0 e PC1)
- Conexões Ethernet entre os dispositivos

```text
           ┌─────────────────┐
           │  Cisco 2960-24TT│
           │     Switch      │
           └────────┬────────┘
                    │
             ┌──────┴──────┐
             │             │
          ┌──┴──┐       ┌──┴──┐
          │ PC0 │       │ PC1 │
          └─────┘       └─────┘

🌐 Endereçamento IPv4

Dispositivo /Endereço IPv4/	Máscara de Sub-rede	  Gateway
PC0	      192.168.1.10	    255.255.255.0	       0.0.0.0
PC1	      192.168.1.20	     255.255.255.0	      0.0.0.0

Os dois dispositivos pertencem à rede 192.168.1.0/24.

🔧 Configuração

Os endereços IPv4 foram configurados manualmente utilizando endereçamento estático.
O gateway padrão não foi configurado, pois o laboratório não possui um roteador e a comunicação ocorre exclusivamente dentro da rede local.

🧪 Teste de Conectividade

Foram realizados testes utilizando o comando ping.

PC0 → PC1
ping 192.168.1.20
PC1 → PC0
ping 192.168.1.10
Resultado

Os dois testes apresentaram respostas com sucesso, confirmando a comunicação entre os computadores através do switch.

📚 Conceitos Praticados

Comunicação em rede local (LAN)
Endereçamento IPv4
Máscara de sub-rede
Endereçamento estático
Funcionamento básico de switches
Teste de conectividade utilizando ping
Comunicação entre hosts pertencentes à mesma sub-rede

🛠️ Ferramenta
Cisco Packet Tracer
