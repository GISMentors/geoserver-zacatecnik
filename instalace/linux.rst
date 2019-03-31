.. |aplikace_ikona| image:: images/aplikace_ikona.png
   :width: 1.5em

.. _label: instalace-linux

.. index::
   single: Linux
   see: Linux; Instalace


GNU/Linux - Ubuntu
------------------

Instalace programů napsaných v jazyce Java spočívá v instalaci JRE
(Java Runtime Environment). JRE bývá obvykle již v systému Ubuntu k dispozici.
Pokud tomu tak není, je její instalace založená na tzv. balíčcích, které jsou k
dispozici v repozitářích.
Existuje řada verzí JRE, základní open source verze dostupná ve všech repozitářích 
by měla pro běh serveru dostačovat. 

Instalace JRE
=============

Instalace v terminálu, předpokládá zadání pouze jednoho příkazu.

.. raw:: latex
 
	 \newpage

.. notecmd:: Instalace JRE
               
   .. code-block:: bash

      sudo apt-get install openjdk-8-jre

.. note:: Je možné, že JRE nebude v repozitáři. Pak je nutné repozitář přidat.

   .. code-block:: bash

      sudo add-apt-repository ppa:openjdk-r/ppa
      sudo apt-get update
      sudo apt-get install openjdk-8-jre  
      

Instalace GeoServer
===================

Pro účely školení a seznamování se s nástrojem GeoServer je vhodná varianta 
`Platform Independent Binary`. Jedná se o ZIP archiv, který je možné rozbalit kdekoli
na disk. Nedoporučují se adresáře s diakritikou a mezerami.

Rozbalení archivu by obvykle již mělo stačit pro spuštění serveru. V
případě starších verzí nebo v případě nestandardních cest je nutné
specifikovat umístění JRE (viz Řešení problémů s instalací).

Řešení problémů s instalací
===========================

V případě problémů se spuštěním je nutné upravit spouštěč serveru, tak
aby věděl, kde je k dispozici `JRE`. Přesuneme se do adresáře bin
rozbaleného serveru.  Zjistíme kde se nachází `JRE`.  Upravíme
spouštěč :file:`startup.sh` přidáním informace o umístění
``JAVA_HOME``.

.. raw:: latex
 
	 \newpage

V souboru :file:`geoserver-2.14.1/bin/startup.sh` nastavíme cestu k instalaci Javy, např.

.. code:: bash

   JAVA_HOME=/usr/lib/jvm/java-8-openjre-amd64

   
Další možnosti instalace
========================

Další možností instalace je využití servlet kontejneru (např. Tomcat nebo JBOSS).
Tomcat nebo JBOSS se instaluje pomocí balíčků. GeoServer se pak instaluje nakopírováním
Web Archive (soubor s příponou WAR) do struktur Tomcat nebo JBOSS.

.. note:: Tento způsob instalace GeoServeru není pro začátečníky vhodný.
