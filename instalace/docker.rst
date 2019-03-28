.. |aplikace_ikona| image:: images/aplikace_ikona.png
   :width: 1.5em

.. _label: instalace-docker

.. index::
   single: Docker
   see: Docker; Instalace

Docker
------

Docker slouží k izolaci aplikací do kontejnerů. Kontejner obsahuje pouze aplikaci a soubory k ní. Neobsahuje operační systém. V této kapitole si ukážeme jak nainstalovat Docker v Ububtu 18.04 a rozchodit v něm GeoServer.

Instalace Docker
================
               
.. code-block:: bash
      
	sudo apt update
	sudo apt install apt-transport-https ca-certificates curl software-properties-common
	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
	sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu bionic stable"
	sudo apt update
	sudo apt install docker-ce
	sudo systemctl status docker

Po úspěšné instalaci příkaz vypíše :

Výstup
======             
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

Dále je vhodné přidat svého uživatele do skupiny docker aby spouštění příkazů Dockeru nevyžadovali SUDO

.. code-block:: bash

	sudo usermod -aG docker ${USER}
	su - ${USER}
	id -nG

${USER} nahradíme svým uživatelem.

Instalace kontejneru pro GeoServer
==================================

Když už máme nainstalovaný Docker přistoupíme k instalaci kontejneru pro GeoServer. 

Stažení kontejneru
==================

.. code-block:: bash

	docker pull oscarfonts/geoserver:2.14.1

`:2.14.1` slouží k nastavení verze GeoServeru. Když to spustíme bez `:2.14.1` tak se nainstaluje do Dockeru nejnovější verze GeoServeru.

.. code-block:: bash

	docker run -d -p 8080:8080 -v /path/to/local/data_dir:/var/local/geoserver -v /path/to/local/exts_dir:/var/local/geoserver-exts --name=geoserver oscarfonts/geoserver:2.14.1

-p slouží určení portu. První část určuje port na, kterém běží Geoserver
-v slouží k nastavění umístnění data_dir a exts_dir. Adresáře si můžeme zvolit libovolně. 
--name zadefinuje název kontejneru 

V adresáři `data_dir` jsou uložené data pro GeoServer a v adresáři `exts_dir` jsou uložené pluginy.

Příkazy pro spuštění a zastavění kontejneru
===========================================

.. code-block:: bash

	docker stop geoserver
	docker start geoserver
	docker restart geoserver
