# aula_assistente_delivery

1.Descrevendo meu entendimento nas aulas, pois no momento não me senti seguro em adicionar uma forma de pagamento
Descrevendo.

Crie um método POST chamado pedido que recebe o pedido do cliente.
O corpo do pedido pode ser algo assim:

Copiar código

{
  "cliente_nome": "João",
  "itens": [
    "Entrada: torradas",
    "Prato Principal: Filé com batatas",
    "Sobremesa: Mousse de Chocolate"
  ]
}

2. Função Lambda - Validar Pedido
Crie uma função Lambda que verifica se o pedido está completo. Ela vai validar se o pedido contém itens e se todos os itens são válidos.

def lambda_handler(event, context):
    pedido = json.loads(event['body'])
    
    if 'itens' not in pedido or len(pedido['itens']) == 0:
        return {
            'statusCode': 400,
            'body': json.dumps({'message': 'Pedido inválido, itens não encontrados.'})
        }
    
    return {
        'statusCode': 200,
        'body': json.dumps({'message': 'Pedido validado com sucesso'})
    }

    
3. Função Lambda - Processar Pagamento
Esta função Lambda simula o processamento do pagamento.


def lambda_handler(event, context):
    pedido = json.loads(event['body'])
    
    pagamento_aprovado = True  # Simulando o pagamento aprovado

    if not pagamento_aprovado:
        return {
            'statusCode': 400,
            'body': json.dumps({'message': 'Pagamento falhou'})
        }

    return {
        'statusCode': 200,
        'body': json.dumps({'message': 'Pagamento aprovado'})
    }

 
Conclusão
com esses passos, criei um fluxo de um jantar romântico utilizando meu entendimento na aula de AWS Step Functions e Amazon Bedrock. 
