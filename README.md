# Projeto de Modulação e Demodulação AM no GNU Radio

Este repositório contém um projeto de simulação de modulação e demodulação AM (Amplitude Modulation) desenvolvido utilizando o GNU Radio. O objetivo é demonstrar a criação de um sistema completo de transmissão e recepção de áudio modulado em amplitude, incluindo a adição de ruído e a recuperação do sinal original.

## Descrição do Projeto

O projeto consiste em dois sistemas principais: **Transmissão** e **Recepção**.

- **Sistema de Transmissão:** O sistema realiza a leitura de um arquivo de áudio `.wav`, aplica um processo de interpolação para ajustar a taxa de amostragem e modula o sinal utilizando uma portadora de 150 kHz. Após a modulação, o sinal é somado a um ruído gaussiano para simular interferências do canal de transmissão.
  
  ![image](https://github.com/user-attachments/assets/39a12d73-79f5-4591-aece-811b31ccabf4)

- **Sistema de Recepção:** O sinal modulado e ruidoso é recebido, demodulado para recuperar as informações originais e enviado para o bloco de áudio, onde pode ser reproduzido para verificar a integridade do sinal recuperado.

  ![image](https://github.com/user-attachments/assets/789981dc-eb30-4692-9ec6-ea055da6772a)


## Estrutura dos Blocos

- **WAV File Source:** Carrega o arquivo de áudio utilizado como sinal base.
- **Interpolating FIR Filter:** Ajusta a taxa de amostragem para a modulação.
- **Multiply e Add Const:** Ajustam amplitude e offset do sinal.
- **Signal Source:** Gera a portadora de 150 kHz para a modulação AM.
- **Multiply (Modulação):** Realiza a modulação multiplicando o áudio pela portadora.
- **Noise Source:** Adiciona ruído gaussiano ao sinal modulado.
- **AM Demod:** Demodula o sinal, extraindo o áudio original.
- **Audio Sink:** Reproduz o áudio recuperado após a demodulação.

## Requisitos

- GNU Radio >= 3.8
- Áudio de entrada no formato `.wav` com taxa de amostragem de 48 kHz e 16 bits.

## Como Executar

1. Clone este repositório:
   ```bash
   git clone https://github.com/seu-usuario/projeto-am-modulation.git
