.. only:: latex

   #####
   Obsah
   #####

.. only:: html

   `GISMentors <http://gismentors.cz>`_ | Školení `GRASS GIS
   <http://gismentors.cz/skoleni/grass-gis>`_ | `QGIS
   <http://gismentors.cz/skoleni/qgis>`_ | `PostGIS
   <http://gismentors.cz/skoleni/postgis>`_ | `GeoPython
   <http://gismentors.cz/skoleni/geopython>`_
   
   ****
   Úvod
   ****

.. only:: html

   .. image:: images/intro_logo.png
      :width: 140px
      :align: left

.. index::
   single: GIS
   single: geografický informační systém

`GeoServer <http://www.geoserver.org/>`_  je Open Source server určený pro sdílení prostorových dat publikovaný pod 
všeobecnou licencí GNU GPL. Mezi hlavní výhody patří zejména rychlost vývoje a rozšiřování jeho funkcionality.
Licence GNU GPL umožňuje používání software i pro komerční účely. Podstatné je, že
umožňuje i modifikaci zdrojového kódu a jeho následné šíření. Neznedbatelnou výhodou serveru je existence grafického
uživatelského rozhraní pro administraci systému a sada cvičných dat, které jsou automaticky po instalaci vypublikovány.

.. only:: latex

   .. figure:: images/intro_logo.png
      :scale-latex: 150

      Logo projektu GeoServer.

.. only:: html

.. tip::
   Text školení je dostupný i v tisknutelné formě `PDF
   <./skoleni-geoserver-zacatecnik.pdf>`_.
   
.. important:: Školení je zaměřeno na aktuální verzi `GeoServer 2.14.1 
               <http://geoserver.org/release/stable/>`_. V
               jiných verzích není zaručena funkčnost uvedených příkladů. 

.. raw:: latex

   \newpage

GeoServer je psán v programovacím jazyce Java a uživatelské prostředí 
pro konfiguraci v jazyce Java a HTML. Díky použití těchto rozšířených
programovacích prostředků je GeoServer multiplatformní, tudíž jej lze
využívat na většině používaných operačních systémech jako je MS
Windows, GNU/Linux nebo OS X. GeoServer využívá pro práci s prostorovými
daty v rastrové anebo vektorové reprezentaci knihovnu `GeoTools <http://geotools.org>`_ 
případně `GDAL <http://gdal.org>`_, díky tomu je možné pomocí GeoServeru publikovat široké
spektrum formátů.

.. figure:: images/intro_geoserver.png
   :scale-latex: 65

   Ukázka uživatelského rozhraní konfiguračního nástroje pro GeoServer.

GeoServer je populární i pro svou rozšiřitelnost pomocí takzvaných
rozšíření (extensions).  Rozšíření jsou dílčí nástroje, které
jsou vyvíjeny komunitou kolem serveru GeoServer.  Pomocí rozšíření je možné dopnit do
serveru GeoServer novou funkcionalitu či podporu pro další formáty či služby.

.. only:: html
             
   #####   
   Obsah
   #####

.. toctree::
   :maxdepth: 2

   intro/index
   styly/index
   vektor/index
   rastr/index
   dlazdice/index
   inspire/index

*******
Dodatky
*******

O dokumentu
===========

Text vychází z textu http://training.gismentors.eu/qgis-zacatecnik/

Text dokumentu je licencován pod `Creative Commons
Attribution-ShareAlike 4.0 International License
<http://creativecommons.org/licenses/by-sa/4.0/>`_.

.. figure:: images/cc-by-sa.png 
   :width: 130px
   :scale-latex: 120
              
*Verze textu dokumentu:* |release| (sestaveno |today|)

Autoři
------

Za `GISMentors <http://www.gismentors.cz/>`_:

* `Jan Růžička <http://www.gismentors.cz/mentors/ruzicka/>`_

Text dokumentu
--------------

.. only:: latex

   Online HTML verze textu školení je dostupná na adrese:

   * http://training.gismentors.eu/geoserver-zacatecnik/

Zdrojové texty školení jsou dostupné na adrese:

* https://github.com/GISMentors/geoserver-zacatecnik


