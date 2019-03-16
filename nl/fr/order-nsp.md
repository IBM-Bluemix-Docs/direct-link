---

copyright:
  years: 2017, 2018, 2019
lastupdated: "2019-02-19"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:codeblock: .codeblock}
{:pre: .pre}
{:screen: .screen}
{:tip: .tip}
{:note: .note}
{:download: .download}

# Comment commander IBM Cloud Direct Link Dedicated ?
{: #how-to-order-ibm-cloud-direct-link-dedicated}

1. Vérifiez que votre fournisseur de réseau peut accéder au point de présence (PoP) approprié et établir une interconnexion avec l'environnement {{site.data.keyword.BluSoftlayer_notm}}.
2. Ouvrez une demande {{site.data.keyword.cloud}} Direct Link Dedicated et indiquez les informations demandées. (Vous pouvez faire appel à des ingénieurs commerciaux IBM pour vous aider).
3. {{site.data.keyword.BluSoftlayer_notm}} fournit une lettre d'autorisation (LOA) pour la connexion.
4. Confirmez que votre circuit a atteint le PoP et a été finalisé par l'opérateur.
5. Commandez une interconnexion à l'aide des informations d'affectation de site client (CFA (Customer Facility Assignment)) {{site.data.keyword.BluSoftlayer_notm}} figurant dans la lettre d'autorisation, ce qui prend en principe de 2 à 10 jours ouvrables pour aboutir. (Ce délai dépend du fournisseur du site et du type de priorité de la commande défini par le client). Ce processus comprend la configuration du correctif pour le port de terminaison {{site.data.keyword.BluSoftlayer_notm}}.
6. Fournissez à {{site.data.keyword.BluSoftlayer_notm}} l'avis d'achèvement de l'interconnexion du fournisseur du site figurant dans le ticket du portail {{site.data.keyword.BluSoftlayer_notm}}.
7. {{site.data.keyword.BluSoftlayer_notm}} vérifiera l'efficacité de l'avis d'achèvement et commandera le correctif à appliquer à partir des informations LOA/CFA au routeur d'interconnexion (XCR) et à d'autres équipements.
8. L'affectation de votre adresse IP sur l'infrastructure réseau {{site.data.keyword.BluSoftlayer_notm}} sera effective dans les trois jours ouvrables une fois l'interconnexion terminée.

## Emplacements

Le tableau fournit des détails sur les centres de données IBM Cloud dans lesquels Direct Link Dedicated est disponible :

|**Code d'emplacement IBM** | **Opérateur de salle d'interconnexion**| **Code de site opérateur** | **Adresse de l'opérateur** |
|-----------------|-----------------|--------------------|--------------------|
| **APAC** | | | |
| CHE01 | Tata | PH-01 | 226, Red Hills Road,Kallikuppam, Ambattur |
| HKG01 | Mega-I (via PACNET) | Mega-I (iAdvantage Hong Kong) |29F, 399 Chai Wan Road |
| MEL01 | Digital Realty | MEL11 | 72 Radnor Drive, Deer Park |
| MEL02 | NextDC | M2 | 820 Lorimer Street, Port Melbourne |
| PER01 | Metronode | F1Z | 60 Randell St, Shenton Park, Western Australia |
| SEO01 | C&C | Seoul01 | 46, Pangyo-ro 255beon-gil, Bundang-gu, Seongnam-si, Gyeonggi-do |
| SEO02 | KINX | KINX Bundang IDC | 3F Hostway IDC ,343-1 Yatap-dong , Gyeonggi-do |
| SNG01 | Digital Realty | SIN10 | 29A International Business Park, S180 |
| SNG02 | Equinix | SG1 | 20 Ayer Rajan Crescent Industrial Park |
| SYD01 | Global Switch | SYD01 | 400 Harris Street aka 273 Pyrmont St Ultimo  |
| SYD02 | Equinix | SY3 | 47 Bourke Rd |
| SYD03 | NextDC | 4 Eden Park Drive, Macquarie Park |
| SYD04 | Digital Realty | SYD10 | 1-11 Templar Rd, Erskine Park |
| SYD05 | Equinix | 200 Bourke Rd |
| TOK01 | Equinix | TY2 |
| TOK02 | At Tokyo | CC2 | 
| TOK03 | Equinix | 
| TOK04 | SoftBank |
| TOK05 | NTT |
| **EMEA** |  |  |
| AMS02 | Equinix | AM1 / AM2 | Larrderhoogtweg 57 |
| AMS03 | KPN | Amsterdam 3 | Rondebeltweg 62 |
| FRA01 | InterXion | FRA01 | Hanauer Landstrasse 302 |
| FRA02 | Zenium | FRA1 | Leonhard - Heisswolf Str 4., Frankfurt am Main |
| FRA03 | Equinix| FRA6 | Larchenstrasse 110, Frankfurt Griesheim |
| FRA04 | E-Shelter | Francfort 1 | Eschborner Landstrasse 100, Building H | 
| FRA05 | InterXion | FRA05 | Weismüllerstraße 40 |
| LON01 | Equinix (fTelecity) | LD8 | 6/7 Harbour Exchange  E14 9GE |
| LON02 | Digital Realty | LHR13 | Fountain Court, Cox Lane |
| LON03 | Equinix | LD5 | 8 Buckingham Ave |
| LON04 | ARK | A103 | A57 Cody Technology Park Old, Victor Way, Farnborough |
| LON06 | Zenium | LON1 | 12 Liverpool Rd, Trading Estate |
| MIL01 | Data IV | Via Monzoro 101-105 , 20010 Cornaredo (MI) |
| MIL02 | Infracom Italia | Infracom 21 Via Caldera Way | Infracom Italia Spa, Building D, Caldera Business Park, Via Caldera, 21|
| OSL01 | EVRY | DigiPlex - Fetsund | 9,, Heiaveien, 1900 Fetsund |
| OSL02 | Verizon | Verizon Oslo | Hans Møller Gassmanssvei 9 |
| PAR01 | Global Switch | PAR01 | Société par Actions Simplifiée Unipersonnelle, 7-9 rue Petit |
| PAR02 | Equinix | PA2 | 114 Rue Ambroise Croizat, St Denis |
| STO01 | InterXion | STO01 | Esbogatan 11 |
|  |  |  |
| **Code point de présence/centre de données IBM** | **Opérateur de salle d'interconnexion** | **Code de site opérateur** |
| **Amériques** |  |  |
| ATL01*| Digital Realty | ATL13 | 56 Marietta Street |
| CHI01 | Equinix | CH4 | 350 E. Cermak |
| DAL03 | Equinix | DA1 | 1950 N. Stemmons Freeway |
| DAL04 | Digital Realty | DFW14 | 2323 Bryan St |
| DAL09 | Digital Realty | DFW35 | 900 Quality Way |
| DAL10 | QTS | IRV | 6431 Longhorn Drive |
| DAL12 |Digital Realty | DFW18 | 907 Security Row |
| DAL13 | Cyrus One | Carrollton - Frankford | 1649 W. Frankford Rd |
| DEN01* | Coresite | DE1 | 910 15th Street | 
| HOU02* | IBM | HOU02 | 855 Greens Parkway | 
| LAX01* | Coresite | LA1 | 624 S. Grand Ave. AKA 1 Wilshire Blvd |
| MEX01 | Alestra | Alestra Queretaro Datacenter | Lateral Carretera Estatal 431,Parque Tecnologico Inovacion Lote 79, El Marqués |
| MIA01 | Terremark / Verizon | NAP | 50 NE 9th Street |
| MON01 | COLO-D | COLO-D1 | 2525 Rue Canadien |
| MON02 | Cologix | MTL3 | 1155 University Street |
| NYC01 | Digital Realty | JFK10 | 111 8th Ave |
| NYC02* | Equinix | NY4 | 755 Secaucus Rd, Secaucus, NJ |
| NYC03* | Equinix | NY5 | 800 Secaucus Rd, Secaucus, NJ |
| SAO01 | Ascenty | SP1 | Rua Presbitero Plinio Alves de Souza, 757 J. Ermida II,Jundiai |
| SAO02 | Equinix | SP2 | Alameda Araguaia, 3641 - Alphaville, Barueri |
| SEA02 | The Westin Building | WBX | 2001 6th Avenue |
| SJC02 | Equinix | SV1 | 11 Great Oaks Blvd |
| SJC03 | Digital Realty | SJC31 | 1100 Space Park Drive |
| SJC04 | Infomart | SJC1 | 2001 Fortune Drive |
| TOR01 | Digital Realty | YYZ11 | 371 Gough Rd |
| TOR02 | Cologix | TOR1 | 151 Front Street |
| WDC02 | Equinix | DC2 | 21715 Filigree Ct |
| WDC04 | Digital Realty | IAD38 | 44060 Digital Loudoun Plaza (Bldg K) |
| WDC05 | Coresite | DC2 | 12098 Sunrise Valley Dr |
| WDC06 | Raging Wire | VA2 | 44610 Guilford Drive |
| WDC07 | Sabey | Sabey Intergate.Ashburn | 21741 Red Rum Dr|

## Tarification

Pour obtenir des informations de tarification, voir la [rubrique sur la tarification](/docs/infrastructure/direct-link/pricing.html).

Si vous avez besoin de l'adresse exacte de TOK01 ou TOK02, contactez votre équipe de vente ou de gestion des offres Direct Link.{:note}
