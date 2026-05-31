# 🚦 Projeto Arduino - Semáforo Inteligente com Botão de Pedestre
## 📌 Descrição

Este projeto consiste em um Semáforo Inteligente utilizando Arduino Uno, desenvolvido em linguagem C/C++ para simulação no Tinkercad ou implementação física.

O sistema realiza o controle automático de um semáforo veicular com três estados:

* 🟢 Verde
* 🟡 Amarelo
* 🔴 Vermelho

Além disso, possui um botão de solicitação de travessia para pedestres, permitindo que o fluxo de veículos seja interrompido de forma segura para a passagem dos pedestres.

O acionamento do botão é tratado através de interrupção externa, garantindo resposta imediata ao usuário sem necessidade de monitoramento contínuo dentro do loop principal.

## 🎯 Objetivos
* Demonstrar o uso de entradas e saídas digitais do Arduino.
* Aplicar conceitos de semáforos automatizados.
* Utilizar interrupções externas.
* Trabalhar com LEDs, resistores e botões.
* Simular um sistema básico de controle de tráfego urbano.

## 🛠 Componentes Utilizados
Componente----------	Quantidade

Arduino Uno R3------	    1

LED Vermelho--------	    1

LED Amarelo---------	    1

LED Verde-----------	    1

LED Azul (Pedestre)-	    1

Resistor 220 Ω------	    4

Botão Push Button---	    2

Resistor 10 kΩ------    	1

Protoboard----------	    1


## 🔌 Ligações
- LEDs
  
- LED	Pino Arduino
  
- Azul (Pedestre)	D4
  
- Verde	D5
  
- Amarelo	D6
  
- Vermelho	D7

Todos os LEDs utilizam resistores de 220 Ω em série.

Botão de Pedestre
Componente	Pino
Botão	D2


O botão utiliza a configuração:
"INPUT_PULLUP"

e é acionado por interrupção:
"attachInterrupt(
    digitalPinToInterrupt(Bot1),
    acionaLed1,
    FALLING
);"

## ⚙️ Funcionamento
Operação Normal

O semáforo executa continuamente a seguinte sequência:

* 🟢 Verde por 3 segundos
* 🟡 Amarelo por 3 segundos
* 🔴 Vermelho por 3 segundos

Após isso o ciclo reinicia.

Travessia de Pedestres

Quando o botão é pressionado:

1 - O LED azul do pedestre é ativado.
2 - O LED verde é desligado.
3 - O LED amarelo permanece ligado por 3 segundos (transição).
4 - O LED vermelho é ligado por 6 segundos.
5 - O sistema retorna ao funcionamento normal.

## 🧠 Conceitos Aplicados
### Interrupções

A interrupção permite que o Arduino detecte o pressionamento do botão imediatamente.
"volatile bool pedestreAtivo = false;"
A variável é declarada como volatile para garantir que seu valor seja atualizado corretamente entre a interrupção e o programa principal.

### Função de Interrupção
"void acionaLed1() {
  pedestreAtivo = true;
}"
Sempre que o botão é pressionado, a variável é alterada para informar ao programa principal que existe uma solicitação de travessia.

### 📄 Código Fonte

O código completo encontra-se no arquivo:
"semaforo_pedestre.ino"
semaforo_pedestre.ino


# ▶️ Como Executar
1 - Tinkercad
2 - Abra o projeto no Tinkercad.
3 - Clique em Start Simulation.
4 - Observe o ciclo do semáforo.
5 - Pressione o botão de pedestre para solicitar a travessia.

# Arduino IDE
1 - Abra o arquivo .ino.
2 - Conecte o Arduino Uno.
3 - Selecione a placa correta.
4 - Faça o upload do código.
5 - Teste o funcionamento.

# 📊 Fluxograma Simplificado
<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/1569da01-de8d-4d92-a4ac-f2cf8071f3cb" />

# 📚 Tecnologias Utilizadas
* Arduino Uno R3
* Linguagem C/C++
* Arduino IDE
* Tinkercad



<img width="1024" height="1536" alt="image" src="https://github.com/user-attachments/assets/bb869edf-7e7e-4b50-bf65-30bdd68788f9" />
