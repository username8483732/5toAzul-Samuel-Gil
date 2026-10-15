# 5toAzul-Samuel-Gil
Pensamiento computacional 
**actividad#3,15/10**
En esta actividad que consistiré en crear un producto para solucionar el problema. yo y Juan González 
realizamos el siguiente circuito
El problema es que en lugares con mucha cola como en una panadería o una farmacia, mucha gente no sabe cuando lo llaman, en que turno le tocan, mucha gente se colea con intención o sin intención, y que el encargado tenga que gritar sus nombres. Esto genera problemas como mucho desorden y caos.

La solución a esto es el siguiente dispositivo que va ayudar a mantener el orden, va ayudar a que la gente  sepa cual es su turno en la cola, va ahorrar malentendidos, y no hay interrupciones.

El funcionamiento del dispositivo es que el encargado presiona un botón al terminar con un cliente. El sistema suma un turno, lo muestra en el monitor serial ("Turno 5, pase por favor") y hace parpadear un LED para llamar la atención.

 El código del programa es: 

const int boton = 2;
const int led = 13;
int turno = 0;

void setup() {
  pinMode(boton, INPUT_PULLUP);
  pinMode(led, OUTPUT);
  Serial.begin(9600);
  Serial.println("Sistema de turnos listo");
}

void loop() {
  if (digitalRead(boton) == LOW) {      // entrada: botón presionado
    turno++;                            // proceso: siguiente turno
    Serial.print("Turno ");
    Serial.print(turno);
    Serial.println(", pase por favor");
    for (int i = 0; i < 3; i++) {       // respuesta: LED parpadea
      digitalWrite(led, HIGH);
      delay(200);
      digitalWrite(led, LOW);
      delay(200);
    }
    while (digitalRead(boton) == LOW);  // espera a que suelten el botón<img width="2360" height="1640" alt="IMG_0710" src="https://github.com/user-attachments/assets/13f63a9b-4508-4c5a-9436-9fbc848ed5c3" />
<img width="2360" height="1640" alt="IMG_0709" src="https://github.com/user-attachments/assets/29f6561c-2f06-4004-87b2-2485f3fd38cd" />
