<div align="center">

  <img src="../images/Logo.png" width="180" alt="dmd-core-logo" />
  
  # Smart Home IoT system
  **Arkitektonisk og udviklet af dmd-core**

![ESP32](https://img.shields.io/badge/ESP32-IoT-blue)
![Blynk](https://img.shields.io/badge/Blynk-Cloud-green)
![Arduino](https://img.shields.io/badge/Arduino-C++-00979D)
![Wokwi](https://img.shields.io/badge/Wokwi-Simulation-orange)
![Lizenz](https://img.shields.io/badge/Lizenz-MIT-red)
</div>
Ein IoT-basiertes Smart-Home-Automatisierungssystem, entwickelt mit **ESP32**, **Blynk Cloud** und dem **Wokwi-Simulator**.

Dieses Projekt demonstriert die praktische Anwendung moderner IoT-Technologien (Internet der Dinge), um Haushaltsgeräte über das Internet fernzusteuern. Die Steuerung erfolgt über die Blynk-Plattform, während der ESP32 als zentrale Steuereinheit dient.

Das gesamte System wurde in der Simulationsumgebung Wokwi entwickelt und getestet, sodass keine physische Hardware erforderlich ist.

---

# 📚 Inhaltsverzeichnis

* Projektübersicht
* Hauptfunktionen
* Systemarchitektur
* Verwendete Technologien
* Hardwarekomponenten
* Softwareanforderungen
* Pinbelegung
* Schaltungsaufbau
* Installationsanleitung
* Einrichtung von Blynk
* Wokwi-Simulation
* Erklärung des Quellcodes
* Funktionsweise
* Testverfahren
* Fehlerbehebung
* Sicherheitshinweise
* Erweiterungsmöglichkeiten
* Projektdokumentation
* Sprache der Dokumentation
* Autor
* Lizenz
* Danksagung

---

# 📌 Projektübersicht

Ziel dieses Projekts ist die Entwicklung eines einfachen, aber erweiterbaren Smart-Home-Systems auf Basis eines ESP32-Mikrocontrollers.

Das System ermöglicht die Fernsteuerung von drei grundlegenden Haushaltsfunktionen:

* 💡 Beleuchtung
* 🔥 Heizung
* ❄️ Kühlung

Die Kommunikation erfolgt über WLAN und die Blynk Cloud. Benutzer können sämtliche Funktionen bequem über eine mobile Anwendung steuern.

Dieses Projekt eignet sich besonders für:

* Studierende der Informatik und Elektrotechnik
* Einsteiger im Bereich Internet of Things
* Entwickler von Embedded-Systemen
* Smart-Home-Enthusiasten

---

# ✨ Hauptfunktionen

* Fernsteuerung von Geräten über Smartphone
* Echtzeit-Kommunikation über die Cloud
* WLAN-Konnektivität mit ESP32
* Integration in die Blynk-Plattform
* Modulare Firmware-Struktur
* Erweiterbares Smart-Home-Konzept
* Simulation ohne reale Hardware
* Benutzerfreundlicher Aufbau
* Lehr- und Lernprojekt für IoT-Anwendungen

---

# 🏗 Systemarchitektur

```text
Benutzer
   │
   ▼
Blynk Mobile App
   │
   ▼
Blynk Cloud
   │
   ▼
ESP32
 ├── Beleuchtung
 ├── Heizung
 └── Kühlung
```

### Datenfluss

1. Der Benutzer betätigt einen Schalter in der Blynk-App.
2. Die App sendet den Befehl an die Blynk Cloud.
3. Die Cloud leitet den Befehl an den ESP32 weiter.
4. Der ESP32 verarbeitet den Befehl.
5. Der entsprechende GPIO-Pin wird aktiviert oder deaktiviert.
6. Das angeschlossene Gerät reagiert unmittelbar.

---

# 🛠 Verwendete Technologien

| Kategorie            | Technologie       |
| -------------------- | ----------------- |
| Mikrocontroller      | ESP32             |
| Programmiersprache   | C++               |
| Entwicklungsumgebung | Arduino Framework |
| IoT-Plattform        | Blynk Cloud       |
| Kommunikation        | WLAN              |
| Simulation           | Wokwi             |
| Versionsverwaltung   | Git               |
| Repository           | GitHub            |

---

# 🔧 Hardwarekomponenten

| Komponente              | Anzahl  |
| ----------------------- | ------- |
| ESP32 Entwicklungsboard | 1       |
| LED                     | 3       |
| Widerstand 220 Ω        | 3       |
| Jumperkabel             | Mehrere |

---

# 💻 Softwareanforderungen

Für die Durchführung des Projekts werden folgende Programme benötigt:

* Arduino IDE
* ESP32 Board Package
* Blynk Bibliothek
* Wokwi Simulator
* Blynk Mobile App
* Git (optional)

---

# 📍 Pinbelegung

| Funktion    | GPIO    |
| ----------- | ------- |
| Beleuchtung | GPIO 23 |
| Heizung     | GPIO 22 |
| Kühlung     | GPIO 21 |

---

# 🔌 Schaltungsaufbau

Für Demonstrationszwecke werden LEDs verwendet.

### Beleuchtung

GPIO23 → Widerstand → LED → GND

### Heizung

GPIO22 → Widerstand → LED → GND

### Kühlung

GPIO21 → Widerstand → LED → GND

---

# 📸 Projektbilder

## Schaltplan

<img src="../images/circuit.png" width="180" alt="dmd-core-logo" />

## Blynk Dashboard

<img src="../images/dashboard.png" width="180" alt="dmd-core-logo" />

---

# 🚀 Installationsanleitung

## Schritt 1: Arduino IDE installieren

Laden Sie die aktuelle Version der Arduino IDE herunter und installieren Sie diese.

---

## Schritt 2: ESP32-Unterstützung installieren

Öffnen Sie:

Werkzeuge → Boardverwalter

Suchen Sie nach:

ESP32

Installieren Sie die aktuelle Version.

---

## Schritt 3: Blynk-Bibliothek installieren

Öffnen Sie den Bibliotheksverwalter und installieren Sie die aktuelle Version der Blynk-Bibliothek.

---

## Schritt 4: Repository klonen

```bash
git clone https://github.com/Dmd-core/SmartHome-ESP32.git
```

---

## Schritt 5: Projekt öffnen

Öffnen Sie die Datei:

```text
sketch.ino
```

in der Arduino IDE.

---

## Schritt 6: Zugangsdaten konfigurieren

Ersetzen Sie die Platzhalter durch Ihre eigenen Daten.

```cpp
#define BLYNK_TEMPLATE_ID   "IHRE_TEMPLATE_ID"
#define BLYNK_TEMPLATE_NAME "Smart Home"
#define BLYNK_AUTH_TOKEN    "IHR_TOKEN"

char ssid[] = "IHR_WLAN";
char pass[] = "IHR_PASSWORT";
```

---

## Schritt 7: Firmware hochladen

Wählen Sie das Board:

```text
ESP32 Dev Module
```

und laden Sie die Firmware hoch.

---

# ☁️ Einrichtung von Blynk

## Template erstellen

1. Bei Blynk anmelden
2. Neues Template erstellen
3. ESP32 auswählen
4. Verbindungstyp WLAN festlegen

---

## Datenströme erstellen

| Funktion    | Virtueller Pin |
| ----------- | -------------- |
| Beleuchtung | V0             |
| Heizung     | V1             |
| Kühlung     | V2             |

---

## Dashboard konfigurieren

Erstellen Sie drei Schalter-Widgets:

* V0 → Beleuchtung
* V1 → Heizung
* V2 → Kühlung

---

# 🖥 Wokwi-Simulation

Das gesamte Projekt kann ohne reale Hardware simuliert werden.

Vorgehensweise:

1. Projekt in Wokwi importieren
2. Simulation starten
3. Verbindung zur Blynk Cloud herstellen
4. Geräte über die App steuern

---

# ⚙️ Erklärung des Quellcodes

### Beleuchtung

```cpp
BLYNK_WRITE(V0)
{
    int state = param.asInt();
    digitalWrite(LAMP_PIN, state);
}
```

Steuert die Beleuchtung.

---

### Heizung

```cpp
BLYNK_WRITE(V1)
{
    int state = param.asInt();
    digitalWrite(HEATING_PIN, state);
}
```

Steuert die Heizung.

---

### Kühlung

```cpp
BLYNK_WRITE(V2)
{
    int state = param.asInt();
    digitalWrite(COOLING_PIN, state);
}
```

Steuert die Kühlung.

---

# 🔄 Funktionsweise

1. ESP32 verbindet sich mit dem WLAN.
2. ESP32 verbindet sich mit der Blynk Cloud.
3. Der Benutzer sendet einen Befehl.
4. Die Cloud übermittelt den Befehl.
5. Der GPIO-Zustand wird geändert.
6. Das angeschlossene Gerät reagiert sofort.

---

# 🧪 Testverfahren

### Test 1

Beleuchtung einschalten

Erwartetes Ergebnis:

LED leuchtet.

### Test 2

Heizung einschalten

Erwartetes Ergebnis:

LED leuchtet.

### Test 3

Kühlung einschalten

Erwartetes Ergebnis:

LED leuchtet.

---

# 🔍 Fehlerbehebung

### Keine WLAN-Verbindung

Prüfen Sie:

* WLAN-Name
* Passwort
* Router-Verbindung

### Gerät offline

Prüfen Sie:

* Authentifizierungstoken
* Template-ID
* Internetverbindung

### LEDs reagieren nicht

Prüfen Sie:

* Verdrahtung
* GPIO-Konfiguration
* Stromversorgung

---

# 🔒 Sicherheitshinweise

Veröffentlichen Sie niemals:

* WLAN-Passwörter
* Blynk-Tokens
* API-Schlüssel
* Zugangsdaten

Verwenden Sie stets Platzhalter vor dem Hochladen auf GitHub.

---

# 🚧 Erweiterungsmöglichkeiten

Geplante Verbesserungen:

* DHT22 Temperatursensor
* Luftfeuchtigkeitsmessung
* Automatische Klimaregelung
* Energieverbrauchsanalyse
* Push-Benachrichtigungen
* Sprachsteuerung
* Datenspeicherung
* TinyML-Integration
* KI-basierte Automatisierung

---

# 📄 Projektdokumentation

![System Diagram](IoT.de.pdf)

Rapporten forklarer:

* Projektmål
* IoT-koncepter
* ESP32-konfiguration
* Blynk-integration
* Kredsløbsdesign
* Implementeringsdetaljer

---

### 🌐 Dokumentationsgateway
Vælg dit foretrukne sprog for at udforske den tekniske dokumentation:

* GB **[English Documentation](../README.md)** — *English*
* IR **[Persian Documentation](README.fa.md)** — *قارسی*
---

# 👨‍💻 Autor

**Mohammad Hossein Almasi**

Student der Computertechnik

Interessengebiete:

* Internet der Dinge (IoT)
* Eingebettete Systeme
* ESP32-Entwicklung
* Künstliche Intelligenz
* Smart-Home-Automatisierung

GitHub:

https://github.com/Dmd-core

---

📜 Licens

Dette projekt er udgivet under MIT-licensen.

Du er fri til at:

* Bruge
* Ændre
* Distribuere
* Lære
* Bygge videre på projektet

til uddannelses- og forskningsformål.

---

# 🙏 Danksagung

Besonderer Dank gilt:

* der ESP32-Community
* der Blynk-Plattform
* dem Wokwi-Team
* der Arduino Open-Source-Community

für die Bereitstellung ihrer Werkzeuge und Ressourcen.

---

## ⭐ Unterstützung

Falls Ihnen dieses Projekt gefallen hat:

⭐ Repository bewerten

🍴 Repository forken

📢 Projekt weiterempfehlen

Vielen Dank für Ihr Interesse an diesem Projekt.

<div align="center">
  <br>
  <a href="dmd.core.dev@gmail.com">
    <img src="https://img.shields.io/badge/Email-000000?style=for-the-badge&logo=gmail&logoColor=white&logoWidth=20" alt="Email" />
  </a>
</div>
