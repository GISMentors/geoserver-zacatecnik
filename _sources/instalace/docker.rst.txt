.. |aplikace_ikona| image:: images/aplikace_ikona.png
   :width: 1.5em

.. _label: instalace-docker

.. index::
   single: Docker
   see: Docker; Instalace

Docker
------

Docker slouží k izolaci aplikací do kontejnerů. Kontejner obsahuje
pouze aplikaci a soubory k ní. Neobsahuje operační systém. V této
kapitole si ukážeme, jak nainstalovat Docker v Ubuntu 22.04 a v něm
zprovoznit GeoServer.

Instalace Docker
================
               
.. code-block:: bash

	sudo apt update
	sudo apt install docker.io

Po úspěšné instalaci příkaz vypíše:

.. code-block:: bash

   sudo systemctl status docker
                

.. code-block:: bash

docker.service - Docker Application Container Engine
     Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
     Active: active (running) since Wed 2024-05-22 17:48:51 CEST; 1h 14min ago
TriggeredBy: ● docker.socket
       Docs: https://docs.docker.com
   Main PID: 1601 (dockerd)
      Tasks: 18
     Memory: 103.4M
     CGroup: /system.slice/docker.service
             └─1601 /usr/bin/dockerd -H fd:// --containerd=/run/containerd/containerd.sock

.. tip::                    
   Dále je vhodné přidat běžného uživatele do skupiny ``docker``, aby
   spouštění příkazů Dockeru nevyžadovalo práva ``sudo``.

   .. code-block:: bash

	sudo usermod -aG docker ${USER}
	su - ${USER}
	id -nG
   
Instalace kontejneru pro GeoServer
==================================

Když už máme nainstalovaný Docker, přistoupíme k instalaci kontejneru
pro GeoServer.

Stažení a spuštení kontejneru
=============================

.. code-block:: bash

	docker pull oscarfonts/geoserver:2.25.0

``:2.25.0`` slouží k nastavení verze GeoServeru. Pokud verzi
vynecháme, tak se nainstaluje do Dockeru nejnovější verze GeoServeru.

Spuštění Docker kontejneru:

.. code-block:: bash

	docker run -d -p 8080:8080 -v /opt/geoserver/data_dir:/var/local/geoserver \
        -v /opt/geoserver/exts_dir:/var/local/geoserver-exts \
        --name=geoserver oscarfonts/geoserver:2.25.0

* ``-p`` slouží k určení portu. První část určuje port, na kterém je
  Geoserver posléze dostupný.

* ``-v`` slouží k nastavení umístnění :file:`data_dir` a
  :file:`exts_dir`. Adresáře :file:`/opt/geoserver` jsou umístěny na
  lokálním disku, můžeme je zvolit libovolně.

* ``--name`` určí název kontejneru

.. note::
   V adresáři :file:`data_dir` jsou uložena data pro GeoServer a v
   adresáři :file:`exts_dir` jsou uloženy pluginy (rozšíření).

Instance Geoserveru je posléze dostupná na adrese http://localhost:8080/geoserver/web/

Příkazy pro správu kontejneru
=============================

.. code-block:: bash

	docker stop geoserver
	docker start geoserver
	docker restart geoserver
