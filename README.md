# Projeto FreeRTOS com BitDogLab e Raspberry Pi W

Este projeto utiliza FreeRTOS para gerenciar tarefas em um sistema embarcado na placa BitDogLab com o microcontrolador Raspberry Pi W. O código implementa um controle simples de botão e LED utilizando tarefas e semáforos para sincronização.

## Funcionalidade
O sistema consiste em três tarefas principais:

1. **Tarefa 1 (Leitura do Botão):**
   - Executada periodicamente a cada 100ms.
   - Lê o estado do botão.
   - Se detectar uma mudança de estado (botão pressionado), aciona a próxima tarefa.

2. **Tarefa 2 (Processamento do Botão):**
   - Aguarda o acionamento da Tarefa 1.
   - Se o botão for pressionado, ativa a Tarefa 3 para controle do LED.

3. **Tarefa 3 (Controle do LED):**
   - Controla o LED com base no estado do botão.
   - Se acionada, liga os LEDs por 1 segundo e depois os desliga.

## Hardware Utilizado
- **Placa**: BitDogLab com Raspberry Pi W
- **Pinos Utilizados**:
  - **Botão**: GPIO 5
  - **LED Azul**: GPIO 12
  - **LED Vermelho**: GPIO 13

## Dependências
Para compilar e rodar o projeto, é necessário ter:
- FreeRTOS
- SDK do Raspberry Pi Pico
- Biblioteca `pico/stdlib.h`
- Biblioteca `semphr.h`

## Como Compilar e Executar
1. Configure o ambiente do Raspberry Pi Pico e FreeRTOS.
2. Compile o código utilizando o CMake.
3. Faça o upload do firmware para a placa BitDogLab.
4. Conecte o terminal serial para visualizar os logs de execução.

## Licença
Este projeto é de código aberto e pode ser utilizado livremente para fins educacionais e experimentais.

