
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

## 🗂️ Estrutura de Pastas

```
PROJECTO_X_SISTEMA_DE_IRRIGACAO_AUTOMATICO/
├── Arduino/
│   └── Projecto_X_Sistema_de_irrigacao_automatico/
│       ├── build/
│       │   ├── arduino.avr.uno
│       │   └── arduino.avr.circuitplay32u4cat
│       └── Projecto_X_Sistema_de_irrigacao_automatico.ino
├── Proteus/
│   ├── Project Backups/
│   │   └── Vários backups automáticos (*.pdsprj)
│   ├── Projecto_X_Sistema_de_irrigacao_automatico.pdsprj
│   └── Projecto_X_Sistema_de_irrigacao_automatico.pdsprj.JS02.Huawei.workspace
├── README.md
```

---

## 🖥️ Esquema do Circuito

O circuito foi desenvolvido no **Proteus** e está conectado da seguinte forma:

- **VCC do sensor** → 5V do Arduino  
- **GND do sensor** → GND do Arduino  
- **A0 do sensor** → A0 do Arduino  
- **D0 do sensor** → Pino digital 8 do Arduino  
- **LED** conectado ao LED_BUILTIN (pino 13 do Arduino UNO)

![Esquema no Proteus](./f6eaaeaf-f2c4-423c-8e4e-843e592afacb.png)

---

## ▶️ Como Abrir o Projeto

### 🔹 Código Arduino:
1. Acesse a pasta `Arduino/Projecto_X_Sistema_de_irrigacao_automatico/`.
2. Abra o arquivo `Projecto_X_Sistema_de_irrigacao_automatico.ino` com o **Arduino IDE**.
3. Conecte a placa (se estiver usando hardware real) ou use o **Proteus** para simular.

### 🔹 Simulação no Proteus:
1. Vá para a pasta `Proteus/`.
2. Abra o arquivo `Projecto_X_Sistema_de_irrigacao_automatico.pdsprj` com o **Proteus 8.x**.
3. Clique em **Play** para iniciar a simulação.

> ⚠️ Se necessário, selecione o arquivo `.hex` ou carregue o `.ino` a partir da simulação.

---

## 💻 Código-Fonte

O código completo está no arquivo [`Projecto_X_Sistema_de_irrigacao_automatico.ino`](./Arduino/Projecto_X_Sistema_de_irrigacao_automatico/Projecto_X_Sistema_de_irrigacao_automatico.ino) e implementa:

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

Desenvolvido por [Seu Nome Aqui].
