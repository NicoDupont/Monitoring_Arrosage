## Monitoring du circuit d'eau d'arrosage

# Montage réalisé sur une protoboard. un pcb dédié sera réalisé

Montage à base d'esp32 utilisé principalement pour monitorer le circuit d'arrosage.  

- pression
- temperature
- debitmetre/volume
- Ouverture/fermeture vanne motorisée  

### Fonctionnement :

Collecte des données.  
Les données remontent dans home-assistant via esphome.  
 => automatisme dans home-assistant   

### Liste des composants :

- 1x esp32 avec antenne wifi externe soudée sur connecteur sma (pas d'esp32u sous la main)
- 8x relais 5v (2x4) (alimente en 5v, logique en 3.3v)
- 1x alim 12v2A
- 1x convertisseur dc 12v=>5v
- 1x convertisseur dc 5v=>3.3v (ams1117)
- 2x BME280 (3.3v)
- 2x DS18B20 (3.3v)
- 1x resistance 4.7 Kohm
- 4x résistance 10 kohm
- 1x PCF8575 (3.3v)
- 1x ADS1115 (5v) + 1x level shifter (i2c 5v<=>3.3v)
- 3x Vannes motorisées 1" 12vdc avec retour d'info position (12v,cr702,bsp,manuel+indicateur) [vanne](https://fr.aliexpress.com/item/32960203891.html?spm=a2g0o.order_list.order_list_main.298.31bd5e5b6e3TMk&gatewayAdapt=glo2fra)
- 3x Capteur pression 0.5/4.5v 0-100psi (5v) [pression](https://www.amazon.fr/gp/product/B08ZDLYKFH/ref=ox_sc_saved_image_1?smid=A1KGD9U4C0ZGWS&psc=1)
- 2 débimetres 1.5" YF-DN40 0-150L (5v) [debimetre](https://fr.aliexpress.com/item/1005003177939542.html?spm=a2g0o.order_list.order_list_main.886.7a7b5e5b7BWxKA&gatewayAdapt=glo2fra)
- Pcb, Bornier, Connecteur, entretoise, cavalier, support,Fusible, Porte Fusible, etc... 

### Cablage :

![links](https://github.com/NicoDupont/Monitoring_Arrosage/blob/main/doc/fritzing.png)

### Montage :

![board](https://github.com/NicoDupont/Monitoring_Arrosage/blob/main/doc/box.png)

### HomeAssistant :

#### Esphome :

[yaml](https://github.com/NicoDupont/Monitoring_Arrosage/blob/main/esp-vs-arrosage.yaml)

#### Entités :

![links](https://github.com/NicoDupont/Monitoring_Arrosage/blob/main/doc/entite1.png)
![links](https://github.com/NicoDupont/Monitoring_Arrosage/blob/main/doc/entite2.png)
