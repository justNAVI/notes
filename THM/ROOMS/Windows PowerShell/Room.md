
### PowerShell Basics

- Comandos no PowerShell são conhecidos como cmdlets e seguem uma convenção de Verb-Noun. 
- O "Verb" descreve a ação e o "Noun" especifica o objeto no qual ação irá agir

#### Basic Cmdlets

| Basic Cmdlets       | Descrição                                                                |
| ------------------- | ------------------------------------------------------------------------ |
| Get-Command         | Lista os comandos que podem ser utilizados                               |
| Get-Help            | Detalha informações sobre cmdlets (Incluindo uso, parametros e exemplos) |
| Get-Alias           | Lista todos os shortcuts dos comandos                                    |
| Get-ChildItem -Path | Lista arquivos e diretórios na localização -path (parâmetro)             |
| Set-Location        | Muda o diretório para o -path especificado                               |
| New-Item -Path      | Cria novo item. Tem que especificar o path e o type(arquivo/diretório)   |
| Remove-Item -Path   | Exclui diretórios e arquivos                                             |
| Copy-Item -Path     | Copia arquivos e diretórios                                              |
| Move-Item -Path     | Move arquivos e diretórios                                               |
| Get-Content -Path   | Similar a "cat"                                                          |
| Find-Module         | Procura modulos online em repositórios                                   |

- Há filtros que podem ser utilizados para diminuir essas listas usando propriedades especificas.

``` shell
Get-Command -CommandType "Function"
Get-Help New-LocalUser
Set-Location -Path ".\Documents"
New-Item -Path ".\navi-room\navi-bed" -Itemtype "Directory"
Remove-Item -Path ".\navi-room\navi-bed\navi-diary.txt"
Get-Content -Path ".\navi-panties"
```
#### Piping, Filtering and Sorting Data

- Piping ( | ) é a técnica que permite concatenar o comando e receber mais informações sobre ele ou o arquivo.
Usado para concatenar os cmdlets com algo que você precise procurar/observar (Traz não somente a informação mas propriedades, métodos descritivos e interage)

| Operators | Descrição                |
| --------- | ------------------------ |
| -ne       | Not equal                |
| -gt       | Greater than             |
| -ge       | Greater than or equal to |
| -lt       | Less than                |
| -le       | Less than or equal to    |

``` shell
Get-ChildItem | Sort-Object Length
Get-ChildItem | Where-Object -Property "Extension" -eq ".txt"
Get-ChildItem | Where-Object -Property "Name" -link "manga*"
Get-ChildItem | Select-Object Name,Length
Select-String -Path ".\navi-dreams.txt" -Pattern "dreams"
```

#### System and Network Information

| Cmdlet                 | Descrição                                                               |
| ---------------------- | ----------------------------------------------------------------------- |
| Get-ComputerInfo       | Lista toda a informação do sistema (Hardware, BIOS, etc)                |
| Get-LocalUser          | Lista todas as contas do sistema                                        |
| Get-NetIpConfiguration | Mostra informações detalhes da rede (IP, DNS, Gateway)                  |
| Get-NetIPAddress       | Mostra detalhes de todos os IP's configurados no sistema (Até inativos) |

#### Real-Time System Analysis

| Cmdlet               | Descrição                                                                                                                      |
| -------------------- | ------------------------------------------------------------------------------------------------------------------------------ |
| Get-Process          | Mostra detalhadamente cada processo em andamento, inclui CPU e uso de memória (Bom pra monitoração e troubleshooting)          |
| Get-Service          | Mostra informações sobre os status dos serviços da maquina (Running, Stopped or Paused)                                        |
| Get-NetTCPConnection | Mostra as conexões TCP [Endpoints Locais e Remotos] (Bom para Resposta a Incidentes, Analise de Malware, Backdoors escondidas) |
| Get-FileHash         | Gera Arquivos Hash (Particularmente bom em Resposta a Incidentes, Analise de Malware, Verificar integridade do arquivo)        |

#### Scripting







