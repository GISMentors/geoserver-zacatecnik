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
kapitole si ukážeme, jak nainstalovat Docker v Ubuntu 18.04 a v něm
zprovoznit GeoServer.

Instalace Docker
================
               
.. code-block:: bash
      
	sudo apt install apt-transport-https ca-certificates curl software-properties-common
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
	sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
	sudo apt update
	sudo apt install docker-ce

Po úspěšné instalaci příkaz vypíše:

.. code-block:: bash

   sudo systemctl status docker
                

.. code-block:: bash

	● docker.service - Docker Application Container Engine
	   Loaded: loaded (/lib/systemd/system/docker.service; enabled; vendor preset: enabled)
	   Active: active (running) since Thu 2018-07-05 15:08:39 UTC; 2min 55s ago
	     Docs: https://docs.docker.com
	  Main PID: 10096 (dockerd)
	     Tasks: 16
   	    CGroup: /system.slice/docker.service
           	    ├─10096 /usr/bin/dockerd -H fd://
          	    └─10113 docker-containerd --config /var/run/docker/containerd/containerd.toml

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

	docker pull oscarfonts/geoserver:2.19.3

``:2.19.3`` slouží k nastavení verze GeoServeru. Pokud verzi
vynecháme, tak se nainstaluje do Dockeru nejnovější verze GeoServeru.

Spuštění Docker kontejneru:

.. code-block:: bash

	docker run -d -p 8080:8080 -v /opt/geoserver/data_dir:/var/local/geoserver \
        -v /opt/geoserver/exts_dir:/var/local/geoserver-exts \
        --name=geoserver oscarfonts/geoserver:2.19.3

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
