
# WireGuard deployment with Ansible and Docker-Compose

>Syncthing is a continuous file synchronization program. It synchronizes files between two or more computers in real time, safely protected from prying eyes. Your data is your data alone and you deserve to choose where it is stored, whether it is shared with some third party, and how it's transmitted over the internet.

## Tested with: 

| Environment | Application | Version  |
| ----------------- |-----------|---------|
| macOS Monterey 12.1 | Ansible | v2.11.6 |

## Prerequisites. 

#### Install [sshpass](https://linux.die.net/man/1/sshpass) and [Ansible](https://www.ansible.com/).

Ubuntu:
```bash
sudo apt-get install sshpass && sudo apt-get install ansible -y
```

macOS:
```bash
# Ansible:
CFLAGS=-Qunused-arguments CPPFLAGS=-Qunused-arguments pip install --user ansible

# sshpass
brew install hudochenkov/sshpass/sshpass
```
 -

 ## Deployment How-To:

1. Clone this repository to your local machine.
2. cd into the project folder.
3. Edit vars.yml adding your server IP and User.
4. Edit the docker-compose file according to your needs.

    | Environment Variables | Function | Note  |
    | ----------------- |-----------|---------|
    | PUID=1000 | for UserID | use the "id" command on your docker host to get it |
    | PGID=1000 | for GroupID | use the "id" command on your docker host to get it |
    | TZ=America/Argentina/Buenos_Aires | Specify a timezone to use | [List of Linux TZ time zones](https://en.wikipedia.org/wiki/List_of_tz_database_time_zones) |

5. Make install.sh executable. 
    ```bash
    chmod +x install.sh
    ```
6. Run it.
    ```bash
    ./install.sh
    ```

## Debugging / Troubleshooting:



## Author:

- [@JManzur](https://jmanzur.com.ar)

## Documentation:

- [WireGuard official website](https://www.wireguard.com/)
- [Syncthing container documentation on linuxserver.io](https://docs.linuxserver.io/images/docker-syncthing)
