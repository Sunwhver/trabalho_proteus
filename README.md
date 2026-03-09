# Componentes utilizados

Abaixo estão os principais componentes que compõem este circuito de retificação e regulação:

1. 7812
2. BRIDGE
3. CAP
4. CAP-ELEC
5. CONN-SIL2
6. LED
7. MINRES120K
8. SIL-100-02

___

### 1. IC 7812 (Regulador de Tensão)

- **O que é:** Um circuito integrado (CI) regulador de tensão positiva de três terminais da série 78xx.
    
- **O que faz:** Ele recebe a tensão contínua que vem dos capacitores (que ainda pode oscilar um pouco) e a estabiliza, "podando" qualquer excesso para manter uma saída fixa e constante de **12V**.
    
- **Importância:** É o componente de precisão e segurança do projeto. Ele garante que, mesmo que a energia da rede elétrica mude levemente, os dispositivos conectados à saída da sua placa recebam sempre a voltagem correta, protegendo-os contra queimas ou mau funcionamento.
    
- **Sinal da Onda:** Recebe uma linha com **Ripple** (uma pequena ondulação de serra) e a transforma em uma **Linha Reta Perfeita (DC Pura)** estabilizada em 12V.
<br>

### 2. BRIDGE (Ponte Retificadora)

- **O que é:** Um conjunto de quatro diodos montados em uma única cápsula.
    
- **O que faz:** Realiza a retificação de onda completa, invertendo os ciclos negativos da corrente alternada para o lado positivo.
    
- **Importância:** É o componente que permite que a energia da tomada (AC) comece a se comportar como uma bateria (DC). Sem ela, os componentes seguintes seriam danificados pela inversão de polaridade.
    
- **Sinal da Onda:** Transforma uma **Senoide** (onda que sobe e desce) em uma **Onda Pulsante Positiva** (uma sequência de "lombadas").
<br>

### 3. CAP-ELEC (Capacitor Eletrolítico)

- **O que é:** Um componente de armazenamento de carga de alta capacidade e polarizado.
    
- **O que faz:** Atua como um filtro de baixa frequência, preenchendo os vazios entre os pulsos da ponte retificadora.
    
- **Importância:** Reduz drasticamente a variação da tensão, impedindo que o circuito "desligue" entre um pulso e outro da rede elétrica.
    
- **Sinal da Onda:** Transforma a onda pulsante em uma linha com **Ripple** (uma pequena ondulação em forma de serra no topo do sinal).
<br>