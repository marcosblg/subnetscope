***Español** · English below*

# Novedades de SubnetScope

## v1.2 — 13 de octubre de 2026

Pedido en los comentarios: ver qué IPs están prestadas de verdad y qué VLAN va más cargada.

- **Concesiones DHCP**: importa las que exportes de tu servidor (Windows Server con `Export-Csv`, pfSense o Linux con `dhcpd.leases`, MikroTik, Kea o un CSV genérico). Las IPs prestadas se ven en la cuadrícula con su equipo, MAC y caducidad, aparecen en el buscador y en el CSV, y "Siguiente IP libre" se las salta. No se conecta al servidor.
- Avisa si el DHCP ha prestado una IP documentada como fija para otro equipo (posible conflicto) y si las concesiones llevan más de un día sin actualizarse.
- **Carga por VLAN**: porcentaje de IPs ocupadas de cada VLAN, con orden de más a menos cargada y aviso a partir del 80 %.
- Corregida una errata en el contador de direcciones IPv6.

## v1.1 — 11 de octubre de 2026

Lo más pedido en los comentarios del lanzamiento. ¡Gracias!

- **IPv6 en doble pila**: cada subred puede llevar su prefijo IPv6 y su puerta de enlace, con una lista de direcciones IPv6 fijas (equipo, tipo, MAC y nota). La ficha de una IPv4 muestra también las IPv6 del mismo equipo.
- **Plan IPv6**: a partir del /48 o /56 del operador se propone un /64 para cada subred, usando el ID de VLAN cuando se puede. Sirve también de calculadora de prefijos.
- **Reglas NAT documentadas**: IP y puerto públicos → IP interna, con protocolo y descripción. Las IPs publicadas llevan una marca en la cuadrícula, su ficha muestra sus reglas y se avisa si dos reglas usan el mismo puerto público o si una apunta a una IP sin documentar.
- El buscador, el CSV y el PDF incluyen las direcciones IPv6 y las reglas NAT, que tienen además su propio CSV.

Los datos de la v1.0 se cargan tal cual.

## v1.0 — 9 de octubre de 2026

Primera versión pública.

- Sedes o redes independientes, VLANs con ID, nombre, color y descripción, y subredes CIDR de /16 a /30 con validación y aviso de solapes.
- Una casilla por IP con su estado (libre, asignada, reservada, DHCP, puerta de enlace, red y broadcast); las subredes mayores de /24, en bloques /24 plegables.
- Ficha por IP con equipo, tipo, MAC, nota e historial; se arrastra si tapa algo.
- Contador por subred, siguiente IP libre, buscador por IP, nombre o MAC y selección múltiple para reservar o liberar rangos.
- Dividir subredes, con vista previa que hace de calculadora.
- Importa los equipos de RackScope y le devuelve las IPs.
- Exportación a CSV, PDF, PNG y JSON, y guardado automático en un archivo vinculado.
- Red de ejemplo y demo guiada de 30 segundos.

---

# What's new in SubnetScope

## v1.2 — October 13, 2026

Requested in the comments: see which IPs are really handed out and which VLAN is busiest.

- **DHCP leases**: import them from your server's export (Windows Server `Export-Csv`, pfSense or Linux `dhcpd.leases`, MikroTik, Kea or a generic CSV). Leased IPs show on the grid with device, MAC and expiry, appear in search and CSV, and "next free IP" skips them. It never connects to the server.
- Warns when DHCP has leased an IP documented as static for another device (possible conflict) and when the leases are more than a day old.
- **VLAN load**: percentage of used IPs per VLAN, sortable from most to least loaded, with a warning from 80 %.

## v1.1 — October 11, 2026

The most requested features from the launch comments. Thank you!

- **Dual-stack IPv6**: every subnet can carry its IPv6 prefix and gateway, with a list of static IPv6 addresses (device, type, MAC and note). An IPv4 card also shows the same device's IPv6 addresses.
- **IPv6 plan**: from your ISP's /48 or /56 it proposes a /64 for each subnet, using the VLAN ID where possible. It doubles as a prefix calculator.
- **Documented NAT rules**: public IP and port → internal IP, with protocol and description. Published IPs get a mark on the grid, their card lists their rules, and you are warned when two rules share a public port or one points to an undocumented IP.
- Search, CSV and PDF include IPv6 addresses and NAT rules, which also get their own CSV.

Data from v1.0 loads as is.

## v1.0 — October 9, 2026

First public release.

- Independent sites or networks, VLANs with ID, name, color and description, and CIDR subnets from /16 to /30 with validation and overlap warnings.
- One cell per IP with its state (free, assigned, reserved, DHCP, gateway, network and broadcast); subnets larger than /24 split into collapsible /24 blocks.
- Per-IP card with device, type, MAC, note and history; drag it aside if it covers something.
- Per-subnet counter, next free IP, search by IP, name or MAC, and multi-select to reserve or release ranges.
- Subnet splitting, with a preview that doubles as a calculator.
- Imports devices from RackScope and sends the IPs back.
- Export to CSV, PDF, PNG and JSON, plus automatic saving to a linked file.
- Sample network and 30-second guided demo.
