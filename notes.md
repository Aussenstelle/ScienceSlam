# Architektur
- Server (Raspi)
- Bridge (Arduino mit WLAN)
  - Voll-Dynamische Adressvergabe
  - 
- Device (Arduino)




# Kommandos
- Senden
- Update
- Adressenbelegung
  - Kommando (von Server zu Bridge (ohne MBN2)): "00000001"
  - Server fragt bridge nach belegten adressen
  - Bridge antwortet mit string von länge 255, 0 heißt kein gerät, 1 heißt belegt.
