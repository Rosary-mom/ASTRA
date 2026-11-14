# Archiv-Plan ASTRA – „Goldenes Zeitalter“

Ziel: Jede Sequenz samt Tonspuren und Zeitmarken ist später wiederauffindbar (Starring, Outtakes, Gesamtfilm).

## Ordner je Folge
```
folgen/folge-NN/
  folge-NN-final.mp4          fertige, freigegebene Folge
  INDEX.csv                   eine Zeile je Datei (siehe unten)
  szenen/SSS/                 eine Szene (Nummer aus szenenliste.csv)
    bild/  SSS-EEE-tTT.mp4    Einstellung EEE, Take TT (t01 = genommen)
    takes/ SSS-EEE-tTT.mp4    verworfene Takes (Outtakes)
    ton/   SSS-stimme-<rolle>.wav | SSS-musik.wav | SSS-chor.wav | SSS-sfx.wav
    zeitmarken.txt            Sprechereinsätze/Synchronpunkte (Sekunden relativ zur Szene)
```
Dateien über 100 MB (GitHub-Grenze) liegen im Kaggle-Datensatz `uwerosenkranz/video2` unter gleichem Pfad; INDEX.csv vermerkt dann `ablage=kaggle`.

## INDEX.csv – Spalten
`datei, folge, szene, einstellung, take, art (bild|stimme|musik|chor|sfx|zeitmarken), rolle/figur (Alias), start_in_folge_s, ende_in_folge_s, dauer_s, status (genommen|outtake), quelle (Kaggle/Wan2.2-5B | Fidelio), lizenz, ablage (github|kaggle)`

`start_in_folge_s`/`ende_in_folge_s` = Zeitspur im fertigen Schnitt, damit jede Sequenz im Film wiedergefunden werden kann.

## Tags für spätere Schnitte
In INDEX.csv optional `tags`: `starring:<Alias>`, `outtake:lustig`, `trailer`, `intro`.
