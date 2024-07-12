const int TRIG_PIN = 6;
const int ECHO_PIN = 7;
const int LED_PIN = 3;
const int BUZZER_PIN = 4;
const int DISTANCE_THRESHOLD = 15; // en centímetros

void setup() {
    Serial.begin(9600);
    pinMode(TRIG_PIN, OUTPUT);
    pinMode(ECHO_PIN, INPUT);
    pinMode(LED_PIN, OUTPUT);
    pinMode(BUZZER_PIN, OUTPUT);
}

void loop() {
    digitalWrite(TRIG_PIN, HIGH);
    delayMicroseconds(10);
    digitalWrite(TRIG_PIN, LOW);
    float duration_us = pulseIn(ECHO_PIN, HIGH);
    float distance_cm = 0.017 * duration_us;

    if (distance_cm < DISTANCE_THRESHOLD) {
        digitalWrite(LED_PIN, HIGH);
        digitalWrite(BUZZER_PIN, HIGH);
    } else {
        digitalWrite(LED_PIN, LOW);
        digitalWrite(BUZZER_PIN, LOW);
    }

    Serial.print("Distancia: ");
    Serial.print(distance_cm);
    Serial.println(" cm");
    delay(500);
}
