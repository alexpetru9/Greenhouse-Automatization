# 🌿 Greenhouse Automatization System

Acest proiect reprezintă un sistem de monitorizare și control automatizat pentru o seră, construit folosind tehnologia **Arduino**. Scopul sistemului este de a optimiza condițiile de creștere a plantelor prin reglarea automată a temperaturii, umidității și ventilației, reducând astfel costurile și intervenția umană.

---

## 🛠️ Componente Utilizate (Hardware)

Pentru realizarea acestui sistem am folosit următoarele componente:
* **Microcontroler:** Arduino Nano (unitatea centrală de procesare)
* **Senzor Temperatură & Umiditate:** DHT11
* **Senzor Lumină:** Modul Fotorezistență (pentru detectarea regimului Zi/Noapte)
* **Acționare Ușă:** Servo motor SG90
* **Ventilație:** Ventilator AFB0405MA-A (controlat via tranzistor 2N2222 și rezistență de 1kΩ)
* **Altele:** Breadboard, fire Jumper, rezistențe.

---

## ⚙️ Logica de Funcționare

Sistemul ia decizii în timp real pe baza datelor primite de la senzori, urmând un set de reguli logice:

| Condiție | Acțiune Ușă (Servo) | Acțiune Ventilator |
| :--- | :--- | :--- |
| **Temperatură > 25°C (Zi)** | Deschisă 🔓 | Oprit ⚪ |
| **Umiditate > 50% (Zi)** | Închisă 🔒 | Pornit 🟢 |
| **Temp > 30°C & Umiditate > 50%** | Deschisă 🔓 | Pornit 🟢 |
| **Temperatură sau Umiditate mare (Noapte)** | Închisă 🔒 | Pornit 🟢 |

*Sistemul face distincția între zi și noapte folosind fotorezistența, adaptând ventilația pentru a proteja plantele în timpul nopții.*

---

## 🔌 Conexiuni (Circuit Diagram)

Componentele sunt conectate la Arduino Nano astfel:
* **DHT11:** Pin Digital 8
* **Senzor Lumină:** Pin Digital 9
* **Ventilator (via Tranzistor):** Pin Digital 7
* **Servo Motor:** Pin PWM 6

---

## 🚀 Cum se utilizează

1.  **Hardware:** Realizează conexiunile conform diagramei de circuit (vezi secțiunea de mai sus).
2.  **Software:** Încarcă codul Arduino (furnizat în folderul `/src`) folosind Arduino IDE.
3.  **Monitorizare:** Sistemul va începe automat citirea datelor și controlul actuatorilor (servo și ventilator).

---

## 📈 Beneficii
* **Eficiență:** Consum redus de energie prin activarea componentelor doar la nevoie.
* **Productivitate:** Menține un microclimat ideal pentru plante 24/7.
* **Accesibilitate:** Soluție low-cost bazată pe componente ușor de găsit.

---
*Proiect realizat ca parte a studiului sistemelor de automatizare hardware.*
