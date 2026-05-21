# Laboratório 07 - Configuração dos Provedores (BGP Externo)

## Objetivo

Configurar os roteadores ISP1, ISP2 e ISP3 para permitir o funcionamento completo do cenário de BGP externo.

### Este laboratório é uma continuação do [Laboratório 6](../Laboratorio_6/lab6.md), Todo o diagrama lógico está descrito lá. 


## Topologia

![img1](../Laboratorio_6/imagens/topologia.png)

## Configuração

Toda a configuração segue quase que completamente o roteiro, mas vou mostrar o *show run* de cada roteador abaixo.

- R1

![img2](imagens/showrunr1.png)

![img3](imagens/showrun2r1.png)

- R4 (ISP 2)

![img4](imagens/showrunr4.png)

- R3 (ISP 1)

![img5](imagens/showrunr3.png)

- R5 (ISP 3)

![img6](imagens/showrunr5.png)

> A configuração das interfaces de R5 segue a mesma do roteiro. Não coloquei pois é grande demais


## Verificação final

Para verificarmos a vizinhança BGP e todas as rotas, usaremos os seguintes comandos:

```
Router# show ip bgp summary

Router# show ip bgp

Router# show ip route

Router# show run
```


- R1 
   - ip bgp
     ![img7](imagens/ipbgpr1.png)
   - ip bgp summary
     ![img8](imagens/ipbgpsumr1.png)
   - ip route
     ![img9](imagens/iprouter1.png)

- R4
   - ip bgp
     ![img10](imagens/ipbgpr4.png)
   - ip bgp summary
     ![img11](imagens/ipbgpsumr4.png)
   - ip route
     ![img12](imagens/iprouter4.png)

- R3
   - ip bgp
     ![img14](imagens/ipbgpr3.png)
   - ip bgp summary
     ![img15](imagens/ipbgpsumr3.png)
   - ip route
     ![img16](imagens/iprouter3.png)

- R5
   - ip bgp
     ![img17](imagens/ipbgpr5.png)
   - ip bgp summary
     ![img18](imagens/ipbgpsumr5.png)
   - ip route
     ![img19](imagens/iprouter5.png)

# FIM




