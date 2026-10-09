***Español** · [English](README.en.md)*

# SubnetScope

**Planifica las IPs y VLANs de tu red en un solo archivo HTML.** Sin servidor, sin instalación y sin que salga un dato de tu equipo.

Qué IP tiene cada equipo, en qué VLAN está y cuántas te quedan libres. Un único archivo `index.html` que se abre con doble clic en cualquier navegador.

Nació para sustituir la típica hoja de cálculo de direccionamiento: la que nunca está al día, en la que hay que filtrar para encontrar una IP libre y donde nadie apunta los rangos reservados. Aquí cada subred se ve como una cuadrícula, una casilla por IP, y lo libre se ve a simple vista.

Es la herramienta hermana de **[RackScope](https://github.com/marcosblg/rackscope)**, que documenta el cableado de los racks. Puedes importar en SubnetScope los equipos que ya tengas en RackScope y darles IP sin volver a teclearlos.

### 👉 [Pruébalo ahora en el navegador](https://marcosblg.github.io/subnetscope/)

No hay que instalar ni descargar nada: el enlace abre la herramienta con una oficina de ejemplo. Pulsa **▶ Ver demo** para la visita guiada.

## Qué hace

**VLANs y subredes**
- VLANs con ID, nombre, color y descripción.
- Subredes en notación CIDR, de /16 a /30, cada una asociada a su VLAN, con puerta de enlace, DNS y rango DHCP opcionales.
- Comprueba que el CIDR es correcto (si escribes `192.168.1.5/24` te propone `192.168.1.0/24`) y **avisa si dos subredes se solapan**.

**Una casilla por IP**
- Cada subred se dibuja como una cuadrícula y cada casilla tiene el color de su estado: libre, asignada, reservada, rango DHCP, puerta de enlace, red y broadcast.
- Las subredes mayores de /24 se parten en **bloques /24 plegables**, cada uno con su recuento y su barra de uso.
- **Clic en una casilla** y se abre su ficha: nombre del equipo, tipo (servidor, switch, impresora, PC, cámara, AP, VM u otro), MAC y nota, con botones para asignar, reservar o liberar.
- Al pasar el ratón por encima ya sale un aviso rápido con la IP y el equipo.
- Avisa si repites una MAC o un nombre de equipo en otra IP.

**Saber qué te queda**
- Contador por subred: *"87 / 254 usadas · quedan 167 libres"*, descontando el rango DHCP.
- Botón **Siguiente IP libre** en cada subred: te lleva a ella y abre la ficha.
- **Buscador** por IP, nombre de equipo o MAC, que resalta la casilla y despliega su bloque.
- **Selección múltiple** (clic, arrastrar o Shift+clic) para reservar o liberar rangos enteros de golpe.

**Sedes o redes**
- Desplegable de sedes: cada una con sus VLANs y subredes, independientes.

**Traer los equipos de RackScope**
- Importa el JSON exportado de RackScope y saca la lista de equipos (sin paneles de parcheo ni huecos).
- Los que ya tienen una IP escrita en RackScope que cae en una de tus subredes se asignan solos; el resto queda en la lista **Equipos sin IP**, desde donde les das IP con un clic.

**Sacar la documentación fuera**
- **CSV** para Excel con todas las IPs asignadas y reservadas.
- **PDF** con la tabla de VLANs, el resumen de subredes y, por cada subred, su cuadrícula y el listado de IPs.
- Imagen **PNG** de las cuadrículas.
- **JSON** de copia de seguridad.
- Todo ello de una sede o de todas a la vez.

## Cómo se usa

1. Descarga `index.html` y ábrelo con doble clic. También puedes probarlo sin descargar nada desde la demo en línea.
2. Pulsa **▶ Ver demo** para una visita guiada de 30 segundos por las funciones.
3. Viene con una oficina de ejemplo (VLANs de servidores, usuarios, voz e invitados) para trastear. Cuando quieras empezar en serio: **＋** en el desplegable de sedes → *en blanco*.
4. Crea las VLAN con **＋ VLAN** y las subredes con **＋ Subred** en el panel de la izquierda.
5. Pulsa **💾 Archivo** y elige un `.json` tuyo: a partir de ahí la aplicación lo reescribe sola cada vez que cambias algo.

## Dónde se guardan los datos

En tu equipo y en ningún sitio más. No hay servidor, no hay cuenta y no sale una sola petición a Internet. Se guarda en el almacenamiento local del navegador y, si vinculas un archivo, en ese `.json` que eliges tú.

Un aviso importante: el almacenamiento del navegador va atado a la ruta del archivo. Si mueves el HTML o te descargas otra copia en otra carpeta, ese almacén no viaja contigo. Por eso conviene vincular un archivo o exportar el JSON de vez en cuando. La aplicación avisa en rojo si detecta que el navegador no le deja guardar.

## Qué no hace (todavía)

SubnetScope es documentación manual: no escanea la red, no hace ping, no consulta SNMP y no trabaja con IPv6.

## Compatibilidad

Probado en navegadores basados en Chromium (Chrome y Edge). El guardado automático en archivo usa la File System Access API; donde no esté disponible, funciona igual con exportar e importar JSON.

## Estado

Proyecto personal, hecho para resolver un problema real de trabajo. Se publica por si le sirve a alguien más. Las sugerencias son bienvenidas: abre un *issue* contando qué necesitarías.

## Licencia

MIT. Haz lo que quieras con él.
