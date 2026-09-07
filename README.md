# Cerbère

Alarme open source accessible à tous, fonctionnant localement avec des capteurs d’ouverture sans fil. Son nom fait référence au gardien de la mythologie grecque.

## Objectif

Permettre au plus grand nombre de s’équiper grâce à un coût accessible, une installation simple et une documentation ouverte. Le fonctionnement local et l’absence d’abonnement sont les orientations proposées pour la première version.

## État du projet

Projet en phase de conception : aucun logiciel d’alarme opérationnel n’est encore fourni.

## Premier choix matériel

- Capteurs d’ouverture **SONOFF SNZB-04P** pour les portes et fenêtres.
- Communication **Zigbee 3.0**.
- Centrale locale avec adaptateur Zigbee et **Zigbee2MQTT** : architecture proposée, à valider.

Les capteurs commerciaux ne sont pas eux-mêmes open source. La licence de ce dépôt couvre les contributions au projet, pas le matériel ni le micrologiciel SONOFF.

## Points à valider sur le prototype

- Réception des ouvertures et fermetures, portée et fiabilité.
- Remontée de pile faible et d’alerte de manipulation.
- Délai de détection d’un capteur qui ne communique plus.
- Comportement après une coupure d’alimentation ou un redémarrage.
- Appairage limité à l’installation et clé réseau propre à chaque installation.

Le chiffrement radio ne protège pas contre le brouillage. La supervision des capteurs devra faire partie de la conception.

## Prochaines étapes

1. Choisir la centrale et son adaptateur Zigbee.
2. Tester deux capteurs SONOFF SNZB-04P.
3. Définir les états de l’alarme et les règles de déclenchement.
4. Choisir la sirène, les commandes et l’alimentation de secours.
5. Documenter l’installation et chiffrer le kit de départ.

## Références

- [SONOFF SNZB-04P : manuel](https://support.sonoff.tech/snzb-04p-usermanual/)
- [Intégration du capteur dans Zigbee2MQTT](https://www.zigbee2mqtt.io/devices/SNZB-04P.html)
- [Zigbee2MQTT](https://www.zigbee2mqtt.io/)

## Licence

[MIT](LICENSE).
