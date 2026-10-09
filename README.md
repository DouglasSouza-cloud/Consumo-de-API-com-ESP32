# ESP32 — Cotação de Moedas

Projeto desenvolvido com ESP32 e display OLED para consultar e exibir cotações de moedas em relação ao real brasileiro (BRL), utilizando uma API de dados financeiros.

## Funcionalidades

* Conexão Wi-Fi.
* Consulta de cotações por meio de uma API.
* Exibição dos valores em um display OLED.
* Apresentação da variação percentual das cotações.
* Alternância automática entre seis moedas a cada 5 segundos.
* Atualização dos dados da API a cada 30 segundos.

## Tecnologias utilizadas

* ESP32
* Arduino/C++
* Display OLED SSD1306 de 128 × 64 pixels
* Comunicação I²C
* Wi-Fi
* API [AwesomeAPI](https://docs.awesomeapi.com.br/)

## Moedas consultadas

* Dólar americano (USD)
* Euro (EUR)
* Libra esterlina (GBP)
* Peso argentino (ARS)
* Bitcoin (BTC)
* Iene japonês (JPY)

## Componentes

* 1 ESP32
* 1 display OLED I²C
* Jumpers para as conexões

## Conexões

| Display OLED | ESP32   |
| ------------ | ------- |
| GND          | GND     |
| VCC          | 3V3     |
| SCL          | GPIO 22 |
| SDA          | GPIO 21 |

## Bibliotecas necessárias

Instale as seguintes bibliotecas na Arduino IDE:

* Adafruit GFX Library
* Adafruit SSD1306
* ArduinoJson

As bibliotecas `WiFi.h`, `WiFiClientSecure.h`, `HTTPClient.h` e `Wire.h` fazem parte do ambiente ESP32 ou do core Arduino utilizado.

## Como executar

1. Monte o circuito conforme a tabela de conexões.
2. Abra o código na Arduino IDE.
3. Instale as bibliotecas necessárias.
4. Configure o Wi-Fi no código.
5. Selecione a placa ESP32 e a porta correspondente.
6. Compile e envie o programa.
7. Acompanhe as cotações no display OLED e as mensagens pelo Monitor Serial, configurado em 115200 baud.

## API utilizada

O projeto utiliza a AwesomeAPI para obter as cotações por meio de requisições HTTPs.

Endpoint utilizado:

`https://economia.awesomeapi.com.br/json/last/USD-BRL,EUR-BRL,GBP-BRL,ARS-BRL,BTC-BRL,JPY-BRL`

## Observações

* É necessária uma conexão com a internet para atualizar as cotações.
* Os valores exibidos dependem da disponibilidade e da resposta da API.
* O código utiliza `setInsecure()` para a conexão HTTPS, sem validar o certificado do servidor. Essa configuração é destinada a testes e deve ser substituída por validação de certificado em aplicações reais.

## Objetivo

Praticar a integração entre microcontroladores, comunicação I²C, conexão Wi-Fi, consumo de APIs e exibição de dados em tempo real.
