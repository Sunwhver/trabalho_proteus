# Componentes utilizados

Abaixo estão os principais componentes que compõem este circuito de retificação e regulação:

7812
BRIDGE
CAP
CAP-ELEC
CONN-SIL2
LED
MINRES120K
SIL-100-02

### 1. IC 7812 (Regulador de Tensão)

- **O que é:** Um circuito integrado (CI) regulador de tensão positiva de três terminais da série 78xx.
    
- **O que faz:** Ele recebe a tensão contínua que vem dos capacitores (que ainda pode oscilar um pouco) e a estabiliza, "podando" qualquer excesso para manter uma saída fixa e constante de **12V**.
    
- **Importância:** É o componente de precisão e segurança do projeto. Ele garante que, mesmo que a energia da rede elétrica mude levemente, os dispositivos conectados à saída da sua placa recebam sempre a voltagem correta, protegendo-os contra queimas ou mau funcionamento.
    
- **Sinal da Onda:** Recebe uma linha com **Ripple** (uma pequena ondulação de serra) e a transforma em uma **Linha Reta Perfeita (DC Pura)** estabilizada em 12V.
    