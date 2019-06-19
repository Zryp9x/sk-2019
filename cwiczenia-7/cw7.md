
Zadanie
------------

![zadanie 7](nat-2.svg)

2. 
    * Przygotuj konfigurację sieci zgodnie z powyższym diagramem
    * Wykonaj konfigurację translacji adresów tak aby udostępnic komunikację z siecią internet dla ``PC-2`` oraz ``PC-3``
    
3. 
    * Rozszerz architekturę o automatyczną konfigurację hostów w podsieciach ``192.168.64.192/27`` oraz ``172.16.95.216/29`` z wyykorzystaniem usługi ``DHCP``
    * Rozpocznij od zapoznania się z dokumentacją oraz instalacji programu ``isc-dhcp-server`` dla ``PC1``

 
 ## Tworzymy 2 sieci NAT
192.168.64.192/27
172.16.95.216/29
## W PC1 ustawiamy:

enp0s8 - 192.168.64.193/27
enp0s3 - NAT
enp0s9 - 172.16.95.217/29

## W PC2 ustawiamy:
enp0s3 - 192.168.64.194/27

## W PC3 ustawiamy:
enp0s3 - 172.16.95.218/29

## na PC1 ustawiamy forwarding i udostepniamy internet:
echo 1 > /proc/sys/net/ipv4/ip_forward
iptables -t nat -A POSTROUTING -o enp0s3 -j MASQUERADE

## na PC2 ustwiamy routing:

ip route add default via 192.168.64.193 dev enp0s3

## na PC3 ustwiamy routing:

ip route add default via 172.16.95.217 dev enp0s3
