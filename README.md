# Projeto de Topologia de Rede com Mininet

- Este projeto utiliza o Mininet para criar uma topologia de rede do tipo árvore (tree) com profundidade de 4 (depth=4) e ramificação de 2 (fanout=2). As configurações incluem largura de banda de 25 Mbps entre os links e o uso do controlador padrão do Mininet. Testes de ping e iperf foram executados para validar a conectividade e o desempenho da rede.

## 1. Criando a Topologia
```sh
    sudo mn --topo tree,depth=4,fanout=2 --mac --link=tc,bw=25
```

## 2. Inspeção das Informações de Rede

- Listar todos os nós (hosts e switches):
```sh
    nodes
```

- Verficar os enlaces
```sh
    net
```

- Verificar endereços
```sh
    dump
```

- Mostrar dados do dispositivo h1
```sh
    h1 ifconfig
```

- Mostrar dados do dispositivo h2
```sh
    h2 ifconfig
```

- Ping entre todos os hosts
```sh
    pingall
```

- Ping específico entre os hosts h1 e h2
```sh
    h1 ping -c 20 h2
```

## 3. Teste de Largura de Banda com Iperf

- Comando iperf
```sh
      xterm h1 h2
```

- h1 servidor, TCP na porta 5555
```sh
      iperf -s -p 5555
```

- h2 cliente, TCP na porta 5555
```sh
      iperf -c 10.0.0.1 -p 5555 -i 1 -t 10 -b 25M
```





