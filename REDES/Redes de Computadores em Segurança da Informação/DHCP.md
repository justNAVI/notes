- Cliente conecta na rede (Envia um pedido de configuração de endereço IP)

**Servidor DHCP**C -> gerencia faixa fixa:
-  Gateway padrão, nomes de domínio e DNS

**Range DHCP** (IP FIXO NÃO PRECISA ENTRAR) -> 
-  0 até X
> Se x+1 tentar se conectar ele não consegue.

- Bloqueio de MAC -> IP nem entra
- Existe limite de IP (roteador)
- Controle de banda (feito pelo MAC)

### Ataque com DHCP 
 - Várias conexões falsas; Você reconhece e pega todos os IP's válidos e não sobra nenhum = ninguém pode se conectar após isso.