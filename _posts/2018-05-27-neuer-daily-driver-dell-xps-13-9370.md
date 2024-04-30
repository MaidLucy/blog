---
layout: post
title: Neuer "Daily Driver" - Dell XPS 13 9370
date: Sun, 27 May 2018 18:08:28 -0000
description: 
...

{% include wordpress-notice.html %}

## Endlich ein richtiger Laptop

Wie dem Titel dieses Posts leicht zu entnehmen ist, geht es hier um den Dell XPS 13. 
Genauer gesagt, warum genau dieses Modell und um eine kleine Panne seitens Dell.

## Ja, warum denn genau der?

Angefangen hat es eigentlich damit, dass jemand in meiner Klasse sich einen nigelnagelneuen Dell XPS 15 geholt hat 
— mit fast voller Ausstattung — und ich mich dann immer mehr mit Laptops beschäftigt habe. 
Ich wollte sowieso schon länger einen Laptop kaufen, einfach weil mir klar war, dass ich für die Uni später einen brauchen werde.
Ich wollte auch einfach mal ein Gerät haben, das ich überall mit hin nehmen kann und mit dem ich alles machen kann, was ich brauche.

Dabei hab ich drauf geachtet, dass ich ein Modell kaufe, das auf der einen Seite genug Performance für meine Ansprüche hat und auf der Anderen einen **dicken** Akku.
Wäre ja doof, wenn man die ganze Zeit an die nächste Steckdose gebunden wäre.
Wichtig war auch, dass der Laptop eine gute Kompatibilität mit Linux hat, denn mit Windows hab ich schon lange abgeschlossen. 
Und nachdem dann dieser Jemand aus meiner Klasse sich den großen angeschafft hat, konnte ich nicht widerstehen
und hab dann auch festgestellt, dass es durchaus Sinn machen würde, den Laptop früher zu kaufen, als eigentlich geplant. 
Geplant war nämlich, dass ich mir einen Laptop für die Schule zu meinem 18. Geburtstag kaufe, mit dem ich dann in der Schule mitschreiben kann,
sodass ich für die Universität schon geübt und gerüstet bin.
„Ja und warum nicht gleich dieses Schuljahr kaufen und für die Oberstufe verwenden?“, war der Gedanke. 

Noch ein kleines Nebenargument war, dass das Gerät Thunderbolt 3 hat, sodass ich spätere Erweiterungen leicht durchführen kann.
Traum-Setup wäre zum Beispiel, nur diesen Laptop zu haben und dann einfach eine eGPU anzuschließen
und dass ich damit meine komplette vorhandene Peripherie am Schreibtisch mit einem Kabel mit dem Laptop verbinden kann.

## Die Geschichte vom Ersten Tag

Endlich gekauft, sollte er an einem Freitag kommen, gekommen ist er dann am Dienstag vor diesem Freitag, einsatzbereit war es allerdings erst wieder so richtig am Freitag. Dazu gleich mehr.
Ich hab mich also riesig gefreut, dass endlich mein neuer Laptop, den ich für die nächsten paar Jahre haben werde, angekommen ist.
Ausgepackt, im Lieferumfang war nur ein USB-C zu USB 3.1 Kabel und ein USB-C Ladekabel und bisschen Papier Kram.
Sehr Minimalistisch, aber kennt man ja so heutzutage. 
Vorab, ich hatte schon einen Plan, was mit dem neuen Laptop dann gemacht wird, der sah folgendermaßen aus:

- Windows einrichten
- BIOS-Update machen
- Windows auf externe Festplatte kopieren
- Interne NVME-SSD löschen
- Manjaro Linux *(aka Arch-Installer)* installieren

Nun, an jenem besagten, erfreuten Dienstag konnte ich gerade mal einen der fünf eigentlich echt einfachen Punkte abarbeiten.

### Die Panne

Da hatte ich also das BIOS-Update hinter mir, war wieder in Windows, wollte die Installation von Manjaro Linux anfangen.
Um jedoch ein Windows fremdes Betriebssystem auf einem von diesen neuartigen Laptops zu booten, muss man im UEFI-BIOS einige Änderungen vornehmen.
Nämlich einmal die Secure-Boot-Optionen ausschalten und alle Keys löschen und Thunderbolt-Boot anschalten, sofern man von nicht nur einem der drei USB-C Anschlüsse booten möchte.
Hab ich also alle besagen Änderungen im BIOS durchgeführt und den Laptop neugestartet, wurde ich von Windows aufgefordert,
den Bitlocker Schlüssel einzugeben, dass es die Bitlocker Partition wieder entschlüsseln kann. Und noch während ich den Schlüssel auf dem Handy rausgesucht habe, ging der Laptop einfach aus.
Ohne Vorwarnung, ohne Gemuckse, ohne nichts, einfach aus.
„Wird wohl ins Standby gegangen sein oder so.“, hab ich mir gedacht.
„Vielleicht ist er ja auch ganz abgestürtzt oder so.“, hab ich mir gesagt,
während ich mit allen möglichen Versuchen probiert hab, das blöde Teil wieder anzubekommen.
Aber nichts. Einfach nichts. Abstürzen lassen, wieder anmachen, nichts. Nichts ging mehr!

Total entsetzt, aber trotzdem ruhig ist mir aufgefallen, dass die Lade-Status anzeige ein komisches Muster blinkt.
`zweimal Orange, einmal Weiß` Und wenn man auf der Dell-Support Seite nachschaut, was das bedeutet, stellt sich heraus,
dass es sich hier um einen Fehlercode handelt.
Und `zweimal Orange, einmal Weiß` bedeutet „CPU-Fehler“.
„Witzig.“, dachte ich mir, „sehr sehr witzig …“
Das kann ja wohl nicht sein, dass der Laptop gleich am ersten Tag nach — ohne Witz — zwei Stunden an Benutzung einfach so kaputt geht.

### Kontakt mit dem Support

Weitere Zehn Minuten vergingen, in denen ich vesuchte, das irgendwie selbst zu retten.
Aber ohne Erfolg.
Also habe ich ein Support Ticket beim Dell Support aufgemacht und mein Problem geschildert.
Weil ich aber sehr ungeduldig war, *(hab mich auch oft genug verschrieben gehabt beim Tippen von der Nachricht)*
habe ich dann nach einer guten Stunde direkt beim Support angerufen.
Nach ein paar Leuten und Blechboxen, die mich gefragt haben, was ungefähr mein Problem sei und mich mit meiner Support und Ticket Nummer identifiziert haben,
hatte ich letzen Endes einen Typen an der Leitung, der mit mir eine Fehleranalyse durchgegangen ist und mir am Ende drei Optionen peräsentiert hat:

1. Zurückgeben, das Geräte war ja nur 5 Tage *(geht vom Kaufdatum aus)* alt und ich hätte die 14-Tägige Frist in Anspruch nehmen können
2. Einschicken, ist ja offensichtlich ein Garantie Fall
3. Ein Techniker kommt und repariert das Gerät vor Ort mit passendem Ersatzteil, weil Premium Support

Erstens: najaaa, dauert dann wahrscheinlich ewig und ist sehr kompliziert.

Zweitens: „Das dauert zwei bis drei Wochen“, oh nein.

Drittens: Da war ich selbst überrascht, dass dieser Laptop premium Support hat und dass es so was überhaupt für Privatkunden gibt.
Aber da scheint Dell den guten Ruf für deren Support wohl zu halten.
Nicht mal Apple bringt so was.
Aber die machen ja zur Zeit sowieso nur Blödsinn in der Richtung meiner Meinung nach.
<a href="https://www.youtube.com/watch?v=9-NU7yOSElE">Siehe hier</a> und <a href="https://www.youtube.com/watch?v=MG_NRcy5mxU">hier</a>.
Also kurzum hab ich natürlich die dritte Variante genommen.
Ausgemacht wurde dann, dass der Techniker möglichst früh und egal zu welcher Zeit kommen kann, da ich Ferien habe/hatte.

## Die Reparatur

Am Tag darauf war eine E-Mail gekommen, in der ein Termin für den Support aufgeführt war: Donnerstag Vormittag.
Also das schonmal echt flott und schnell, kann man nichts sagen.
Am Donnerstag vormittag entdeckte ich dann einen verpassten Anruf um viertel vor 9 von einer meinem Handy unbekannten Nummer.
Zurückgerufen stellte sich heraus, dass dies, wie zu erwarten, der Techniker von Dell war.
Er teile mir mit, dass er heute viel zu viele Aufträge hat und darum meinen leider ausfallen lassen muss, da er es sonst zeitlich nicht schafft.
Okay, kann man wohl nichts machen.
Haben dann gleich für den nächsten Tag den eigentlichen Termin ausgemacht.
Hier kann man aber sagen, dass es sich offensichtlich um einen Denkfehler des Delll Supports handelt, dort muss wahrscheinlich viel automatisiert ablaufen,
um so viele Kunden überhaupt betreuen zu können
und außerdem sagte der Mann am Telefon vom Support auch, dass er erstmal anrufen würde.
Insofern war also alles nach Plan. 

Am Freitag, dem Tag, an dem der Laptop ja eigentlich erst kommen sollte, bin ich gegen 7 Uhr wach geworden, weil ich einfach zu aufgeregt war.
Um 8 hab ich dann von mir aus dem Techniker angerufen und gefragt, wann er kommen könne.
Er sagte dann, dass er heute auch einige Aufträge hat und so erst gegen Nachmittag kommen kann, er würde anrufen, wenn er beim Kunden vor mir losfährt.
Also hab ich mich wieder hingelegt und weiter geschlafen.
Gegen 3 kam dann ein Anruf, er würde jetzt losfahren und sei in 10 Minuten da.
Da hab ich mich ziemlich gefreut und schon mal einen Tisch hergerichtet, der genug Platz für seine Operation bietet. 

Während der Aktion haben wir uns unterhalten, denn ich hab mich einfach neben ihn gesetzt und zugeschaut, was er da macht, weil es mich natürich interessiert
und ich sowieso nichts bessere zu tun hatte.
Während der Unterhaltung hat sich dann rausgestellt, dass das ein ähnlicher Freak wie ich ist, der auch gern an Computern rumbastelt,
aber sich nicht so sehr für Software interessiert, wie ich.
War auf jeden Fall eine interessante und spannende Sache, das alles.
Er hat mir dann noch den Gefallen getan, für das BIOS-Update dazubleiben und den Part mit dabei zu sein, wo Windows den Bitlocker-Key abfragt.
Dieses Mal gab es keinen plötzlichen Absturz oder Ähnliches.

## Inbetriebnahme

Da Windows für meine Definition keine richtige „Inbetriebnahme“ für einen Computer ist, hab ich also meinen Plan von weiter oben fortgesetzt.
Die Manjaro Live Version statete ohne Probleme und ich konnte die interne NVME-SSD auf die externe Festplatte übertragen,
allerdings erst, nachdem ich den NVME Modus von RAID auf AHCI umgestellt hatte. <a href="https://triplescomputers.com/blog/uncategorized/solution-switch-windows-10-from-raidide-to-ahci-operation/">Mehr Infos dazu gibt's hier</a>.

Nachdem ich beides gemacht hatte, musste ich noch die ID der Festplatte ändern, sodass ich von der externen booten konnte, ohne Windows in Verwirrung zu bringen.
Aber so weit bin ich gar nicht gekommen, denn das ID ändern mit dem `diskpart`-Tool – oder wie das heißt – hat die Windows Installation nämlich nicht überstanden.
War mir aber an der Stelle auch egal, so richtig was anfangen mit Windows konnte ich hier drauf ohne hin nicht.
Also Manjaro nochmal gebootet, ging ja ohne Probleme, Manjaro Installer gestartet und einmal eine neue Paritions-Tabelle erstellt, weg mit Windows, hehe. 

Der Rest war wie üblich, wenn ich mir ein Linux eingerichtet hatte.
Als Fenstermanager kam GNOME 3.28 zum Einsatz und über meine weiteren Lieblingsprogramme unter Linux kann ich ja in einem anderen Post informieren, das würde den Rahmen von diesem hier etwas sprengen.
Den Rest des Freitags hab ich jedenfalls damit verbracht, die tollen Welten von Arch Linux und AUR, dem Arch User Repository, zu erforschen
und es mir gemütlich zu machen, in meiner neuen, frischen Linux installation.
Und ich bin heute noch nicht fertig, alles zu erkunden, und das zwei Tage danach.

## Schlusswort

Zusammenfassend würde ich sagen, dass ich hier einen tollen Laptop ergattert habe, zu einem sehr vernünftigen Preis, den ich auch später noch brauchen werde und brauchen kann.
Der Anfang war zwar etwas happig wegen der Panne, aber da das so problemlos behoben wurde,
kann man eher sagen, es war eine interessante Erfahrung, die ich da gemacht habe, dass tatsächlich ein Techniker von Dell kommt und das repariert, hat man ja auch nicht alle Tage.

Übrigens, Dell gibt einem Windows-Keys zu den Ersatzteilen dazu, falls man die Festplatte beim Repariern löschen muss.
*hust* Anscheinend haut Microsoft den OEMs die Lizenzen so um die Ohren, dass sie die einfach herschenken.
Ist ja selbst bei der „Developer Editon“, die mit Ubuntu 16.04 LTS aus der Fabrik kommt eine dabei, sollte man mal irgendwann doch Windows drauf brauchen. 

Na dann, das war's mit dem Post.
Hoffentlich war es einigermaßen interessant zu lesen und nicht total lame, aber das ist ja gerade mal mein zweiter richtiger Post hier,
also darf ich mir das erlauben, viele Fehler zu machen und nicht gut zu sein, denke ich.

Bis zum nächsten Post,<br>
Lucy

