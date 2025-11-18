Tags: [
#F,
[[%Java]],
[[%Game Development]],
[[%Computer Science]]
]

# Überblick:

Erstellt ein Fenster ( JFrame ), konfiguriert es für Vollbild, fügt ein Spielpanel hinzu, zeigt das Fenster an und startet den Spiel-Thread.
## Importe

```java
package com.game;

import javax.swing.JFrame; // Hauptfenster der GUI
import java.awt.GraphicsDevice; // Vollbildmodus
import java.awt.GraphicsEnvironment; // Bildschirminformationen
```

## Main-Methode & Fenster erstellen

```Java
JFrame frame = new JFrame(); // Erstellt neues Fenster
frame.setDefaultCloseOperation(JFrame.EXIT_ON_CLOSE); // Setzt den Weg für das beenden des Spiels
frame.setResizable(false); // Fenstergröße ist fixed
frame.setTitle("2D Game"); // setzt den Titel
```

## Vollbild vorbereiten

```Java
GraphicsEnvironment ge = GraphicsEnvironment.getLocalGraphicsEnvironment();
GraphicsDevice gd = ge.getDefaultScreenDevice();
// Holt die Bildschirmumgebung und auch das aktuelle Gerät
```

## Spielpanel hinzufügen

```Java
GamePanel gamePanel = new GamePanel(); // Erstellt Instanz eines GamePanels
frame.add(gamePanel); // Fügt das Panel dem Fenster zu
```

## Window Einstellungen

```Java
frame.setLocationRelativeTo(null); // Positioniert das Fenster in der Mitte des Bildschirmes

if (gd.isFullScreenSupported()) { // Wenn Vollbild unterstütz wird
    frame.setUndecorated(true); // Entfernt Fensterrahmen
    gd.setFullScreenWindow(frame); // Aktiviert Vollbild
} else {
    frame.setExtendedState(JFrame.MAXIMIZED_BOTH); // Maximiert Fenster als Fallback
}

frame.pack(); // Passt die Fenstergröße an den Inhalt an
frame.setVisible(true); // zeigt den Screen
```

## Spiel-Thread 

```Java
gamePanel.startGameThread(); // Startet den Loop -> Endlosschleife für Updates und Rendering
```
