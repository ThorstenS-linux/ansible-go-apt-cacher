# ansible-go-apt-cacher
installs go-apt-cacher on debian

## ToDos
Folgendes muss die Rolle erledigen:
 * ✔ Benutzer/Gruppe apt-cacher-ng einrichten
 * ✔ systemd-unit anlegen (erst ab ansible 2.2 gibt es ein systemd modul!)
 * ✔ Konfigurationsdatei mit debian-Backend unter /etc/go-apt-cacher.toml legen
 * ✔ Vorlage für die unit: https://github.com/Efreak/apt-cacher-ng/blob/master/systemd/apt-cacher-ng.service
 * ⚡ avahi-service anlegen - macht das Sinn?
 * ♡ Entweder das aktuelle binary richtig herunterladen (nach TAG), oder auf einem Rechner
   mit go Umgebung selbst kompilieren. Hier ist ein wget für das TAG 1.2.2
   wget https://github.com/cybozu-go/aptutil/releases/download/v1.2.2/go-apt-cacher_v1.2.2_linux_amd64.tgz
 * Die möglichen Variablen für die service-unit auslösen und als template
   umsetzen. Das ermöglicht schnell das Anpassen des Loglevels oder des
   Formats. go-apt-cacher --help zeigt die möglichen Parameter
 * Die config go-apt-cacher.toml in ein template umbauen. Mögliche Anpassungen
  * neben dem Ubuntu Backend das debian Backend einbauen für httpredir, security und backports.
  * die Cache Größe  variabel gestalten
  * den Cache Ordner variabel gestalten

## URLs
Blogpost: http://ymmt2005.hatenablog.com/entry/2016/07/19/Introducing_go-apt-cacher_and_go-apt-mirror

## Abhängige Rollen
Es wäre sehr sinnvoll eine Rolle für die sources.list zu haben, die mit diesem Backend umgehen kann.
Hiermit wäre zumindest der Host hier selbst umstellbar:
http://docs.ansible.com/ansible/apt_repository_module.html

## ToDo
