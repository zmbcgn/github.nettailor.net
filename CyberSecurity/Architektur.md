Architektur und Design
=================

Asymetrische Cipher
----------------------
-   Diffie-Hellman
-   RSA
-   ECC
-   DSA


Backup
--------
-   Inkrementelles Backup
    -   Sichert alle Daten, die sich geändert haben, seit dem letzten inkrementellen Backup.
-   Differentielles Backup
    -   Sichert alle Daten seit dem letzten FULL Backup.

Cipher Suites
--------------
-   Block Cipher
    -   Bei einem Block Cipher werden mehrere Bits auf einmal verschlüsselt, bevor zu dem nächsten Block übergegangen wird.
-   Stream Cipher
    -   Bei einem Stream Cipher wird ein Bit nach dem anderen verschlüsselt.

Crossover-Error-Rate
----------------------
Eine Kenngröße bei biometrischen Sicherheitsverfahren um den Punkt zu Beschreiben bei dem False-Rejection-Rate und False-Acceptance-Rate gleich sind.

Datenbesitzer - Data Owner
-----------------------------
Datenbesitzer tragen die Verantwortung für Daten Qualität Standards. (Geschäftsführung / Executive Level)

Datentreuhänder - Data Custodian
------------------------------------
Individuen die mit der Aufbewahrung von Informationen unter der Aufsicht des Datenbesitzers betraut sind.

Datenverwalter - Data Steward
--------------------------------
Der Datenverwalter trägt die Verantwortung zur Einhaltung von Qualitätsstandards (Tagesgeschäft)

Digitale Zertifikate
--------------------
-   P7B
    -   Base64 / ASCII
    -   WINDOWS / JAVA / Tomcat
    -   .p7b oder .p7c
-   PFX
    -   binär
    -   WINDOWS
    -   .pfx / .p12
-   PEM
    -   Base64 / ASCII
    -   APACHE HTTP / nginx
    -   .pem / .cer / .crt
-   DER
    -   binär
    -   JAVA
    -   .der / .cer / .crt
-   EXTENDED VALIDATION
    -   liefert ein Höchstmaß an Vertraulichkeit und Sicherheitsfeatures
-   DOMAIN VALIDATION CERTIFICATE
    -   Zertifikat das nur den Domainnamen beinhaltet (preiswert)
-   ORGANIZATIONAL VALIDATION
    -   Unternehmen werden einer gründlichen Prüfung unterzogen. Ein Abgleich mit offiziellen, staatlichen Institutionen (Handelsregister etc.) Ein gebräuchlicher Typus von Zertifikaten bei öffentlichen Stellen.

False-Rejection-Rate
----------------------
Eine Kenngröße bei biometrischen Sicherheitsverfahren um zu ermitteln wie viele valide Versuche dennoch abgelehnt worden sind.

False-Acceptance-Rate
-------------------------
Eine Kenngröße bei biometrischen Sicherheitsverfahren um zu ermitteln wie viele ungültige Versuche dennoch erlaubt worden sind.

HASH Algorithmen
--------------------
-   MD5
    -   128 Bit
-   SHA1
    -   160 Bit
-   SHA2
    -   224 – 512 Bit

Schlüsselverlängerung - Key Stretching
-----------------------------------------
…wird verwendet um einen vermeintlich schwachen Schlüssel, normalerweise ein Passwort oder ein Schlüsselwort, sicherer gegen brute-force Angriffe zu machen. Es müssen zum „Code knacken“ mehr Ressourcen eingesetzt werden.

Key-Stretching Algorithmen

-   PBKDF2
    -   CPU gehärtet
-   bcrypt
    -   CPU und Speicher gehärtet

Symmetrische Cipher
-----------------------
-   DES
    -   56 Bit
-   3DES
    -   112 Bit
-   IDEA
    -   128 Bit
-   AES
    -   128/192/256 Bit
-   BLOWFISH
    -   32 bis 448 Bit
-   TWOFISH
    -   128/192/256 Bit
-   RC4
    -   ?
-   RC5 / RC6
    -   0 – 2048 Bit

Zugriffskontrolle
-----------------
-   Descretionary Access Control
    -   Der Dateneigentümer vergibt Zugriffsrechte
-   Attribute-Based-Control
    -   Dynamisch und Kontext-abhängige Zugriffskontrolle nach dem WENN-DANN Schema.
-   Mandatory-Access-Control
    -   Ein Computer-System ermittelt die entsprechenden Berechtigungen anhand von „Labels“. Implementierung erfolgt dann über Rollen-Basierte Zugriffskontrolle.
-   Rollen-Basierte Zugriffskontrolle
    -   Genauso wie Mandatory-Access-Control, nur das hier die Berechtigungen in Gruppen, oder Sets vergeben werden. „PowerUser“ wäre eine solche Rolle.