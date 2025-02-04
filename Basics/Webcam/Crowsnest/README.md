# Basics - Crowsnest - Mehr Webcam FPS  
  
*Link zum Crowsnets Github:*

https://github.com/mainsail-crew/crowsnest  
  

### <u>**Crownest installieren**</u>

```
cd ~
```
```
git clone https://github.com/mainsail-crew/crowsnest.git
```
```
cd crowsnest
```
```
./install.sh
```

### <u>**Crownest deinstallieren**</u>
```
cd ~/crowsnest
```
```
./uninstall.sh
```

### <u>**Moonraker.conf anpassen**</u>
- Moonraker.conf in Mainsail öffnen
- Eintrag einfügen
```
[update_manager webcamd]
type: git_repo
path: ~/crowsnest
origin: https://github.com/mainsail-crew/crowsnest.git
```

### <u>**Camera konfigureren**</u>
- Die Konfig Datei ist folgende ~/klipper_config/webcam.conf
```
[webcamd]
log_path: ~/klipper_logs/webcamd.log
log_level: quiet

[cam 1]
streamer: ustreamer
port: 8080
device: /dev/video0
resolution: 1920x1080
max_fps: 25
```
  
*[cam 1] = Kamera zuordnung (Bitte immer nur die Zahl aufsteigend ändern)  
stream = Streamer service; ustreamer oder rtsp kann ausgewählt werden  
port = Port (Sollte sich von den anderen Webcams unterscheiden; keine Doppelbelegung)  
device = Kamera "Port" (über "v4l2-ctl --list-devices" rausfinden )  
resolution = Auflösung (1920x1080; 1280x720)  
max_fps= maximale FPS*
