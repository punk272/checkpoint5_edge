<h1 align="center"> Checkpoint 5 - DHT11 + LDR no ESP32 | Vinheria Agnello </h1> <br>
<p align="center">
  <a href="https://github.com/punk272/checkpoint5_edge">
    <img alt="Circuito" title="Wokwi" src="https://imgur.com/rHbCDoS.png" width="1000">
  </a>
</p>


## Tópicos do projeto

- [Projeto](#projeto)
- [Componentes](#componentes)
- [Requisitos](#requisitos)
- [Autores](#autores)

## Projeto

Após o sucesso da primeira fase do projeto da Vinheria Agnello é hora de expandir os negócios e fazer um upgrade no circuito que mede a temperatura, umidade e luminosidade do ambiente onde os vinhos ficam armazenados.
Seguindo a necessidade de saber exatamente qual a temperatura e umidade do depósito, da integração da vinheria a distribuidores europeus e da consequente demanda dos dados históricos o mais rápido possível, implementamos um circuito diferente:
Para a leitura dos valores de temperatura, umidade e luminosidade capturados pelo sensores DHT11 (ou DHT22) e LDR será utilizado um microcontrolador ESP32.
Com essa mudança, os dados coletados podem ser enviados para uma plataforma back-end FIWARE (plataforma para coletar, processar, armazenar e compartilhar informações na hora da execução), através do protocolo MQTT(Sistemas de Supervisão e Aquisição de Dados, gerenciando a transformação de mensagens MQTT em atualizações de contexto compreensíveis), em tempo real. Basicamente, o microcontrolador, através dos sensores, captam um dado que é armazenado no FIWARE através das mensagens MQTT, assim conseguindo armazenar informações mais precisas e confiáveis.

## Componentes

Peças usadas na construção deste circuito:

* 1 x Placa ESP32
* 1 x Breadboard
* 1 x Sensor DHT11 ou DHT22
* 1 x Resistor Dependente da Luz (LDR)
* 1 x Resistor de 10k Ohms
* 8 x Jumpercables

## Requisitos

* Collection FIWARE Postman (FIWARE.postman_collection.json): Recebe e armazena dos dados do ESP32.
* Biblioteca Paho-MQTT (FIAP_Fiware_Paho.ipynb): Leitura dos dados obtidos pelo ESP32.
* Código Fonte IDE Arduino (fiware_ngsi_mqtt_esp32.ino): Código principal do circuito, faz todo o processo de captura, leitura de dados e comunicação do microcontrolador com o servidor IoT através de Wi-Fi.
* Gráfico de Luminosidade (sth-comet.py): Obtém os dados de luminosidade para a criação de um gráfico em função do tempo.
* Docker e Docker-Compose Ubuntu Server LTS (docker-compose.yml): Software onde o servidor será instalado (Clique <a href=https://docs.docker.com/engine/install/ubuntu/> aqui </a> para ver as instruções de instalação.

## Autores

- **Leonardo Mansur**
- **Luís Guilherme**
