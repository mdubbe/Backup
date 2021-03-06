---

copyright:
  years: 1994, 2018
lastupdated: "2018-08-13"

---
{:pre: .pre}
{:new_window: target="_blank"}

# EVault unter Windows 2016 konfigurieren

## EVault-Softwareagenten installieren

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei herunterzuladen:
   ```
   http://downloads.service.softlayer.com/evault/
   ```
   {:pre}
   >**Hinweis** - Installieren Sie den Agenten der Version 8.30 oder einer höheren Version.
2. Doppelklicken Sie auf die heruntergeladene Datei und klicken Sie im daraufhin aufgerufenen Fenster auf **Ausführen**.
3. Wählen Sie die Sprache für Ihre Installation aus und klicken Sie auf **OK**.
4. Klicken Sie auf **Weiter**, um den Vorgang zu starten.
5. Lesen Sie die Bedingungen und wählen Sie dann **Ich akzeptiere die Bedingungen der Lizenzvereinbarung** aus. Klicken Sie anschließend auf **Weiter**.
6. Wählen Sie den Installationstyp **Standard** aus. Klicken Sie auf **Weiter**.
7. Wählen Sie in der Anzeige 'Agenten beim Portal registrieren' die Option **Registrierung überspringen** aus. Klicken Sie auf **Weiter**.
8. Klicken Sie in der nächsten Anzeige auf **Installieren**.
9. Klicken Sie nach Abschluss der Installation auf **Fertigstellen**.

## EVault Software CentralControl 8.30 installieren

1. Öffnen Sie auf dem Zielserver eine Browsersitzung und geben Sie die folgende URL ein, um die ausführbare Datei herunterzuladen:

   ```
   http://downloads.service.softlayer.com/evault/CentralControl/
   ```
   {:pre}

2. Doppelklicken Sie auf die heruntergeladene Datei und klicken Sie im daraufhin aufgerufenen Fenster auf **Ausführen**.
3. Befolgen Sie die Installationsschritte für eine **Standardinstallation**.
   1. Wenn Sie gefragt werden, ob eine Desktopverknüpfung hinzugefügt werden soll, dann wählen Sie **Ja** aus. Klicken Sie auf **Weiter**.
   2. Lesen Sie die Softwarelizenzvereinbarung und wählen Sie dann **ZUSTIMMEN** aus. Klicken Sie auf **Weiter**.
   3. Übernehmen Sie den standardmäßigen Zielordner und klicken Sie dann auf **Weiter**.
4. Aktivieren Sie nach Abschluss der Installation das Kontrollkästchen **EVault Software Central Control starten**. Klicken Sie auf **Fertigstellen**.


## CentralControl konfigurieren

Diese Task erfolgt durch eine Reihe von Interaktionen, während Sie bei dem Server angemeldet sind, der für den EVault Backup-Service bestimmt ist.

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Starten Sie CentralControl.
3. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **MyAgent** und wählen Sie die Option **Agentenkonfiguration** aus.
4. Klicken Sie auf der Registerkarte 'Vaults' auf **Neu**. Daraufhin wird der Assistent für die Vaultkonfiguration aufgerufen. Klicken Sie auf **Weiter**.
5. Wählen Sie **Als neuer Computer registrieren** aus und klicken Sie auf **Weiter**.
6. Geben Sie im Feld für den Profilnamen den Vaultnamen ein. Der Vaultname kann im [{{site.data.keyword.slportal}}](https://control.softlayer.com/){:new_window} abgerufen werden.
6. Geben Sie die Netzadresse (IP-Adresse der zugewiesenen Vault) ein und klicken Sie anschließend auf **Hinzufügen**. Klicken Sie anschließend auf **Weiter**.
7. Geben Sie die neuen Portwerte ein, klicken Sie auf **Hinzufügen** und klicken Sie dann auf **Weiter**.
8. Geben Sie in der Anzeige 'Verbindungseinstellungen' die gewünschte Anzahl der Sekunden/Minuten ein. Behalten Sie die Auswahl des Kontrollkästchens zum **Aktivieren über die Verbindungsverschlüsselung für Übertragungen zur/von der Vault** bei. Klicken Sie auf **Weiter**.
9. Geben Sie in der Anzeige 'Authentifizierung' Ihre Berechtigungsnachweise ein und klicken Sie auf **Weiter**.
10. Im Fenster 'Registrierte Computer' wird nun der Hostname Ihres Servers angezeigt. Klicken Sie auf **Weiter**.
11.	Klicken Sie auf **Fertigstellen**, um die Konfiguration abzuschließen.


## EVault-Aufbewahrungsschemas erstellen

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Starten Sie CentralControl.
3. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **MyAgent** und wählen Sie die Option **Agentenkonfiguration** aus.
4. Klicken Sie auf die Registerkarte **Aufbewahrungen**. Klicken Sie im daraufhin aufgerufenen Aufbewahrungsassistenten auf **Weiter**.
5. Geben Sie den Aufbewahrungsnamen ein. Klicken Sie auf **Weiter**.<br/>
   **Hinweis** - Der Eintrag darf maximal 32 alphanumerische Zeichen umfassen. Die Verwendung von Leerzeichen ist nicht zulässig, Unterstreichungszeichen (`_`) und Gedankenstriche (`-`) dürfen jedoch benutzt werden.
6. Geben Sie die Anzahl der Tage für die Onlineaufbewahrung und die Anzahl der Kopien für diesen Aufbewahrungstyp ein. Klicken Sie anschließend auf **Weiter**.<br/>
   **Hinweis** - Die Kombination aus den Aufbewahrungstagen und -kopien wird verwendet, um sicherzustellen, dass die mindestens erforderliche Aufbewahrungsdauer eingehalten und eine bestimmte Anzahl von Sicherungskopien aufbewahrt wird.
7. Wählen Sie **Ich will keine Archivierungssicherungskopien erstellen** aus. Klicken Sie auf **Weiter**.
8. Klicken Sie auf **Fertigstellen**, um die Konfiguration des Aufbewahrungsschemas abzuschließen.


## EVault-Job konfigurieren

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Starten Sie CentralControl.
3. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **MyAgent** und wählen Sie die Option **Neuer Job** aus. 
4. Klicken Sie in der Eingangsanzeige auf **Weiter**.
5. Wählen Sie den Sicherungsquellentyp aus.
6. Wählen Sie für die Codierung **Unicode** aus. Klicken Sie auf **Weiter**.
7. Wählen Sie das Ziel für diesen Job aus. Klicken Sie auf **Weiter**.
8. Geben Sie den Namen für den Job und dessen Beschreibung ein.<br/>
   **Hinweis** - Der Name darf zwischen 1 und 30 Zeichen umfassen. Der Name darf Buchstaben, Ziffern, Unterstreichungszeichen (`_`), Bindestriche (`-`) sowie Dollarzeichen (`$`) enthalten.
9. Wählen Sie die Datenquellen aus. Klicken Sie auf **Hinzufügen**.
10. Geben Sie die Optionen für die Verarbeitung und den Sicherungszeitpunkt an. Aktivieren Sie die Option **Quick File Scanning** (Schnelldateisuche) und legen Sie das Sicherungszeitfenster durch eine entsprechende Stunden- oder Minutenangabe fest. Klicken Sie anschließend auf **Weiter**.
11. Wählen Sie den Verschlüsselungstyp (Standardeinstellung AES 256-Bit) aus und geben Sie Ihr Verschlüsselungskennwort ein. Klicken Sie auf **Weiter**.
12. Wählen Sie die Protokolloptionen für Ihren Job aus. Aktivieren Sie die Option **Protokolldatei erstellen** und wählen Sie dann die Option **Nur abgelaufene Protokolldateien automatisch bereinigen** aus. Klicken Sie anschließend auf **Weiter**.
13. Wählen Sie die Option zum **Beenden des Assistenten** aus und klicken Sie dann auf **Fertigstellen**, um die Konfiguration abzuschließen. Unter 'MyAgent' wird daraufhin der neue Job angezeigt.


## EVault-Job ausführen

1. Aktivieren Sie die Fernsteuerung Ihres Servers über RDP.
2. Starten Sie CentralControl.
3. Klicken Sie im Arbeitsbereich mit der rechten Maustaste auf **MyAgent** und wählen Sie dann den von Ihnen erstellten Agenten aus.
4. Klicken Sie in der Eingangsanzeige auf **Weiter**.
5. Wählen Sie das Sicherungsziel oder eine alternative Speicherposition für den Seed-Sicherungsjob (vollständige Gesamtsicherung) aus. Klicken Sie auf **Weiter**.<br/>
   *Tipp* - Weitere Informationen zur Verwendung mehrerer Vaults finden Sie unter dem Thema [Multi-Vaulting](multivaulting.html).
6. Wählen Sie die Option für das Quick File Scanning aus, um zu vermeiden, dass Dateien, die nicht geändert wurden, gelesen werden. Klicken Sie auf **Weiter**.
7. Klicken Sie auf **Fertigstellen**, um die Konfiguration abzuschließen und die Sicherung zu starten. Daraufhin wird ein Fenster mit Prozessinformationen aufgerufen, in dem der Status des Sicherungsjobs angezeigt wird. Klicken Sie nach Abschluss des Sicherungsjobs auf **Schließen**.
