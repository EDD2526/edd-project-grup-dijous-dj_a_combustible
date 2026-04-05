View this project on [CADLAB.io](https://cadlab.io/project/30195). 

# Projecte DJ_A_combustible

>**Autors: Edgar Castro i Pere Ribas
>**Versió: 1

----------

## Objectiu

Monitorització en temps real el nivell de combustible i les seves condicions (pressió/temperatura).

Control de la bomba de combustible i el tancament de seguretat de forma automàtica.

Bona connexió amb el vehicle per a que altres unitats de control tinguin accès a la informació.



## Diagrama de blocs
![Diagrama_de_blocs](C:\Users\danco\Documents\AA_UB\AA_SEMESTRE4\EdD\AA_PROJECTE\edd-project-grup-dijous-dj_a_combustible\AA_DIAGRAMABLOCSFINAL.png)

### Descripció/funcionalitat de cada bloc

  **Etapa 1, Alimentació**
  Etapa dedicada a protegir i alimentar tots els altres blocs del projecte.
  Primer els 12V seran protegits amb díodes, i aquests serviran per a la bomba del combustible i el tancament del dipòsit.
  A partir d'aqui baixarem a 3.3V que ens servirà per alimentar el nostre Micro.

  **Etapa 2, Control**
  Etapa destinada a ser el cervell del projecte.
  Trobem el micro, encarregat de rebre informació a través dels sensors, del CAN i del MAX3232, i de donar ordres ja siguin programades o especificades per l'usuari mitjançant els botons.
  Disposem també d'un conncetor per a la possible programació, de dos DE9 pels transceptors i d'un clock.

  **Etapa 3, Sensors i Potència dels motors**
  Etapa destinada a agafar informació a través del sensor de pressió de pneumàtics i del sensor de nivell de combustible.
  A més gràcies a les sortides digitals del micro, MOSFETs i relés, es controlarà de manera segura l'activació o desactivació de la bomba de combustible i l'obriment o tancament del dipòsit.

  **Etapa 4, Interacció i comunicació**
  Aquesta última etapa simplement serveix per a activar o desactivar els motors de la bomba o del tancament.
  Mitjançant botons i LEDs (per demostrar el correcte funcionament) es realitzarà aquestes dues funcions.

-----------

## Requisits / Especificacions

  * Alimentació; 12V, regulada 5V i 3.3V
  * Microcontrolador PIC24HJ128GP502
  * ...

-----------

## Components

| Descripció | Ref | Package | Datasheet | Proveïdor | Preu | Unitats |
| --- | --- | --- | --- | --- | --- | --- |
| **Microcontrolador PIC24 (16-bit)** | U20 | SOIC-28W | [Datasheet](http://ww1.microchip.com/downloads/en/DeviceDoc/70293G.pdf) | - | - | 1x |
| **Sensor de Pressió (TPMS)** | U23 | QFN-24-1EP | [Datasheet](https://www.nxp.com/docs/en/reference-manual/FXTH87ERM.pdf) | - | - | 1x |
| **Sensor Capacitiu (Combustible)** | U6 | QFN-16 | [Datasheet](https://www.ti.com/lit/ds/symlink/fdc2214.pdf) | - | - | 1x |
| **Relé SPST-NO (6A)** | K1, K2 | Vertical THT | [Datasheet](https://www.fujitsu.com/sg/imagesgig5/ftr-ly.pdf) | - | - | 2x |
| **MOSFET N-Channel** | Q1, Q2 | TO-220F-3 | [Datasheet](http://www.irf.com/product-info/datasheets/data/irliz44n.pdf) | - | - | 2x |
| **Regulador Step-Down 12V** | U1 | TO-263-5 | [Datasheet](http://www.ti.com/lit/ds/symlink/lm2596.pdf) | - | - | 1x |
| **Regulador LDO 3.3V** | U2 | TO-252-3 | [Datasheet](http://www.ti.com/lit/ds/symlink/lm1117.pdf) | - | - | 1x |
| **Transceptor CAN** | U3 | SOIC-8 | [Datasheet](http://www.ti.com/lit/ds/symlink/sn65hvd230.pdf) | - | - | 1x |
| **Driver RS232** | U4 | SOIC-16 | [Datasheet](https://datasheets.maximintegrated.com/en/ds/MAX3222-MAX3241.pdf) | - | - | 1x |
| **Díode Rectificador (Flyback)** | D_p_bomba1, 2 | DO-41 THT | [Datasheet](http://www.vishay.com/docs/88503/1n4001.pdf) | - | - | 2x |
| **Díode Schottky (DCDC)** | D_schottky1 | D_SMA | - | [Datasheet](https://ww1.microchip.com/downloads/aemdocuments/documents/HRDS/ProductDocuments/DataSheets/1n5823-25.pdf) | - | 1x |
| **Díode Zener 14V** | D_Zener1 | D_SOD-123 | - | - | - | 1x |
| **Díode Protecció (MBR0520)** | D_Proteccio1 | D_SOD-123 | [Datasheet](http://www.mccsemi.com/up_pdf/MBR0520~MBR0580(SOD123).pdf) | - | - | 1x |
| **Cristall de Quars** | Y1 | SMD 5032-2 | - | - | - | 1x |
| **LED Indicador (3mm)** | D1, D2 | LED_D3.0mm | - | - | - | 2x |
| **Pulsadors (Slide/DIP)** | SW1, SW2, SW3 | SMD DIP | - | - | - | 3x |
| **Connector DB9 (RS232)** | J1, J2 | DSUB-9 | - | - | - | 2x |
| **Connectors Bomba/Tancament** | J4, B1, T1 | Pin 1x02 | - | - | - | 3x |
| **Connector Prog. PIC (ICSP)** | J3 | Pin 1x05 | - | - | - | 1x |
| **Connector Prog. Sensor (BKGD)** | J5 | Pin 1x04 | - | - | - | 1x |
| **Inductor 33uH (DCDC)** | L_DCDC1 | SRP7028A | - | - | - | 1x |
| **Inductor 18uH (Filtre)** | L1 | L_0805 | - | - | - | 1x |
| **Ferrite Bead** | FB1, FB2 | L_1812 | - | - | - | 2x |
| **Condensador 680uF** | Cin_DCDC1 | Radial D10mm | - | - | - | 1x |
| **Condensador 220uF** | Cout_DCDC1 | Radial D10mm | - | - | - | 1x |
| **Condensador 100uF** | Cout_reg1 | Radial D5mm | - | - | - | 1x |
| **Condensadors 10uF** | C7, Cin_reg1 | C_0805 | - | [Datasheet](https://datasheets.kyocera-avx.com/AutoMLCC.pdf) | - | 2x |
| **Condensadors 100nF** | C1-C9, C32-33 | C_0805 | - | [Datasheet](https://datasheets.kyocera-avx.com/AutoMLCC.pdf) | - | 10x |
| **Condensadors 22p / 33p** | C10, C11, C20 | C_0805 | - | [Datasheet](https://datasheets.kyocera-avx.com/AutoMLCC.pdf) | - | 3x |
| **Resistència 10k** | R1-R21 (varies) | R_0805 | - | [Datasheet](https://www.vishay.com/docs/20035/dcrcwe3.pdf) | - | 7x |
| **Resistència 4.7k** | R3, R4 | R_0805 | - | [Datasheet](https://www.vishay.com/docs/20035/dcrcwe3.pdf) | - | 2x |
| **Resistència 220** | R22, R23 | R_0805 | - | [Datasheet](https://www.vishay.com/docs/20035/dcrcwe3.pdf) | - | 2x |
| **Resistència 120 (CAN)** | R_CAN1 | R_0805 | [Datasheet](https://www.vishay.com/docs/20035/dcrcwe3.pdf) | - | - | 1x |

-----------

## Software

### Eines:

  * KiCad 9.0 o superior
  * 

### Configuraci&#243; :

  * 

### Funcionalitats:

  * 

-----------


## Historial de canvis
### 15/03/2026
Hem millorat el diagrama de blocs, tant l'etapa 1 com la 3.
A més he fet que les fletxes siguin més gruixudes per tal que es vegin millor.
Al KiCad he obert l'esquemàtic i he **creat els subesquemàtics**, en els quals només he posat els noms de les etapes 1 i 3.
I he fet una **carpeta** per anar posant les millores dels **diagràmes de **blocs**.
Realment del diagrama de blocs només quedaria posar el **nom i especificacions generals dels components que falten**,  acabar de modificar una mical del **disseny del diagrama** i ja estaria acabat.

### 19/03/2026
Hem millorat el diagrama de blocs, amb les correccions dels professors.
També hem començat la part esquemàtica de les diferents etapes a KiCad. En general, s'ha avançat gran part, quedarien connectar pocs pins i definir-los correctament, entendre bé el funcionament i les correccions del professor. 
A més, també haurem de millorar l'organització dels subesquemàtics creats a la carpeta compartida per tal d'aquesta manera tenir una millor visualització i entendre les etapes millor. 
Properament haurem de assignar valors als diferents components i optimitzar algun circuit

### 22/03/2026
S'ha *finalitzat definitivament el diagram de blocs*.
A l'etapa de control s'ha **afegit** un **relé** per a major **protecció** per al microcontrolador degut a les grans càrregues i potències que pot comportar el funcionament de la bomba i el tancament.
S'ha **afegit** el símbol del sensor de combustible **FDC2214**, falta **crear** el símbol del sensor de pressió **FXTH87**

### 24/03/2026
A dia d'avui, en principi no queda pràcticament res (de la part de l'esquemàtic). S'ha avançat gran part del que ens vam proposar en la darrera sessió de pràctiques, com la forma dels pins, afegir els pins que faltaven, els valors dels components, etc., juntament amb les correccions del professor. A banda d'això, també s'ha afegit una part de programació ICSP per a que l'usuari pugui controlar al seu gust mitjançant un connector extern del propi usuari al microcontrolador. 
A la tarda d'avui, només queda (de moment) crear el símbol del sensor de pressió i connectar els pins corresponents.

### 25/03/2026
**Esquemàtic acabat** abans de l'última sessió (a falta de les correccions que es faràn demà a classe).
S'ha continuat fent el Readme on s'han anat emplenant diferents apartats.
A banda d'això s'hauria d'**anar triant les petjades**, sobretot pels símbols que hem creat nosaltres o els que no estem acostumats a treballar, ja que per components passius o que ja hem tocat, les petjades suposem que seran les mateixes i que no les haurem de crear ni afegir al KiCad


### 29/03/2026
La **majoria de petjades s'han afegit**. Tots els components que no son resistències o capacitats ja tenen **petjada**.
Falta **mirar** els **pins FXTH87** ja que els pins possiblement estiguin **mal posats** i el **footprint no coincideixi** i falta repassar el propi datasheet per saber quin footprint triar.
*Altres footprints que falten:*
Cristall
Connectors 1x2 i 1x5
Díodes
Bobines
Resistències i Capacitats
També s'hauràn d'afegir les petjades i datasheets al README



### 04/04/2026
**Totes les petjades afegides**
Sensor de pressió acabat
Falta posar les petjades al readme
**Esquemàtic acabat (en teoria)**
