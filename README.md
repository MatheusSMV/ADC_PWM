# Projeto: Controle de Display OLED e LEDs com Raspberry Pi Pico - BitDogLab

## Descrição
Este projeto implementa o controle de um display OLED SSD1306, LEDs RGB e um joystick analógico utilizando um Raspberry Pi Pico. O código faz uso de comunicação I2C para interação com o display, PWM para controle da intensidade dos LEDs e ADC para leitura dos valores do joystick.

## Funcionalidades
- Exibição de informações no display OLED SSD1306 via I2C.
- Controle de LEDs RGB usando sinais PWM.
- Leitura do joystick analógico para movimentação no display.
- Implementação de debounce para botões de controle.
- Botão A desativa os Leds controlados via PWM. (Azul e Vermelho).
- Botão do Joystick desativa e ativa o led verde.

## Componentes Utilizados
- Raspberry Pi Pico
- Display OLED SSD1306
- LEDs RGB
- Joystick analógico
- Botões de entrada
Em suma a placa BitDogLab, fornecida pelo EmbarcaTech.

## Bibliotecas Utilizadas
- `hardware/i2c.h` - Para comunicação I2C
- `ssd1306.h` - Controle do display OLED
- `hardware/pwm.h` - Controle de PWM para LEDs
- `hardware/adc.h` - Leitura de ADC para o joystick

## Como Utilizar
1. Carregue o código na BitDogLab.
2. Use os botões para alternar entre diferentes modos de exibição e controle dos LEDs.
3. Importante ressaltar, a configuração dos potênciometros pode variar de placa para placa, ou seja, a simulação central conforme está expressa no vídeo explicativo pode ser diferente em função da calibração na placa BitDogLab, ou seja, é uma coisa bem específica, que nesse caso, deve ser ajustado pelo operador, pois, a relação não é a mesma entre as placas.


## Desenvolvedor:
Desenvolvido por Matheus Santos Souza.

## Código de Inspiração
Professor Wilton Lacerda. [Acesse o GitHub do Professo Wilton](https://github.com/wiltonlacerda/EmbarcaTechU4C6)

## Vídeo Explicativo e Demonstrativo

[Vídeo Explicativo Via YouTube](https://youtu.be/TUSUu4HAW5s)





