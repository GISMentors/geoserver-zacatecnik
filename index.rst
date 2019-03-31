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

`GeoServer <http://www.geoserver.org/>`__ je open source mapový server
určený pro sdílení a publikaci geografických dat. Mezi jeho hlavní
výhody patří zejména rychlost vývoje a rozšiřování jeho funkcionality.
Licence GNU GPL umožňuje jeho používání i pro komerční
účely. Podstatné je, že umožňuje i modifikaci zdrojového kódu a jeho
následné šíření. Neznedbatelnou výhodou tohot mapového serveru je
existence webové uživatelského rozhraní pro administraci systému a v
neposlední řadě sada cvičných dat, které jsou automaticky po instalaci
vypublikovány.

.. only:: latex

   .. figure:: images/intro_logo.png
      :scale-latex: 150

      Logo projektu GeoServer.

.. only:: html

.. important:: Školení je zaměřeno na verzi `GeoServer 2.14.1
   <http://geoserver.org/release/stable/>`__. V jiných verzích není
   zaručena funkčnost uvedených příkladů.

.. raw:: latex

   \newpage

GeoServer je včetně jeho uživatelského prostředí napsán v
programovacím jazyce Java. Díky tomu je GeoServer multiplatformní,
tudíž jej lze využívat na většině používaných operačních systémech
jako je MS Windows, GNU/Linux nebo OS X. GeoServer využívá pro práci s
prostorovými daty v rastrové anebo vektorové reprezentaci knihovnu
`GeoTools <http://geotools.org>`__ případně `GDAL
<http://gdal.org>`__.  Díky tomu je možné pomocí GeoServeru publikovat
široké spektrum formátů.

.. figure:: images/intro_geoserver.png
   :scale-latex: 65

   Ukázka uživatelského rozhraní konfiguračního nástroje pro GeoServer.

GeoServer je populární i pro svou rozšiřitelnost pomocí takzvaných
rozšíření (extensions).  Rozšíření jsou dílčí nástroje, které jsou
vyvíjeny komunitou kolem projektu GeoServer.  Pomocí rozšíření je
možné dopnit do GeoServeru novou funkcionalitu či podporu pro další
formáty či služby.

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

Text dokumentu je licencován pod `Creative Commons
Attribution-ShareAlike 4.0 International License
<http://creativecommons.org/licenses/by-sa/4.0/>`__.

.. figure:: images/cc-by-sa.png 
   :width: 130px
   :scale-latex: 120
              
*Verze textu dokumentu:* |release| (sestaveno |today|)

Autoři
------

Za `GISMentors <http://www.gismentors.cz/>`_:

* `Jan Růžička <http://www.gismentors.cz/mentors/ruzicka/>`_
* `Boris Kružliak <http://www.gismentors.cz/mentors/kruzliak/>`_  

Text dokumentu
--------------

.. only:: latex

   Online HTML verze textu školení je dostupná na adrese:

   * http://training.gismentors.eu/geoserver-zacatecnik/

Zdrojové texty školení jsou dostupné na adrese:

* https://github.com/GISMentors/geoserver-zacatecnik

Případné chyby nebo náměty na vylepšení můžete hlásit:

* https://github.com/GISMentors/geoserver-zacatecnik/issues
  


