# ⚡ HEMS Sektorenkopplungs-Demonstrator – Downloads & Startanleitung

Willkommen im offiziellen Download-Portal des **HEMS Sektorenkopplungs-Demonstrators** (Photovoltaik, Heimspeicher, Wärmepumpe, Klimaanlage, Wallbox/V2H & Dynamische Stromtarife).

👉 **[Hier klicken, um direkt zur aktuellsten Version unter „Releases“ zu gelangen](../../releases/latest)**

---

## 📦 1. Welches Paket soll ich herunterladen?

Unter **[Releases](../../releases/latest)** findest du im Bereich **„Assets“** vier fertige Pakete für alle gängigen Systeme:

| Betriebssystem | Dateiname | Besonderheit & Empfehlung |
| :--- | :--- | :--- |
| **🪟 Windows 10 / 11** *(Empfohlen)* | `HEMS-Demonstrator-v...-Windows-Standalone.zip` | **Kein Java nötig, keine Admin-Rechte nötig.** Einfach ZIP entpacken und `HEMS-Demonstrator.exe` starten. |
| **🍏 macOS** *(Apple Silicon & Intel)* | `HEMS-Demonstrator-1.0.0.dmg` | **Kein Java nötig.** Disk-Image öffnen und die App in den `Programme`-Ordner ziehen. |
| **🐧 Linux** *(Ubuntu / Debian / Mint)* | `hems-demonstrator_1.0.0-1_amd64.deb` | **Kein Java nötig.** Natives Debian-Paket zur Installation über Paketmanager oder `dpkg`. |
| **✉️ Universal-Paket** *(Klein, ~6 MB)* | `HEMS-Demonstrator-v...-Universal-MailPackage.zip` | Für alle Systeme geeignet, setzt aber ein bereits installiertes **Java 21 (JDK/JRE)** auf dem Rechner voraus. |

---

## 🛡️ 2. Wichtiger Hinweis beim allerersten Start (Sicherheitseinstellungen)

Da dieses Bildungsprojekt **kostenfrei und nicht-kommerziell** bereitgestellt wird, verzichten wir auf kostenpflichtige kommerzielle Herausgeber-Zertifikate (Code-Signing) von Apple und Microsoft. Beim **allerersten Start** zeigen macOS und Windows daher standardmäßig einen Sicherheitshinweis an, den du einmalig wie folgt bestätigen kannst:

### 🍏 macOS (Apple Gatekeeper einmalig freigeben)
Nachdem du die `HEMS-Demonstrator.dmg` geöffnet und das Programm in deinen `Programme`-Ordner gezogen hast, erscheint beim ersten Öffnen die Meldung:
> *„HEMS-Demonstrator“ nicht geöffnet – Apple konnte nicht überprüfen, ob „HEMS-Demonstrator“ frei von Schadsoftware ist.*

**Lösung A – Über die Systemeinstellungen (ohne Terminal):**
1. Klicke in dem Warnfenster auf **„Fertig“** *(bitte **nicht** auf „In den Papierkorb legen“ klicken!)*.
2. Öffne die **Systemeinstellungen** deines Macs (über das -Menü oben links) und wähle links **„Datenschutz & Sicherheit“**.
3. Scrolle rechts nach unten zum Abschnitt **„Sicherheit“**. Dort siehst du den Hinweis *„‚HEMS-Demonstrator‘ wurde blockiert, da es nicht von einem verifizierten Entwickler stammt“*.
4. Klicke daneben auf **„Trotzdem öffnen“** und bestätige mit deinem Mac-Passwort oder per Fingerabdruck (Touch ID).
5. *Fertig!* Ab dem zweiten Start öffnet sich der Demonstrator sofort ohne jede Rückfrage.

**Lösung B – Blitz-Freigabe per Terminal (für Fortgeschrittene):**
Öffne die App **Terminal** (`Cmd + Leertaste` $\rightarrow$ `Terminal`) und führe einmalig diesen Befehl aus, um das Apple-Quarantäne-Attribut zu entfernen:
```bash
xattr -cr /Applications/HEMS-Demonstrator.app
```

---

### 🪟 Windows 10 / 11 (Microsoft Defender SmartScreen)
1. Lade die Datei `HEMS-Demonstrator-v...-Windows-Standalone.zip` herunter.
2. **Wichtig:** Klicke mit der rechten Maustaste auf die ZIP-Datei $\rightarrow$ **„Alle extrahieren...“**, um den Ordner komplett zu entpacken (z. B. auf deinen Desktop). Starte die `.exe` nicht direkt aus der ungepackten ZIP-Vorschau heraus.
3. Öffne den entpackten Ordner `HEMS-Demonstrator` und doppelklicke auf **`HEMS-Demonstrator.exe`**.
4. Erscheint das blaue SmartScreen-Fenster (*„Der PC wurde durch Windows geschützt“*), klicke links auf den unterstrichenen Text **„Weitere Informationen“**.
5. Klicke anschließend unten rechts auf den Button **„Trotzdem ausführen“**.
6. *Hinweis zur Windows-Firewall:* Falls beim ersten Start ein Fenster der Windows Defender Firewall erscheint, erlaube den Zugriff (der Simulator startet lediglich lokal auf deinem eigenen Rechner unter `http://localhost:8080`).

---

### 🐧 Linux (Ubuntu / Debian / Linux Mint)
1. Öffne ein Terminal im Download-Ordner und installiere das `.deb`-Paket mit:
   ```bash
   sudo dpkg -i hems-demonstrator_*_amd64.deb
   ```
2. Starte den Demonstrator danach über dein Anwendungsmenü oder direkt im Terminal über:
   ```bash
   /opt/hems-demonstrator/bin/HEMS-Demonstrator
   ```

---

## 🌐 3. Bedienung im Browser & Beenden der Anwendung

* **Automatischer Browser-Start:** Nach dem Start der Anwendung fährt im Hintergrund der lokale Simulations-Server hoch und öffnet nach ca. 3–5 Sekunden automatisch deinen Standardbrowser unter der Adresse **`http://localhost:18080`**.
* **Manuelles Öffnen:** Sollte sich das Browserfenster nicht von selbst öffnen, gib einfach **`http://localhost:18080`** in die Adresszeile eines beliebigen Browsers (Chrome, Edge, Firefox, Safari) ein.
* **Sauberes Beenden:** Da die Standalone-App als Hintergrundprozess läuft, reicht das bloße Schließen des Browser-Tabs nicht aus, um den Server zu stoppen. Klicke zum vollständigen Beenden bitte oben rechts in der Kopfleiste des Dashboards auf den Button **`⏹️ Beenden`**.

---

## ⚖️ 4. Rechtlicher Hinweis, Normen-Stand & Lizenz (Stand: November 2026)

* **Eingefrorener Rechts- und Normen-Stand (11/2026):** Alle im Simulator hinterlegten Gesetze, Tarife und technischen Regelwerke (insbesondere **§ 14a EnWG**, **§ 9 EEG Solarspitzengesetz**, **Solarpaket I**, **VDE-AR-N 4105**, **DIN EN 50160** sowie **IEC 61851-1**) beziehen sich auf den Stand **November 2026**.
* **Haftungsausschluss (Kein Fachplanungswerkzeug):** Diese Software dient ausschließlich zu Lehr-, Forschungs- und Demonstrationszwecken. Sie ersetzt keine elektrotechnische Fachplanung nach VDE / § 13 NAV und keine verbindliche Wirtschaftlichkeits- oder Steuerberatung. Die Bereitstellung erfolgt unentgeltlich unter Ausschluss jeglicher Haftung im Rahmen der §§ 521, 523, 524 BGB.
* **Nicht-kommerzielle Lizenz (Non-Commercial):** Die Nutzung und Weitergabe für Privatpersonen, Schulen, Hochschulen, gemeinnützige Vereine und Klimaschutz-Initiativen ist kostenfrei gestattet. Jede kommerzielle Verwertung (Verkauf, kostenpflichtiges Hosting oder Einsatz in entgeltlicher Verkaufsberatung ohne schriftliche Genehmigung) ist untersagt.
