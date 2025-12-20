Tags: [
#F,
[[%Java]],
[[%Game Development]],
[[%Computer Science]]
]

# Überblick:

>- Speicher Position und Größe des Spielers
>- Reagiert auf Tasteneingaben
>- Zeichnet den Spieler auf dem Bildschirm relativ zur Kamera

## Importe

```Java
package com.game; // Klasse gehört zum Paket "com.game"
import java.awt.Color; // für das Zeichnen verwendet
import java.awt.Graphics;
```

## Variablen

```Java
GamePanel gp; // Referent auf das GamePanel für Größen
KeyHandler keyH; // Referenz auf die Eingabesteuerung 

public int worldX, worldY, speed; // Position des Spielers in derW Welt NICHT BILDSCHIRM und Speed
public int width, height; // Größe des Spielers 
```

## Konstruktor

```Java
public Player(GamePanel gp, KeyHandler keyH) {
    this.gp = gp;
    this.keyH = keyH;
    
    worldX = 10 * gp.tileSize; // Startposition
    worldY = 10 * gp.tileSize;
    
    speed = 2; // Geschwindigkeit
    width = gp.tileSize; // Größe auf eine Tile
    height = gp.tileSize;
}
```

## Update-Methode

```Java
public void update() { // Holt Infos von KeyHandler und bewegt, abhängig von gedrückten Tasten
    if (keyH.upPressed) worldY -= speed;
    if (keyH.downPressed) worldY += speed;
    if (keyH.leftPressed) worldX -= speed;
    if (keyH.rightPressed) worldX += speed;
}
```

## Draw-Methode

```Java
public void draw(Graphics g) {

int screenX = worldX - gp.camera.worldX + gp.screenWidth / 2;
int screenY = worldY - gp.camera.worldY + gp.screenHeight / 2;

// Berechnet die Position des Spieler in Relation zur Kamera

if (worldX + gp.tileSize > gp.camera.worldX - gp.screenWidth / 2 &&
    worldX - gp.tileSize < gp.camera.worldX + gp.screenWidth / 2 &&
    worldY + gp.tileSize > gp.camera.worldY - gp.screenHeight / 2 &&
    worldY - gp.tileSize < gp.camera.worldY + gp.screenHeight / 2) 
    
// Prüft ob der Spieler innerhalb des sichtbaren Bereiches liegt

{

	g.setColor(Color.WHITE);
    g.fillRect(screenX, screenY, width, height); // Zeichnet den Player
    g.setColor(Color.BLACK);
    g.fillRect(screenX + 4, screenY + 4, 3, 3);
    g.fillRect(screenX + 9, screenY + 4, 3, 3); // Zeichnet Augen als Detail
    }
}
```
