# Accu-Chek Insight pomp

**Deze software is onderdeel van een doe-het-zelf oplossing en is geen kant-en-klaar product, maar vraagt JOU te lezen, leren en te begrijpen hoe het systeem werkt en hoe je het kunt gebruiken. Het neemt niet je gehele diabetes management van je over, maar stelt je wel in staat om je diabetes beter onder controle te krijgen en je kwaliteit van leven te verhogen, als je bereid bent de benodigde tijd erin te investeren. Haast je niet, maar geef jezelf de tijd om te leren. Jij alleen bent verantwoordelijk voor wat je ermee doet.**

* * *

## ***WAARSCHUWING:** Als je de Insight al gebruikte met **SightRemote** in het verleden, gelieve **bij te werken naar versie 2.1.1** en **SightRemote te verwijderen**.*

## Benodigde hardware en software

- Een Roche Accu-Chek Insight pomp (firmware maakt niet uit, ze werken allemaal) <br />Opmerking: AAPS zal alleen het **eerste basaal-profiel van de pomp** gebruiken.
- Een Android telefoon
- De AndroidAPS-app (versie 2.1.1 of hoger) geïnstalleerd op jouw telefoon

## Pomp koppelen

-     In [Configurator](../Configuratie/Config-Builder) van de AndroidAPS app: selecteer Accu-Chek Insight onder het Pomp kopje
     
      ![Screenshot of Config Builder Insight](../../images/Insight_ConfigBuilder.png)
     

-     Tik op het tandwiel-icoon naast Insight om de instellingen te openen.
     

-     In de instellingen: tik op de knop 'Insight koppelen' bovenaan het scherm. Als het goed is zie je nu een lijst van alle nabijgelegen bluetooth apparaten (links onder).
     
 
 -     Op de Insight pump, ga naar menu > Instellingen > Communicatie > Apparaat toevoegen. De pomp zal het volgende scherm (rechts onder) weergeven met het serienummer van de pomp.
      
      ![Screenshot of Insight Pairing 1](../../images/Insight_Pairing1.png)
      

-     Ga terug naar je telefoon, tik op het pomp serienummer in de lijst van bluetooth apparaten. Tik vervolgens op Koppelen om te bevestigen. 
     
      ![Screenshot of Insight Pairing 2](../../images/Insight_Pairing2.png)
     

-     Both the pump and phone will then display a code. Controleer of de codes op beide apparaten hetzelfde zijn en bevestig zowel de pomp als de telefoon.
     
      ![Screenshot of Insight Pairing 3](../../images/Insight_Pairing3.png)
     

-     Succes! Geef jezelf een schouderklopje voor het succesvol koppelen van je pomp met AndroidAPS.
     
      ![Screenshot of Insight Pairing 4](../../images/Insight_Pairing4.png)
     

-     Om te controleren of alles goed is, ga je terug naar de Configurator in AndroidAPS en tik op het tandwiel-icoontje bij de Insight pomp om in de Insight-instellingen te komen. Tik vervolgens op Insight Pairing en je zult wat informatie te zien krijgen over de pomp:
     
      ![Screenshot van Insight Pairing Informatie](/../images/Insight_PairingInformation.png)
     

Opmerking: Er zal geen permanente verbinding zijn tussen pomp en telefoon. Een verbinding zal alleen tot stand worden gebracht als dat nodig is (d.w.z. instellen van tijdelijke basaalstand, bolus geven, pomp geschiedenis uitlezen...). Anders zouden de batterij van telefoon en pomp te snel leeglopen.

## Instellingen in AAPS

      ![Screenshot of Insight Settings](../images/Insight_pairing.png)
    

In de Insight-instellingen in AndroidAPS kun je de volgende opties inschakelen:

- "Infuuswissel noteren": Dit zal automatisch een insuline ampul wissel noteren in AndroidAPS wanneer je het "vul canule" programma op de pomp gebruikt.  
 <font color="red">Opmerking: Een canule wissel reset ook Autosens</b></font>
- "Slangwissel noteren": Dit voegt een notitie toe aan de AndroidAPS database wanneer je het "infusieset vullen" programma op de pomp gebruikt.
- "Batterijwissel noteren": Dit voegt een notitie toe aan AndroidAPS wanneer je een nieuwe batterij in de pomp plaatst.
- "Werkingsmodus-wissel noteren": Hiermee voegt je een notitie toe in de AndroidAPS database wanneer je de pomp start, stopt of pauzeert.
- "Alarm noteren": Dit maakt een notitie in AndroidAPS wanneer de pomp een alarm geeft (behalve herinneringen, bolus en tijdelijke basaalstand annulering - deze worden niet geregistreerd).
- "TBR-emulatie inschakelen": De Insight pump kan alleen tijdelijke basaalstanden (TBRs) instellen tot maximaal 250%. To get round this restriction, TBR emulation will instruct the pump to deliver an extended bolus for the extra insulin if you request a TBR of more than 250%.  
 <font color="red">Note: Just use one extended bolus at a time as multiple extended boluses at the same time might cause errors.</font>
-     "Herstel duur": Dit definieert hoe lang AndroidAPS zal wachten na een mislukte verbindingspoging voordat hij het opnieuw probeert. Je kunt kiezen van 0 tot 20 seconden. Als je verbindingsproblemen ondervindt, kies je een langere wachttijd. 
       <br><br>Voorbeeld voor min. herstel duur = 5 en max. herstel duur = 20
       <br><br>geen verbinding -> wacht <b>5</b> sec.
         <br> probeer opnieuw -> geen verbinding -> wacht <b>6</b> sec.
         <br> probeer opnieuw -> geen verbinding -> wacht <b>7</b> sec.
         <br> probeer opnieuw -> geen verbinding -> wacht <b>8</b> sec.
         <br>...
         <br> probeer opnieuw -> geen verbinding -> wacht <b>20</b> sec.
         <br> probeer opnieuw -> geen verbinding -> wacht <b>20</b> sec.
         <br>...
     

-     "Verbindingsvertraging ": Dit bepaalt hoe lang (in seconden) AndroidAPS zal wachten met het verbreken van de pomp nadat een opdracht is uitgevoerd. Standaard waarde is 5 seconden.
     

Voor perioden waarin de pomp gestopt is geweest, zal AAPS een tijdelijke basaalstand noteren van 0%.

In AndroidAPS toont het Accu-Chek Insight tabblad de huidige status van de pomp. Er zijn hier twee knoppen:

- "Vernieuw": Vernieuwt de pomp status
-     "Activeer/deactiveer melding van TBR einde": Een Insight pomp is standaard ingesteld om een alarm af te geven wanneer een TBR (tijdelijke basaalstand) eindigt. Met deze knop kun je dit alarm activeren of deactiveren zonder dat je hiervoor speciale Accucheck configuratie-software nodig hebt.
     
      ![Screenshot of Insight Status](../../images/Insight_Status2.png)
     

## Instellingen in de pomp

Configureer alarmen in de pomp als volgt:

- Menu > Instellingen > Apparaat-instellingen > Instellingen modus > Zacht > Signaal > Geluid Menu > Instellingen > Apparaatinstellingen > Instellingen modus > Zacht > Volume > 0 (verwijder alle balken)
- Menu > Modi > Signaalmodus > Zacht

Met deze instellingen gaan alle alarmen vanuit de pomp af in stilte. AndroidAPS krijgt de alarmen wel binnen, en beslist vervolgens of een alarm relevant voor jou is. Niet-relevante alarmen worden bevestigd in de pomp door AndroidAPS, hiervan zul jij dus niks merken. Wel-relevante alarmen worden door AndroidAPS niet bevestigd, waarna het volume van het alarm zal toenemen (eerst piepen, dan trillen) en jij als gebruiker het alarm moet bevestigen.

Insight pumps with newer firmware will vibrate briefly every time a bolus is delivered (for example, when AndroidAPS issues an SMB or TBR emulation delivers an extended bolus). Dit trilalarm kan niet worden uitgeschakeld. Oudere pompen trillen in deze omstandigheden niet.

## Batterij vervangen

De Insight pomp heeft een kleine interne batterij om essentiële functies zoals de interne klok, te kunnen laten doorgaan terwijl jij de batterij verwisselt. Als het wisselen van de batterij te lang duurt, kan deze interne batterij leegraken. Dan wordt de interne klok gereset en wordt je gevraagd een nieuwe tijd en datum in te voeren nadat je een nieuwe batterij in de pomp hebt gedaan. Als dit gebeurt, zullen alle behandelingen in AndroidAPS voorafgaand aan de batterijwissel niet meer in berekeningen (zoals COB, IOB) worden opgenomen, omdat de juiste tijd niet kan worden vastgesteld.

## Insight specifieke foutmeldingen

### Extended bolus

Just use one extended bolus at a time as multiple extended boluses at the same time might cause errors.

### Time out

Sometimes it might happen that the Insight pump does not answer during connection setup. In this case AAPS will display the following message: "Timeout during handshake - reset bluetooth".

![Insight Reset Bluetooth](../images/Insight_ResetBT.png)

In this case turn off bluetooth on pump AND smartphone for about 10 seconds and then turn it back on.

## Wisselen van tijdzone met de Insight

For information on traveling accross time zones see section [Timezone traveling with pumps](../Usage/Timezone-traveling#insight).