# CyberHome

![CyberHome Dashboard](https://raw.githubusercontent.com/jamerskristof-creator/CyberHome/main/Dashboard.jpg)


Aangepast Home Assistant dashboardmenu geïnspireerd door een setup die gedeeld werd in de HA-community.  
Een strak, donker, icoon-gebaseerd navigatiemenu met ruimte voor meerdere subpagina’s.

## Functies

- Donkere, futuristische uitstraling die perfect past bij een smart-home thema  
- Icoon-gebaseerd menu aan de linkerkant voor snelle navigatie  
- Ontworpen voor 16:9 dashboards (tablets, pc)

## Hoe gebruiken?

1. Open je Home Assistant dashboard.  
2. Ga naar **Dashboard bewerken** → **Ruwe configuratie bewerken**.  
3. Vervang je bestaande configuratie door de inhoud van:  
   `dashboards/cyberhome-menu.yaml`  
4. Sla op en vernieuw je dashboard.


Ik blijf deze repository updaten naarmate mijn eigen dashboard evolueert (pagina’s, extra views, theming, ...).


---

# Achtergrond toevoegen

Wil je dezelfde achtergrond gebruiken als in het CyberHome-dashboard?  
Volg deze stappen — dit is exact hoe ik het zelf heb ingesteld.

## 1. Achtergrondafbeelding uploaden

Open **Studio Code Server** of **File Editor** in Home Assistant.

1. Ga naar:
/config/www/

2. Maak een map aan (indien nog niet aanwezig):
backgrounds

3. Upload daarin jouw achtergrondbestand, bv.:
Achtergrond.png

Je bestand staat dan hier:
/config/www/backgrounds/Achtergrond.png

## 2. Thema aanpassen in CyberHome.yaml

Open nu je thema-bestand:

/config/themes/CyberHome.yaml


Voeg onderstaande regel toe (of vervang de bestaande):

```yaml

lovelace-background: "center / cover no-repeat url('/local/backgrounds/Achtergrond.png') fixed"
ha-app-layouts:
  primary-background: "center / cover no-repeat url('/local/backgrounds/Achtergrond.png') fixed !important"

```
of

```yaml

lovelace-background: 'center / cover no-repeat url("/local/backgrounds/Achtergrond.png") fixed'
card-mod-root-yaml: |
   ha-app-layout$: |
      #view {
         background: center / cover no-repeat url("/local/backgrounds/Achtergrond.png") fixed !important;
       }
```

## 3. Thema activeren
Ga naar je profiel

Browserinstellingen

Thema

Selecteer CyberHome

## 4. Browsercache vernieuwen
Gebruik een force-refresh:

Mac: Cmd + Shift + R

Windows: Ctrl + Shift + R

Eventueel Home Assistant herstarten via Instellingen → Systeem → Herstart.
