## Wyszukanie plików zawierających tekst
`grep -iRl "your-text-to-find" ./`

## Wypisywanie maszyn
vboxmanage list vms

## Usuwanie mszyn
vboxmanage unregistervm Vm1 --delete

# Laby 2

## Maszyna
Utworzyłem maszynę w domu na Widowsie. Dzięki temu, że połączenie jest mostkowe dostała ona adres IP i da się ją zpingować.
Po odpaleniu maszyna nie miała przypisanego adresu ip.
By to zmienić pobrałem adres ip od serwera dhcp poleceniem `dhclient em0`
W celu podłączenie się ssh trzeba zmienić ustawienia systemu.
Trzeba wygenerować klucze poleceniem `ssh-keygen -A` oraz dodać do pliku /etc/rc.conf linię sshd_enable="YES"  
Wtedy możliwe jest uruchomienie demona ssh poleceniem `service sshd restart`

## Tworzenie sieci
Polecenie `ifconfig bridge create` utworzyło wirtualny mostek o nazwie bridge0.  
Przy pomocy polecenia `ifconfig bridge0 addm em0` podłączyłem interfejs fizyczny do mostka.

Utworzenie dwóch interfejsów e-pair `ifconfig epair create`.