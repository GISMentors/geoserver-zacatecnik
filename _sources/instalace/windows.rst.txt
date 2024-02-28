.. _label: instalace-windows

.. index::
   single: MS Windows
   see: MS Windows; Instalace

MS Windows
----------

Systém GeoServer je možné pod MS Windows nainstalovat několika způsoby.
Jako osvědčený způsob se jeví využití platformně nezávislého balíčku.

Platformně nezávislý balíček
============================

Pro účely školení a seznamování se s nástrojem GeoServer je vhodná
varianta *Platform Independent Binary*
(http://geoserver.org/download/).  Jedná se o zip archiv,
který je možné rozbalit kdekoli na disk. Nedoporučují se adresáře s
diakritikou a mezerami.


Další možnosti instalace
========================

Další možností je využít Windows installer. Obvykle s ním nejsou problémy, ale
mohou se vyskytnout, proto jej nedoporučujeme.

Další možností instalace je využití servlet kontejneru (např. Tomcat nebo JBOSS).
Tomcat nebo JBOSS se instaluje pomocí instalátorů (MSI, EXE). GeoServer se pak 
instaluje nakopírováním Web Archive (soubor s příponou WAR) do struktur Tomcat nebo JBOSS.

.. note:: Tyto způsoby instalace GeoServeru nejsou pro začátečníky vhodné.
