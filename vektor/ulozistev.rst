.. index::
   single: Úložiště vektorových dat

.. _ulozistev:

Úložiště vektorových dat
------------------------

Úložiště (`Storage`) slouží k definici datového skladu, ze kterého budou
data publikována.

Před samotnou prací s úložišti je vhodné věnovat pozornost pracovním 
prostorům (`Workspaces`).

Workspaces
==========

Pracovní prostory slouží pro lepší organizaci v rámci serveru. Pro pracovní prostor
je možné definovat samostatná metadata, přístupová práva a další nastavení.

Seznam pracovních prostorů je možné získat pomocí odkazu `Workspaces` v sekci `Data`.

.. figure:: images/workspaces.png

   Seznam pracovních prostorů.
   
Pokud pak následně zvolíme prostor (např. `topp`) uvidíme jeho konfiguraci. 
V rámci této konfigurace je kromně názvu důležitá položka URI. URI jednoznačně
identifikuje prostor v rámci všehomíra. Jako vhodné hodnoty jsou možné téměř 
všechny URL, přičemž daná URL nemusí reálně existovat.

.. figure:: images/workspace.png

   Konfigurace pracovního prostoru.
   
Úložiště ESRI Shapefile
=======================

Často využívaným úložištěm je adresář se soubory typou `ESRI Shapefile`. Seznam
existujících úložišť je možné získat pomocí odkazu `Stores` v sekci `Data`. 

.. figure:: images/stores.png

   Seznam úložišť.
   
Pokud pak následně zvolíme prostor (např. `taz_shapes`) uvidíme jeho konfiguraci. 
V rámci této konfigurace je kromě názvu poviná položka `Shapefile location`.
Zde je uvedena cesta k adresáři se soubory. Cesta může být relativní nebo absolutní. 
Relativní cesta začíná v adresáři `data_dir`.

.. note:: Povinné položky jsou označeny červeným kolečkem. Položky, které je vhodné doplnit jsou označeny zeleným kolečkem.

.. figure:: images/store.png

   Úložiště taz_shapes.
   
.. note:: Začátečníkům se doporučuje používat pouze relativní cesty, zapsané pomocí funkce dostupné pod tlačítkem `Browse`.

Úložiště PostGIS
================

Často využívaným úložištěm je databáze PostgreSQL/PostGIS. Přidání nového
úložiště je možné buď jako PostGIS nebo PostGIS (JNDI). 
.. note:: Varianta JNDI vyžaduje konfiguraci na úrovni aplikačního serveru a pro 
začátečníky není vhodná. Navíc testy ukázaly, že je připojení přes JNDI o něco pomalejší. 
Vhodné je v případě, že již organizace JNDI běžně využívá.

.. figure:: images/storepostgis1.png

   PostGIS úložiště.
   
Základní konfigurace úložiště je poměrně jednoduchá. Povinné položky jsou již předvyplněny a 
hodnoty obvykle vyhovují požadavkům. Nutné je pouze úložiště pojmenovat `Data Source Name` a 
správně uvést název databáze `database`, uživatele `user` a heslo `passwd` do databáze.
Někdy je potřeba změnit jméno serveru `host`, kde databázový server běží a někdy port `port` na kterém naslouchá.

.. note:: Povinné položky jsou označeny červeným kolečkem. Položky, které je vhodné doplnit jsou označeny zeleným kolečkem.

.. figure:: images/storepostgis2.png

   Definice PostGIS úložiště.
   



