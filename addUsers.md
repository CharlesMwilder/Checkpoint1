```bash
#!/bin/bash

#vérification des arguments
if [ $# -eq 0 ]; then
    echo "Il manque les noms d'utilisateurs en argument - Finito"
    exit 1
fi

#vérification des noms d'user
for users in "$@"; do
    if grep -q "$users" /etc/passwd; then
        echo "L'utilisateur $users existe déjà"
    else
        #vérification de création
        if useradd "$users"; then
            echo "L'utilisateur $users a été crée"
        else
            echo "Erreur à la création de l'utilisateur $users "
        fi
    fi
done
```

![Checkpoint1-SRVDEBIAN  Running  - Oracle VirtualBox 25_10_2024 11_54_17](https://github.com/user-attachments/assets/66ccda62-4860-4614-b7a1-4d2d54f4ca40)


![Checkpoint1-SRVDEBIAN  Running  - Oracle VirtualBox 25_10_2024 11_39_56](https://github.com/user-attachments/assets/67806cc2-c9e4-418b-8f3a-a9d17c5082da)

