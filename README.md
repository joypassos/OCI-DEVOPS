# OCI-DEVOPS

 https://medium.com/p/9fdbb18a232d/edit
 
## Terraform em OCI

Implementação da Terraform no OCI
Provisionar recursos dentro da OCI usando infraestrutura como código.
Os recursos provisionados são os seguintes:
OKE | DEVOPS | APM |API GATEWAY

Juntamente com os recursos REDE e GESTÃO, tais como:
VCN| SUB-REDES |GRUPOS DINÂMICOS |COMPARTIMENTOS

Baixar repositório
Como primeiro passo, devemos transferir este repositório do GitHub e para isso existem 2 opções:
1. git clone https://github.com/joypassos/OCI-DEVOPS
OU
2. Transferência directa de . zip no GitHub

Os códigos terraform já estão em uma pasta, então precisamos codificar um arquivo. Tf para provisionar um Oracle API Gateway junto com os outros recursos já criados nesta pasta.

## Gerar um novo arquivo. Tf
Adicione um novo arquivo de texto chamado 'apigateway.Tf' para criar um novo arquivo terraform. ou qualquer outro nome, mas com a extensão ". Tf" dentro da pasta que são os outros arquivos terraform.

Exemplo:

Esse código é usado para indicar que queremos configurar um Oracle API Gateway.

¨¨bash
recurso "oci_apigateway_gateway" "devops_gateway" {compartment_id = var.compartment_id
 endpoint_type = var.api_gateway_type
 subnet_id = oci_core_subnet.oke_lb_subnet[0]. id
 display_name = var.api_gateway_name
}
¨¨

Neste código, estamos afirmando que queremos criar um novo tipo de recurso 'oci_apigateway_gateway' e estamos definindo as informações necessárias para configurá-lo.

Fonte deste código: Documentação do Terraform sobre API GATEWAY.

Criado e preenchido neste arquivo . Tf, agora carrgue toda essa infraestrutura como código no OCI.

## Carregar terraform no Oracle Resource Manager

* Acesse o menu sanduíche à esquerda

* Clique neles"Serviços para desenvolvedores"

* Nas opcões que aparecer selecione "Resource Manager".

* Selecione e crie um novo STACK

* Selecione como fonte a pasta do seu computador contendo os arquivos . Tf baixado, fazendo com que o Gerenciador de Recursos já preencha todos os campos.
