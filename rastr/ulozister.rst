.. index::
   single: Úložiště rastrových dat

.. _ulozister:

Úložiště rastrových dat
-----------------------

Úložiště WorldImage
===================

Často využívaným úložištěm je rastrový soubor s doplňkovým souborem typu `WorldFile`. 
Např. pro `TIFF` se jedná o soubor `TFW`. Seznam existujících úložišť je možné získat pomocí odkazu 
`Stores` v sekci `Data`. 

.. figure:: images/rstores.png

   Seznam úložišť.
   
Pokud pak následně zvolíme prostor (např. `img_sample2`) uvidíme jeho konfiguraci. 
V rámci této konfigurace je kromně názvu poviná položka URL.
Zde je uvedena cesta k rastrovému souboru. Cesta může být relativní nebo absolutní. 
Relativní cesta začíná v adresáři `data_dir`.

.. note:: Povinné položky jsou označeny červeným kolečkem. Položky, které je vhodné doplnit jsou označeny zeleným kolečkem.

.. figure:: images/rstore.png

   Úložiště img_sample2.
   
.. note:: Začátečníkům se doporučuje používat pouze relativní cesty, zapsané pomocí funkce dostupné pod tlačítkem `Browse`.

Úložiště GeoTIFF
================

Dalším často používaným formátem pro rastrové data je GeoTIFF. Na rozdíl od souboru s doplňkovým souborem typu `WorldFile` je informace o poloze zapsaná přímo do souboru `TIFF`.

Ukázkovým uložištěm pro GeoTIFF je `sfdem`. Všechno nastavění je stejné jako pro `WorldImage`

.. figure:: images/bstores.png

   Úložiště sfdem.
   


