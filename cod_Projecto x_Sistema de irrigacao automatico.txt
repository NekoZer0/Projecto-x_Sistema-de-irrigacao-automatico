// Define o pino digital conectado à saída digital do sensor de umidade
int pinoDigitalUmidade = 8;

// Define o pino analógico conectado à saída analógica do sensor de umidade
int pinoAnalogicoUmidade = A0;

// Variável para guardar o último estado lido do pino digital (seco ou úmido)
bool estadoAnteriorDigital = HIGH;

// Variável para guardar o último valor lido da umidade analógica
int nivelAnteriorUmidade = 0;


void setup() {
  Serial.begin(9600); // Inicia a comunicação serial com o terminal (ex: Virtual Terminal no Proteus)

  pinMode(pinoDigitalUmidade, INPUT);   // Define o pino digital como entrada
  pinMode(LED_BUILTIN, OUTPUT);         // Define o LED interno como saída (útil para indicar se o solo está seco ou úmido)

  // Lê o estado inicial do sensor digital (LOW = úmido, HIGH = seco)
  int estadoInicial = digitalRead(pinoDigitalUmidade);

  // Lê o valor inicial da umidade (0–1023) do sensor analógico
  int nivelInicial = analogRead(pinoAnalogicoUmidade);

  // Verifica o estado inicial do solo usando o sensor digital
  if (estadoInicial == LOW) {
    Serial.println("Solo umido!");         // Mostra mensagem no terminal
    digitalWrite(LED_BUILTIN, HIGH);       // Acende o LED se estiver úmido
  } else {
    Serial.println("Solo seco.");
    digitalWrite(LED_BUILTIN, LOW);        // Apaga o LED se estiver seco
  }

  // Mostra o valor lido da umidade analógica
  Serial.print("Nivel inicial de umidade: ");
  Serial.println(nivelInicial);

  // Atualiza as variáveis de estado anterior
  estadoAnteriorDigital = estadoInicial;
  nivelAnteriorUmidade = nivelInicial;
}

void loop() {
  // Lê o estado atual do sensor digital
  int estadoAtual = digitalRead(pinoDigitalUmidade);

  // Lê o nível atual da umidade no pino analógico
  int nivelAtual = analogRead(pinoAnalogicoUmidade);

  // Verifica se o estado digital mudou desde a última leitura
  if (estadoAtual != estadoAnteriorDigital) {
    estadoAnteriorDigital = estadoAtual;

    if (estadoAtual == LOW) {
      Serial.println("Solo umido!");
      digitalWrite(LED_BUILTIN, HIGH);  // Acende o LED se o solo estiver úmido
    } else {
      Serial.println("Solo seco.");
      digitalWrite(LED_BUILTIN, LOW);   // Apaga o LED se estiver seco
    }
  }

  // Verifica se o nível analógico mudou
  if (nivelAtual != nivelAnteriorUmidade) {
    if (nivelAtual > nivelAnteriorUmidade) {
      Serial.print("Umidade aumentando: ");   // Solo ficando mais úmido
    } else {
      Serial.print("Umidade diminuindo: ");   // Solo ficando mais seco
    }

    // Mostra o novo valor da umidade
    Serial.println(nivelAtual);

    // Atualiza o valor anterior
    nivelAnteriorUmidade = nivelAtual;
  }

  delay(100); // Espera 100 milissegundos antes da próxima leitura
}


