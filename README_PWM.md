# Controle de Motor DC via PWM com Arduino Nano

Este projeto faz parte da disciplina de Simulação em Sistemas Embarcados e demonstra o controle de velocidade de um motor DC variando o *Duty Cycle* do sinal PWM.

## Índice
1. [Introdução ao PWM](#1-introdução-ao-pwm)
2. [Componentes necessários](#2-componentes-necessários)
3. [Esquemático](#3-esquemático)
4. [Código-fonte](#4-código-fonte)
5. [Instruções de montagem](#5-instruções-de-montagem)
6. [Funcionamento do projeto](#6-funcionamento-do-projeto)
7. [Esquemático do PWM](#7-esquemático-do-pwm)
8. [Vídeo do circuito funcionando](#8-vídeo-do-circuito-funcionando)

---

## 1. Introdução ao PWM
O PWM (*Pulse Width Modulation* - Modulação por Largura de Pulso) é uma técnica utilizada para controlar a potência média fornecida a uma carga. Alternando rapidamente o sinal entre o nível alto (5V) e baixo (0V), podemos controlar a velocidade de rotação do motor DC. Quanto maior o tempo em nível alto (*Duty Cycle*), mais rápido o motor gira.

## 2. Componentes necessários
* Arduino Nano (ATmega328P)
* Driver de Motor Ponte H - L293D
* Motor DC
* Push Button e Resistor de 10kΩ
* Bateria de 5V
* Osciloscópio (Ferramenta virtual do Proteus)

## 3. Esquemático
Os arquivos do esquemático foram desenvolvidos no Proteus e estão organizados na pasta `schematics`:
* Arquivo de simulação: `trabalho01.pdsprj`

## 4. Código-fonte
O firmware foi desenvolvido em C++ utilizando o ambiente PlatformIO. O arquivo principal está localizado em:
* [`/src/main.cpp`](./src/main.cpp)

## 5. Instruções de montagem
1. Clone este repositório para sua máquina local.
2. Abra o projeto utilizando o VS Code com a extensão PlatformIO instalada.
3. Compile o código clicando no botão **Build** (✓) para gerar o arquivo `.hex` na pasta oculta `.pio`.
4. Abra o arquivo `trabalho01.pdsprj` no Proteus.
5. Nas propriedades do Arduino Nano, aponte o `Program File` para o arquivo `.hex` recém-gerado.
6. Inicie a simulação.

## 6. Funcionamento do projeto
O sistema inicia com o motor totalmente parado (0% de PWM). Ao pressionar o botão (conectado ao pino D2), o Arduino lê a transição de estado e incrementa a velocidade do motor em degraus de aproximadamente 25% (64 pontos na escala de 0 a 255 do `analogWrite`), enviando o sinal pelo pino D9. 

No osciloscópio, é possível visualizar o *Duty Cycle* aumentando a cada clique. Ao ultrapassar o limite máximo (100%), a velocidade é zerada e o ciclo recomeça.

## 7. Esquemático do PWM
Abaixo, a representação visual do circuito montado no ambiente Proteus:

![Esquemático do Circuito no Proteus](./assets/Schematic%20PWM.png)

## 8. Vídeo do circuito funcionando
Demonstração da variação da onda no osciloscópio e rotação do motor:

<video src="./assets/Gravação do trabalho de PWM - Proteus.mp4"></video>
```
