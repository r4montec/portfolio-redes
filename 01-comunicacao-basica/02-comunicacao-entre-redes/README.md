# Laboratório 02 — Comunicação entre Redes

## 🎯 Objetivo

Implementar e validar a comunicação entre duas redes IPv4 distintas utilizando um roteador como gateway padrão.

O laboratório demonstra como um roteador permite a comunicação entre dispositivos pertencentes a diferentes redes IP.

## 🖥️ Topologia

A topologia é composta por:

- 1 Switch Cisco 2960-24TT
- 1 Roteador Cisco 1941
- 2 computadores
- Conexões Ethernet entre os dispositivos

```text
PC001
192.168.2.10/24
Gateway: 192.168.2.1
       │
       │
    Switch
       │
       │
Router1
G0/0: 192.168.1.1/24
G0/1: 192.168.2.1/24
       │
       │
    Switch
       │
       │
PC00
192.168.1.10/24
Gateway: 192.168.1.1.

🌐 Endereçamento IPv4
Dispositivo	Interface	IPv4	Máscara	Gateway
PC00	FastEthernet0	192.168.1.10	255.255.255.0	192.168.1.1
PC001	FastEthernet0	192.168.2.10	255.255.255.0	192.168.2.1
Router1	GigabitEthernet0/0	192.168.1.1	255.255.255.0	—
Router1	GigabitEthernet0/1	192.168.2.1	255.255.255.0	—
🔧 Configuração do Roteador

O Router1 possui duas interfaces GigabitEthernet, cada uma conectada a uma rede diferente:

GigabitEthernet0/0 → 192.168.1.1/24
GigabitEthernet0/1 → 192.168.2.1/24

As duas interfaces estão com estado up/up.

🛣️ Tabela de Roteamento

Foi utilizado o comando:

show ip route

O resultado apresentou as duas redes como diretamente conectadas:

C 192.168.1.0/24 is directly connected, GigabitEthernet0/0
C 192.168.2.0/24 is directly connected, GigabitEthernet0/1

Isso demonstra que o roteador possui conhecimento direto das duas redes e pode encaminhar pacotes entre elas.

🚪 Default Gateway

Cada computador utiliza o endereço da interface do roteador pertencente à sua própria rede como gateway padrão.

PC00 → 192.168.1.1
PC001 → 192.168.2.1

Quando um computador precisa se comunicar com um destino localizado em outra rede, o tráfego é encaminhado para o gateway padrão.

🧪 Testes de Conectividade

Foram realizados testes de comunicação entre os dois computadores utilizando o comando ping.

PC001 → PC00
ping 192.168.1.10

Resultado:

Packets: Sent = 4, Received = 4, Lost = 0 (0% loss)

Resultado: Comunicação realizada com sucesso.

PC00 → PC001
ping 192.168.2.10

Resultado:

Packets: Sent = 4, Received = 3, Lost = 1 (25% loss)

Apesar do primeiro pacote apresentar timeout, os três pacotes seguintes foram recebidos com sucesso, confirmando a comunicação entre as redes.

O comportamento inicial pode estar relacionado à resolução ARP necessária para estabelecer a comunicação.

📚 Conceitos Praticados

Endereçamento IPv4
Máscara de sub-rede
Redes distintas
Default Gateway
Roteamento entre redes
Interfaces GigabitEthernet
Rotas diretamente conectadas
Comando show ip interface brief
Comando show ip route
Teste de conectividade com ping

🛠️ Ferramenta

Cisco Packet Tracer
