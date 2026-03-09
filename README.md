# Explicação e especificações do trabalho

- Placa de tamanho retangular de 40mm de altura e 80mm de largura
- O conector macho deve ser o secundário do transformador/ saída do transformador
- Fazer o circuito em modo Esquemático, PCB e 3D
- Tirar capturas de telas do circuito nos 3 modos
- Colocar os mesmos valores do simulador (capacitores e resistores)
- As trilhas/ligações do circuito interno devem ser desenhadas na parte inferior da placa (bottom/linhas devem ser azuis)
- Criar o projeto no GitHub e documentar o que cada parte/elemento do circuito é, faz e sua importância (e sinal da onda) para o funcionamento correto do circuito


## Componentes utilizados

Abaixo estão os principais componentes que compõem este circuito de retificação e regulação:

1. 7812
2. BRIDGE
3. CAP
4. CAP-ELEC
5. CONN-SIL2
6. LED
7. MINRES120K
8. SIL-100-02


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

### 4. CAP (Capacitor Cerâmico/Desacoplamento)

- **O que é:** Um capacitor de baixa capacitância, geralmente não polarizado.
    
- **O que faz:** Filtra ruídos de alta frequência e transientes rápidos vindos da rede ou gerados pelo próprio regulador.
    
- **Importância:** Garante a estabilidade do regulador 7812, evitando que ele entre em oscilação ou sofra com interferências eletromagnéticas.
    
- **Sinal da Onda:** Limpa os "espinhos" ou ruídos quase invisíveis que ficam sobrepostos à linha de tensão contínua.
<br>

### 5. CONN-SIL2 / SIL-100-02 (Conectores)

- **O que é:** Terminais de conexão física (bornes ou pinos).
    
- **O que faz:** Provê o ponto de entrada para a fonte AC e o ponto de saída para a carga 12V DC.
    
- **Importância:** Permite a manutenção e a conexão segura de fios externos sem a necessidade de soldar e dessoldar diretamente na placa a todo momento.
    
- **Sinal da Onda:** Na entrada (SIL de entrada), o sinal é AC Senoidal. Na saída (SIL de saída), o sinal é 12V DC Puro.
<br>

### 6. LED (Diodo Emissor de Luz)

- **O que é:** Um semicondutor que emite luz quando percorrido por uma corrente.
    
- **O que faz:** Converte energia elétrica em sinalização visual.
    
- **Importância:** Indica o estado do sistema (Ligado/Desligado). É crucial para que o usuário saiba que a placa está energizada antes de tocá-la ou conectar um dispositivo.
    
- **Sinal da Onda:** Opera em 12V DC (após o resistor), emitindo luz constante.
<br>

### 7. MINRES120K (Resistor)

- **O que é:** Um componente passivo que oferece resistência à passagem da corrente.
    
- **O que faz:** Limita a intensidade da corrente elétrica que chega ao LED.
    
- **Importância:** Sem ele, o LED receberia toda a corrente da fonte e queimaria instantaneamente. Ele calcula e "freia" a energia para o nível seguro do LED.
    
- **Sinal da Onda:** Mantém a tensão contínua, mas reduz a amplitude da corrente circulante.


## Imagens do trabalho

Como especificado pelo professor, é preciso ter imagem do circuito nas 3 formas possíveis: Esquemático, PCB e 3D

### Schematic Capture (Esquema Elétrico):

É o desenho lógico do circuito. Aqui é definido quais componentes serão usados e como eles se conectam eletricamente (quem liga em quem). Serve para simular o comportamento do circuito (testar se a fonte realmente entrega 12V) e validar a lógica antes de montar a placa física.

![Esquema Elétrico](assets/Schematic%20Capture%20-%20Retificador%20Trabalho%2001.png)
<br>

### PCB Layout (ARES):

É o desenho físico da placa de circuito impresso. Aqui é posicionado os componentes onde eles realmente vão ficar soldados e onde as trilhas de cobre são desenhadas (as linhas azuis e vermelhas). É o arquivo usado para a fabricação da placa. É onde é definido a espessura das trilhas e o tamanho real do objeto.

![Layout da placa](assets/PCB%20Layout%20-%20Retificador%20Trabalho%2001.png)
<br>