# SMS-commando's

Ga in je telefoon instellingen naar Apps > AndroidAPS > Machtigingen en schakel SMS in.

In AndroidAPS ga naar Configurator, scroll naar kopje Algemeen en schakel SMS Commando's in. Ga via het tandwiel-icoontje naar de instellingen en voer het(de) telefoonnummer(s) in waar de SMS-commando's vandaan mogen komen. Meerdere nummers kun je scheiden door puntkomma's, gebruik nergens spaties of andere tekens (bijvoorbeeld +31612345678;+31612345679). Schakel ook 'Sta SMS commando's toe' in.

Stuur vanaf de zojuist ingevoerde telefoonnummer(s) één van onderstaande **vetgedrukte** SMS commando's naar de telefoon waar AndroidAPS opstaat. De telefoon zal bevestigen dat het commando of de statusverandering succesvol is doorgevoerd.

## BG

- Laatste BG: 5,6, Verschil:-0,2 mmol, IOB: 0,20E (Bolus: 0,10E Basaal: 0,10E)

## LOOP STOP/DISABLE

- Loop was uitgeschakeld

## LOOP START/ENABLE

- Loop was ingeschakeld

## LOOP STATUS

- Loop is uitgeschakeld
- Loop is ingeschakeld
- Gepauzeerd (10 min)

## LOOP SUSPEND 20

- Loop wordt onderbroken gedurende 20 minuten

## LOOP RESUME

- Loop hervat

## TREATMENTS REFRESH

- TERATMENTS REFRESH 1 receivers *****LET OP: hiermee haal je behandelingen op uit Nightscout. Zorg dat je de instelling "Alleen NS upload" in de Configurator bij NSClient instellingen UIT hebt staan, anders worden al je behandelingen vervangen door 'niks' en ben je ze dus kwijt! Dat is wel weer op te lossen, maar voorkomen is beter.

## NSCLIENT RESTART

- NSCLIENT RESTART 1 receivers

## DANAR / PUMP (sinds AAPS v1.60)

- Laatste Verbinding: 1 min geleden Temp: 0,00E/uur @11:38 5/30min IOB: 0,5E Reservoir: 34E Batterij: 100

## BASAL STOP/CANCEL

- Om het tijdelijke basaal te stoppen antwoord met de code EmF

## BASAL 0.3

- Om het basaal 0,3 E/uur te starten antwoord met de code Swe
- Externe basaal instelling is niet toegestaan (als externe commando's niet zijn toegestaan)

## BOLUS 1.2

- Om een bolus van 1,2 E toe te dienen antwoord met de code Rrt
- Externe bolus niet toegestaan (*niet toegestaan als je dit binnen 15 min na je laatste bolus commando stuurt, of als externe commando's niet zijn toegestaan*)

## CAL 5.6

- Om calibratie te verzenden antwoord met de code Rrt
- Kalibratie verzonden (*als xDrip is geïnstalleerd. In de xDrip+ instellingen moet je aangevinkt hebben dat kalibraties van volgers geaccepteerd worden*)