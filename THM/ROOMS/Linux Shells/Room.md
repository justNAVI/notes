
## Interagindo com a Shell

| Comando  | Descrição                                      |
| -------- | ---------------------------------------------- |
| pwd      | Checa o diretório atual                        |
| cd       | Muda o diretório                               |
| ls       | Lista o conteúdo do diretório                  |
| cat      | Lê o conteúdo do arquivo                       |
| grep     | Busca por algo especifico                      |
| chmod +x | Da permissão para executar o script            |
| ./       | Executa o script que a permissão foi concedida |

### Shell Scripiting


> [!important] Bash
> - Todo script tem que ter o formato .sh
> - No inicio de todo script precisa ter a shebang "#!/bin/bash"
> 

#### Loops

```` shell
#!/bin/bash
for i in {1..10};
do
echo $i
done
```` 

#### Condicionais (Com comentários)

```` shell
# Pede o usuário um input
echo "Qual é seu nome?"

#Guarda o valor na variavel
read name

# Checa se o input é igual ao pré-requisito para saber o segredo
if [ "$name" = "Navi" ]; then

# Se o input condizer com o pré-requisito, mostra a seguinte linha.
	echo "Navi, você já sabe o segredo! "TRY HARDER" "

# Caso for diferente, mostra a seguinte linha.
else 
	echo "Você ainda tem que descobrir o segrego!"
fi
````
