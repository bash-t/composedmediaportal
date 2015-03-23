Grundsätzlicher Aufbau:
Alle Dokumente innerhalb der DB werden über den key "docClass" kategorisiert. Dies soll die oberste Strukturebene sein.

# Klasse: DownloadRequest #
So ein Dokument wird von dem Request des Bookmarklets erzeugt und enthält hauptsächlich die URL der Seite, auf der das herunterzuladende Medium sich befindet.

### JSON Objekt ###

```
{
   "_id": "123",
   "docClass": "downloadRequest",
   "submitter": "bp", //wird im Bookmarklet konfiguriert.
   "url": "http://www.youtube.com/watch?v=eY2_EPG-zWY&feature=grec_index"
}
```



# Klasse: Media #
Dieses Dokument enthält als Attachment das eigentliche Medium sowie ein Script zur Anweisung, wie dieses Medium angezeigt und abgespielt werden soll.

### JSON Objekt ###

```
{
   "_id": "456",
   "docClass": "media",
   "mediaType": "flv",                        //evtl. überflüssig
   "mediaSource": "youtube",
   "submitter": [                             //jeder der das gleiche mediadoc angefordert hat wird hier aufgeführt. Somit könnte man nur seine eigenen Medias filtern.
       "bp",
       "skl"
   ],
   "mediaTitle": "ZBrush 4 - Alpha Roll (Custom Brushes)",
   "mediaLength": 155,                        //Länge in Sekunden
   "mediaSize": 2500,                         //Größe in KB
   "mediaSizeAudio": 1000,                    //Größe der Audiodatei (falls vorhanden)
   "audioAvailable": true,                    //konnte aus dem Video der Ton extrahiert werden?
   "mediaTags": [
       "ZBrush",
       "ZBrush 4",
       "3D Sculpting",
       "3D videos",
       "ZBrush tutorial",
       "Alpha Roll",
       "Custom Brushes"
   ],
   "_attachment": [
       "movie.flv",
       "audio.mp3"
   ]
}
```


# Klasse: ... #
Weitere Dokumentenklassen für URL Worker etc....

### JSON Objekt ###