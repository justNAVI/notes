
![[modelo osi.png]]

####  Demonstração Academia (Como funciona uma comunicação de Rede e como ela atua)
 -  Dividido em 7 camadas, cada uma com uma função e protocolos. 
 - A informação desce da 7 á 1 e quando chega ao seu destino ela sobe da 1 á 7 camada para que tudo seja visível para o usuário final.

| Camadas                | Descrição                                                                                                         | Exemplos                                          | Protocolos                                       |
| ---------------------- | ----------------------------------------------------------------------------------------------------------------- | ------------------------------------------------- | ------------------------------------------------ |
| Camada 7: Aplicação    | Camada que o usuário consegue visualizar no computador dele                                                       | Transferencia de arquivos, teminal virtual, email | HTTP, RTP, SMTP, FTP, SSH, DNS...                |
| Camada 6: Apresentação | Principal objetivo é a formatação de dados e conversão de caracteres e códigos (Função adicional de criptografia) |                                                   | XDR, TLS..                                       |
| Camada 5: Sessão       | Negociação estabelecimento de conexão com outro nó (Iniciar, manter e finalizar conexão)                          | Logar com uma conta em um servidor                | NetBIOS                                          |
| Camada 4: Transporte   | Meios e métodos para a entrega de dados ponta-a-ponta (Transmissão confiável de dados)                            |                                                   | NetBEUI, TCP, UDP, SCTP, DCCP, RIP...            |
| Camada 3: Rede         | Roteamento de pacotes através de uma ou várias redes (Endereçamento lógico, controle de tráfego)                  |                                                   | IP, Ipsec, ICMP, ARP, NAT...                     |
| Camada 2: Enlace       | Detecção e correção de erros introduzidos pelo meio de transmissão (Endereçamento fisico)                         |                                                   | Ethernet, IEEE 802. 1Q, HDLC, FDDI, PPP...       |
| Camada 1: Fisica       | Camada que comunica-se entre um dispositivo ao outro(Interface de comunicação e sinalização)                      | Cabo de roteador, Modem, WIFI, USB...             | Modem, 802. 11 WIFI, RDIS, RS-232, Bluethooth... |


![[tabela_camada.png|697]]


## Modelo TCP/IP (Utilizado comercialmente)

- Diferença entre Modelo TCP/IP e Modelo OSI = Modelo TCP/IP segmenta todas as etapas dentro de uma comunicação de uma forma simplificada
		- Toda a parte de Aplicação já possui Apresentação e Sessão
		- Toda a parte Acesso a Rede já possui Enlace e Fisica


![[TCP-IPvsOSI.png|697]]


## OSI HACK

| Tipo de Ataques    | Descrição                                                                | Camada           | Exemplo                                                  |
| ------------------ | ------------------------------------------------------------------------ | ---------------- | -------------------------------------------------------- |
| EXPLOIT            |                                                                          | Aplicação (7)    | Ataque de payload                                        |
| PHISHING           |                                                                          | Apresentação (6) |                                                          |
| HIJACKING          | "Sequestro" de sessão; Objetivo é roubar uma sessão de um usuário logado | Sessão (5)       |                                                          |
| RECONNAISSANCE/D0S | Inviabilizar uma conexão por envio massivo de pacotes                    | Transporte (4)   |                                                          |
| MAIN-IN-THE-MIDDLE | Não necessariamente um SNIFFING, interceptação em nível de rede          | Rede (3)         |                                                          |
| SPOOFING           |                                                                          | Enlace (2)       |                                                          |
| SNIFFING           | Interceptar dados                                                        | Fisica (1)       | Colocar um equipamento no meio entre o cabo e o roteador |

![[OSI_HACK.png]]
