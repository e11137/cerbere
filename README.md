# Cerbère

Alarme open source accessible à tous, fonctionnant localement avec des capteurs d’ouverture et de mouvement sans fil. Son nom fait référence au gardien de la mythologie grecque.

## Objectif

Permettre au plus grand nombre de s’équiper grâce à un coût accessible, une installation simple et une documentation ouverte. Le fonctionnement local et l’absence d’abonnement sont les orientations proposées pour la première version.

## État du projet

Projet en phase de conception : aucun logiciel d’alarme opérationnel n’est encore fourni.

## Capteurs retenus

| Fonction | Référence | Utilisation |
| --- | --- | --- |
| Ouverture | **SONOFF SNZB-04P** | Détection de l’ouverture des portes et fenêtres par contact magnétique. |
| Mouvement infrarouge passif (PIR) | **SONOFF SNZB-03P** | Détection de mouvement à l’intérieur, en complément des ouvertures. |

Les deux modèles communiquent en **Zigbee 3.0** et sont pris en charge par **Zigbee2MQTT**. La centrale locale et son adaptateur Zigbee restent à choisir.

La première version ne prévoit pas de capteur de choc ou de vibration. Le SNZB-04P ne détecte pas les coups ni une vitre cassée si la fenêtre reste fermée.

Les capteurs commerciaux ne sont pas eux-mêmes open source. La licence de ce dépôt couvre les contributions au projet, pas le matériel ni le micrologiciel SONOFF.

## Chats et chiens

Aucune immunité aux animaux n’a été confirmée dans la documentation consultée pour le SNZB-03P. Il ne doit donc pas être considéré comme capable de distinguer une personne d’un chat ou d’un chien.

Dans les pièces accessibles aux animaux, les PIR devront être exclus du déclenchement de l’alarme lorsque les animaux sont présents. Les capteurs d’ouverture resteront actifs. Cette configuration réduit la couverture : une entrée par une vitre cassée sans ouverture peut ne pas être détectée dans ces pièces.

Cerbère devra permettre de configurer chaque PIR selon la zone et le mode d’alarme :

- **Mode absent** : ouvertures actives et PIR actifs uniquement dans les zones sans animaux.
- **Mode présent / nuit** : ouvertures actives et PIR exclus dans les zones occupées par des personnes ou des animaux.

Ces règles sont à implémenter et à valider sur le prototype.

## Points à valider sur le prototype

- Réception des ouvertures, fermetures et mouvements, portée et fiabilité.
- Remontée de pile faible sur les deux modèles et d’alerte de manipulation sur le SNZB-04P.
- Délai entre deux détections du SNZB-03P et retour à l’état sans mouvement.
- Placement des PIR et exclusion effective des zones occupées par les animaux.
- Délai de détection d’un capteur qui ne communique plus.
- Comportement après une coupure d’alimentation ou un redémarrage.
- Appairage limité à l’installation et clé réseau propre à chaque installation.

Le chiffrement radio ne protège pas contre le brouillage. La supervision des capteurs devra faire partie de la conception.

## Prochaines étapes

1. Choisir la centrale et son adaptateur Zigbee.
2. Tester deux capteurs SONOFF SNZB-04P et un PIR SONOFF SNZB-03P.
3. Définir les états de l’alarme, les zones, les modes et les règles de déclenchement.
4. Choisir la sirène, les commandes et l’alimentation de secours.
5. Documenter l’installation, notamment les logements avec animaux, et chiffrer le kit de départ.

## Références

- [SONOFF SNZB-04P : manuel](https://support.sonoff.tech/snzb-04p-usermanual/)
- [SONOFF SNZB-04P dans Zigbee2MQTT](https://www.zigbee2mqtt.io/devices/SNZB-04P.html)
- [SONOFF SNZB-03P : présentation fabricant](https://sonoff.tech/products/sonoff-zigbee-motion-sensor-snzb-03p)
- [SONOFF SNZB-03P dans Zigbee2MQTT](https://www.zigbee2mqtt.io/devices/SNZB-03P.html)
- [Zigbee2MQTT](https://www.zigbee2mqtt.io/)

## Licence

Copyright (c) 2026 Rogelio CANEDO.

Cerbère est distribué sous la [GNU General Public License v3.0](LICENSE) (GPL-3.0-only).
