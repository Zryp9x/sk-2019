Zadanie 1
---------

![zadanie 1](zadanie-1.svg)

1. Zaprojektuj oraz przygotuj prototyp rozwiązania z wykorzystaniem oprogramowania ``VirtualBox`` lub podobnego. 
Zaproponuj rozwiązanie spełniające poniższe wymagania:
   * Usługodawca zapewnia domunikację z siecią internet poprzez interfejs ``eth0`` ``PC0``
   * Zapewnij komunikację z siecią internet na poziomie ``LAN1`` oraz ``LAN2``
   * Dokonaj takiego podziału sieci o adresie ``172.22.128.0/17`` aby w ``LAN1`` można było zaadresować ``500`` adresów natomiast w LAN2 ``5000`` adresów    
   * Przygotuj dokumentację powyższej architektury w formie graficznej w programie ``DIA``
 
 
 LAN1:
 
 Maska: 255.255.254.0 /23
 Adres podsieci: 172.22.160.0
 
 LAN2:

 Maska: 255.255.224.0 /19
 Adres podsieci: 172.22.128.0
 
 PC0:
 
 eth0: Połączenie z internetem
 eth1: 172.22.128.1
 eth2: 172.22.160.1
 
 PC1:

 eth0: 172.22.160.2
 
 PC2:
 
 eth0: 172.22.128.3
 
