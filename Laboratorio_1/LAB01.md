# Laboratório 01 - Configuração inicial no PNetLab


## Objetivos do laboratório

- Compreender que redes distintas **não se comunicam automaticamente**
    
- Identificar o **papel do roteador** como elemento lógico de interconexão
    
- Diferenciar falha de comunicação por ausência de roteamento de falha física
    
- Relacionar teoria de roteamento com comportamento real da rede

## Cenário do Laboratório

### Topologia lógica

![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1485623169699287092/image.png?ex=69c3db65&is=69c289e5&hm=5c12e91936302390cd73e90b9ac23fd147c798bb544ec52a010d24e572cb41fd&=&format=webp&quality=lossless)

## Dispositivos utilizados

1. Roteador cisco (IOL)
2. Switch cisco (apenas l2)
3. 2 Virtual PCs

## Configuração de endereçamento IP

### Endereçamento utilizado

- VPC4:

![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1485623656049803315/image.png?ex=69c3dbd9&is=69c28a59&hm=6757fb228af1ad8196b274006b72998c3d2c9034af52c4a746504cbcbdbcf1e7&=&format=webp&quality=lossless)

- VPC 0

![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1485623656385085530/image.png?ex=69c3dbd9&is=69c28a59&hm=2e5eb2e3f44ccebdce2092d8c60f6e66fa415532bf5dc6e3754f1866d13efc1f&=&format=webp&quality=lossless) 

- Roteador

![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1486086999298543697/image.png?ex=69c439de&is=69c2e85e&hm=9e5cf0ba5f6fc8cd1c5d48e21e35aeee97c7a8cfd5d3a83e79646ba2b92d25b3&=&format=webp&quality=lossless)

> Note que cada VPC está com o endereço de gateway definido pois sem ele não haveria comunicação entre diferentes sub-redes.

## Teste de conectividade entre os dispositivos

### Entre VPC 0 e VPC 4
![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1485623656724959283/image.png?ex=69c3dbd9&is=69c28a59&hm=63a8dc525e07964fa682198132f25e82f659c6e80d9d846ada1c35ddd3bb5214&=&format=webp&quality=lossless)

> Já não ser que o roteador tem regras de restringir a comunicação de um lado somente entre as sub-redes, conseguimos normalmente nos comunicar do VPC 4 para o VPC 0.

![Imagem](https://media.discordapp.net/attachments/1483784774656200704/1485623657098117270/image.png?ex=69c3dbd9&is=69c28a59&hm=63753b5c1d6a560b8aee8be9c9d4ae3ed8c0426e890f211e59de61d15a90b014&=&format=webp&quality=lossless)


##  Perguntas

### Discussão final orientada

- O roteador conhece o caminho completo?
    
    R: Sim, dada a topologia utilizada, o roteador consegue fazer o encaminhamento normalmente dos pacotes pois ele administra as duas sub-redes do projeto. Em outros casos, ele teria que se comunicar com outros roteadores através
    de protocolos de roteamento para a descoberta de outras sub-redes e melhor caminho para os pacotes.

    
- Onde ocorreu a “inteligência” da rede?
    
    R: No roteador R1. Pois ele quem conseguiu administrar as duas sub-redes trabalhando como gateway para fornecer comunicação entre as duas sub-redes. O switch (gatinho) apenas faz o encaminhamento de frames e não entende sobre camada 3 para poder pensar no melhor caminho para um determinado pacote e nem sequer pensar em conceitos de sub-redes.
    
- O que aconteceria com mais roteadores?

    R: Depende da topologia, mas se diferentes sub-redes forem administradas por um roteador diferente, deve-se adotar a utilização de protocolos de roteamento (plano de controle) para que as sub-redes tenham uma comunicação.

### Plano de dados x plano de controle

Neste laboratório, apenas trabalhamos com o plano de dados. Ou seja, o roteador apenas consultou sua tabela de encaminhamento para conseguir fazer a comunicação das sub-redes. 
#### Por quê?

O roteador é gateway das duas sub-redes utilizadas no laboratório, logo não há necessidade de atribuir rotas estáticas ou protocolos de roteamento.

O plano de controle é onde o roteamento age. Ele calcula qual o melhor caminho que o pacote deve ter para chegar de um ponto A a um ponto B. É necessário quando o pacote precisa passar por diversos nós.

#### Como funciona a tabela de encaminhamento?

A tabela de encaminhamento relaciona o endereço de uma rede com qual interface ele deve ser encaminhado. Isso ocorre em nível de hardware e por isso não é necessário muito processamento. É resumido em entrada-saída.




