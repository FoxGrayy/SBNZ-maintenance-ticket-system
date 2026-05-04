# SBNZ Sistem za prioritizaciju i eskalaciju maintenance tiketa
Milica Lazić SW90/2017
## Motivacija
U sistemima za održavanje često postoji veliki broj prijavljenih problema koji zahtevaju brzu reakciju. U takvim sistemima, određivanje prioriteta je od visokog značaja. Ručno određivanje prioriteta može biti neefikasno i podložno greškama, posebno u situacijama kada se istovremeno javlja više kvarova različite važnosti. Potreban je sistem koji će na osnovu dostupnih podataka automatski proceniti ozbiljnost problema i predložiti odgovarajuću akciju.
## Ideja rešenja
Rule-based sistem koji koristi unapred definisana pravila za donošenje odluka. Sistem će na osnovu ulaznih podataka o konkretnom tiketu generisati međurezultate, kao što su hitnost i procena rizika, a nakon toga doneti konačnu odluku o prioritetu i potrebnoj akciji.
## Ulazni podaci
Sistem će koristiti informacije kao što su:
-	tip problema 
-	kritičnost opreme 
-	vreme zastoja 
-	broj prethodnih kvarova 
-	status sistema (da li je system trenutno u radu ili ne) 
-	broj prijava istog problema 
## Izlaz
Na osnovu ulaza sistem generiše:
-	nivo prioriteta tiketa 
-	preporučenu akciju (praćenje problema, planirana intervencija, hitna intervencija, eskalacija) 
## Način rada sistema
Sistem se zasniva na pravilima tipa IF–THEN. Zaključivanje će se vršiti korišćenjem forward chaining pristupa, gde se iz poznatih činjenica izvode novi zaključci kroz više nivoa rezonovanja. 
Prvi nivo - obrađuju se ulazni podaci
Drugi nivo - procenjuje se stanje sistema
Treći nivo - donosi se konačna odluka
## Primer pravila
IF criticality = high AND downtime > 60 THEN risk = high
IF risk = high AND system_running = no THEN priority = critical
IF priority = critical THEN action = escalation

