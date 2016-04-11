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

      sudo apt-get install openjdk-7-jre

Instalace GeoServer
===================

Pro účely školení a seznamování se s nástrojem GeoServer je vhodná varianta 
`Platform Independent Binary`. Jedná se o ZIP archiv, který je možné rozbalit kdekoli
na disk. Nedoporučují se adresáře s diakritikou a mezerami.

Následně je nutné upravit spouštěč serveru, tak aby věděl, kde je k dispozici `JRE`.
Přesuneme se do adresáře bin rozbaleného serveru. Zjistíme kde se nachází `JRE`.
Upravíme spouštěč startup.sh přidáním informace o umístění `JAVA_HOME`.

.. raw:: latex
 
	 \newpage

.. notecmd:: Instalace GeoServer
               
   .. code-block:: bash

      cd geoserver-2.8.3/bin
	  locate jvm
	  vim startup.sh
	  JAVA_HOME=/usr/lib/jvm/java-7-openjre-amd64

   
Další možnosti instalace
========================

Další možností instalace je využití servlet kontejneru (např. Tomcat nebo JBOSS).
Tomcat nebo JBOSS se instaluje pomocí balíčků. GeoServer se pak instaluje nakopírováním
Web Archive (soubor s příponou WAR) do struktur Tomcat nebo JBOSS.

.. note:: Tento způsob instalace GeoServeru není pro začátečníky vhodný.
