
# 🌱 Projeto Arduino: Monitoramento de Umidade do Solo

Este projeto tem como objetivo monitorar a umidade do solo usando um **sensor de umidade** conectado a uma **placa Arduino UNO**, permitindo acionar um LED quando o solo estiver seco ou úmido, além de exibir informações em tempo real no **terminal serial**.

---

## 🔧 Componentes Utilizados

- Arduino UNO
- Módulo Sensor de Umidade do Solo (Soil Moisture Sensor)
- LED Vermelho (indicador visual)
- Resistor de 220 ohms
- Jumpers
- Solo simulado com planta (no Proteus)
- Fonte de alimentação 5V (pelo Arduino)
- Software: [Proteus 8.x](https://www.labcenter.com/downloads/) (simulação) e [Arduino IDE](https://www.arduino.cc/en/software) (programação)

---

## ⚙️ Funcionamento

- O **sensor de umidade** possui duas saídas:
  - **Digital (D0)**: retorna `LOW` se o solo estiver úmido e `HIGH` se estiver seco.
  - **Analógica (A0)**: retorna um valor entre `0–1023`, representando o nível de umidade do solo.
- O Arduino lê os dois sinais e:
  - Exibe mensagens no **monitor serial** sobre o estado do solo (úmido ou seco).
  - Acende ou apaga um LED indicando o estado atual.
  - Mostra a variação do nível de umidade com mensagens do tipo:
    - `Umidade aumentando: <valor>`
    - `Umidade diminuindo: <valor>`

---

## 🖥️ Esquema do Circuito

O circuito foi desenvolvido no **Proteus** e está conectado da seguinte forma:

- **VCC do sensor** → 5V do Arduino  
- **GND do sensor** → GND do Arduino  
- **A0 do sensor** → A0 do Arduino  
- **D0 do sensor** → Pino digital 8 do Arduino  
- **LED** conectado ao LED_BUILTIN (pino 13 do Arduino UNO)

![Esquema no Proteus](./debde5df-5613-4e57-aa0c-52f6b676b158.png)

---

## 💻 Código-Fonte

O código completo está no arquivo [`main.ino`](./main.ino) e implementa:

- Leitura digital e analógica do sensor
- Detecção de mudanças no estado do solo
- Exibição no terminal serial
- Indicação visual com LED

---

## 📈 Possíveis Melhorias Futuras

- Enviar alertas via Wi-Fi (usando ESP8266/ESP32)
- Registrar dados em um cartão SD ou banco de dados online
- Sistema de irrigação automatizado
- Interface web ou dashboard IoT

---

## 📄 Licença

Este projeto está licenciado sob a [MIT License](LICENSE).

---

## 🤝 Contribuições

Sinta-se à vontade para abrir *issues*, sugerir melhorias ou enviar *pull requests*. Toda colaboração é bem-vinda!

---

## 👨‍💻 Autor

Desenvolvido por José de Almeida (NekoZer0).
