# Controle de LED com ESP32 e dois botões

Exemplo básico de leitura de botões e controle de uma saída digital. O primeiro botão liga o LED e o segundo desliga.

## Pinos usados

| Função | GPIO |
|---|---:|
| LED | 2 |
| Botão para ligar | 5 |
| Botão para desligar | 4 |

Use um resistor adequado em série com o LED. Os pinos dos botões estão configurados como `INPUT`; o circuito precisa fornecer um nível lógico definido quando cada botão está solto e pressionado. Confira o esquema antes de montar.

## Como funciona

O programa lê os dois botões continuamente com `digitalRead()`. Quando o botão no GPIO 5 é detectado em nível alto, o LED do GPIO 2 acende. Quando o botão no GPIO 4 é detectado em nível alto, o LED apaga.

Se os dois botões estiverem em nível alto na mesma iteração, o programa executa primeiro o comando de ligar e depois o de desligar. O LED termina a iteração apagado.

O código inclui um atraso de 200 ms depois do comando de desligar. A leitura não implementa tratamento completo de ruído ou debounce.

## Circuito

<img width="590" height="578" alt="Esquema do circuito de controle de LED" src="https://github.com/user-attachments/assets/9b1968c9-d41b-4866-aee0-2ac8dc6c43f0" />

## Executar

1. Abra `sketch_mar24a.ino` na Arduino IDE.
2. Selecione uma placa ESP32 compatível e a porta correta.
3. Confira o circuito e envie o programa.
