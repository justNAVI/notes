
# O que e a internet?

- Constituida basicamente de canais de comunicacao 
- Internet e uma rede interconectada por meio de cabos metalicos
- Utiliza dispositivos como roteadores, switches, modems, antenas e etc
- Comunicacao cliente -> servidor

# IP

- Protocolo usado para identificar dispositivos ou conexoes 
- IP que reconhece a comunicao entre dois dispositivos distintos e o TCP/IP
- IP interno != IP externo
- IP dinamico != IP fixo
- IPv4 != IPv6

# MAC

- Media Access Control
- Endereco fisico do dipositivo
- Numero de serie de 48 bits
- Serve para identificar dispositivo de rede Rthernet ou WiFi globalmente
- Existe a possibilidade de mudanca de MAC (gambiarra)
- Se o destino nao esta na mesma rede IP do remetente, e enviado ao roteador, utilizando o endereco MAC

# Rede Externa VS Rede Interna

![[Pasted image 20261116104525.png]]

- **192.168.0.1** - Gateway, IP da rede interna do roteador
- **216.58.192.5** - O IP da rede externa do roteador

## Como funciona

O papel do IP interno e se comunicar internamente entre os aparelhos do local

O papel do IP externo e se comunicar com a internet, se comunicar com outros equipamentos

## Exemplo da imagem

- A comunicao interna da rede e feita com o IP 192.168.0.1
- O smartphone quer fazer uma requisicao:
	- Ele envia informacao do 192.168.0.109 para o gateway 192.168.0.1 e assim ele envia para a rede externa 216.58.192.5 e assim faz a comunicao com a internet



# DHCP

**Dynamic Host Configuration Protocol**

