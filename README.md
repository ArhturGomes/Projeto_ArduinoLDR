# Projeto Arduino - Sensor de Luz com LED

👥 Integrantes: **Thalisson Rocha** e **Arthur Gomes**

## 🎯 Objetivo
Este projeto demonstra como utilizar um **sensor LDR (Light Dependent Resistor)** para medir a intensidade da luz ambiente e controlar um **LED**.  
A ideia é simples: quando o ambiente estiver muito iluminado, o LED acende; caso contrário, ele permanece apagado.

## ⚙️ Componentes Utilizados
- [Arduino UNO](ca://s?q=Arduino_UNO)
- [LED](ca://s?q=LED_em_projetos_Arduino)
- [Resistor LDR](ca://s?q=Sensor_LDR_Arduino)
- Resistores auxiliares
- Protoboard e fios de conexão

<img src="https://github.com/ArhturGomes/Projeto_ArduinoLDR/blob/8eb0e20d9b3c1e58de72cdca919509ca9aaed9c4/Captura%20de%20tela%202026-09-09%20165027.png" alt="Descrição da imagem" width="700" height="500">

## 📜 Observações

```cpp
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


