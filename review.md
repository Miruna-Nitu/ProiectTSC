** 1. General 
-- CAD ERC FAIL: Exista o eroare critica si 73 warninguri:
	- Eroarea "Segment of net GND has fallen apart": la firul ce pleaca din pinul B1 de la componenta RT6160AWSC de la DC/DC (verifica numele netului sau daca ai 2 fire care se suprapun acolo)
	- Warning-uri "Close but unconnected": traseele par conectate vizual, dar Fusion nu le vede electric, deci trebuie refacute din conexiuni.
-- Schematic Symbols FAIL: la microcontroller-ul nRF52840, ai uitat sa pui atributele NAME si VALUE ca in schematicul model

** 2.Power Supply
-- Decoupling present for all ICs FAIL: ai warninguri de tip POWER pin connected to N$xx la nRF52840, deci probabil ca pinii de alimentare (DEC1, DEC4) nu sunt legati la retele cu nume clare (again problema cu numele componentelor)

** 3. Signals
-- Numerotare incompleta: in sheet-ul cu e-paper driver, numerotarea elementelor nu respecta modelul (ex: diodele si tranzistorul Q1)

** 4. Debugging
-- Test points on interesting signals: INCOMPLET - test pad-urile trebuie sa fie clar marcate in silkscreen cu numele semnalelor (ex: SDA, SCL, GND), dar la Fuel Gauge nu ai pus numele care trebuie

* era doar schematicul facut, fara pcb.