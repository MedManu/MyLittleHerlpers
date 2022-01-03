#  TIM:

##ssh Verbindung:

- ssh pi@10.0.0.2

### config ändern:

- /etc/pwnagotchi/config.toml

### log checken:

- tail -f /var/log/pwnagotchi.log

### checken ob er läuft:

- systemctl status pwnagotchi

### Restart(geht in Menu):

- systemctl restart pwnagotchi

### Zurück in AUto bringen:

- touch /root/.pwnagotchi-auto && systemctl restart pwnagotchi

### file anschauen:

- cat config.toml

###file öffnen:

- sudo nano config.toml