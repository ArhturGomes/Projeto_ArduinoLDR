# Projeto Arduino - Sensor de Luz com LED

## 🎯 Objetivo
Este projeto demonstra como utilizar um **sensor LDR (Light Dependent Resistor)** para medir a intensidade da luz ambiente e controlar um **LED**.  
A ideia é simples: quando o ambiente estiver muito iluminado, o LED acende; caso contrário, ele permanece apagado.

## ⚙️ Componentes Utilizados
- [Arduino UNO](ca://s?q=Arduino_UNO)
- [LED](ca://s?q=LED_em_projetos_Arduino)
- [Resistor LDR](ca://s?q=Sensor_LDR_Arduino)
- Resistores auxiliares
- Protoboard e fios de conexão

## 📜 Código
```cpp
int LED = 13;       // Pino do LED
int LDR = A0;       // Pino do sensor LDR
int valor_LDR;      // Variável para armazenar leitura

void setup() {
  pinMode(LED, OUTPUT);
  pinMode(LDR, INPUT);
  Serial.begin(9600); // Comunicação serial
}

void loop() {
  valor_LDR = analogRead(LDR);   // Lê intensidade da luz
  Serial.println(valor_LDR);     // Exibe no monitor serial

  if (valor_LDR > 1000) {        // Se luz for intensa
    digitalWrite(LED, HIGH);     // Acende LED
  } else {
    digitalWrite(LED, LOW);      // Apaga LED
  }
  delay(1000);                   // Aguarda 1 segundo
}


