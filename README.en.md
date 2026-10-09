*[Español](README.md) · **English***

# SubnetScope

**Plan your network's IPs and VLANs in a single HTML file.** No server, no install, no dependencies — and nothing ever leaves your machine.

Which IP each device has, which VLAN it lives in and how many addresses you have left. One `index.html` you open by double-clicking it in any browser.

It was built to replace the usual IP addressing spreadsheet: the one that is never up to date, where finding a free IP means filtering columns and where nobody writes down the reserved ranges. Here every subnet is drawn as a grid, one cell per IP, so free space is obvious at a glance.

It is the sister tool of **[RackScope](https://github.com/marcosblg/rackscope)**, which documents rack cabling. You can import the devices you already have in RackScope into SubnetScope and assign them IPs without typing them again.

### 👉 [Try it right now in your browser](https://marcosblg.github.io/subnetscope/)

Nothing to install or download: the link opens the tool with a sample office. Hit **▶ Ver demo** for the guided tour.

## What it does

**VLANs and subnets**
- VLANs with ID, name, color and description.
- Subnets in CIDR notation, from /16 to /30, each linked to its VLAN, with optional gateway, DNS servers and DHCP range.
- Validates the CIDR (type `192.168.1.5/24` and it suggests `192.168.1.0/24`) and **warns when two subnets overlap**.

**One cell per IP**
- Every subnet is drawn as a grid, and each cell is colored by state: free, assigned, reserved, DHCP range, gateway, network and broadcast.
- Subnets larger than /24 are split into **collapsible /24 blocks**, each with its own count and usage bar.
- **Click a cell** to open its card: device name, type (server, switch, printer, PC, camera, AP, VM or other), MAC and note, with buttons to assign, reserve or release.
- Hovering already pops up a quick hint with the IP and the device.
- Warns when a MAC or a device name is already used on another IP.

**Know what is left**
- Per-subnet counter: *"87 / 254 used · 167 free"*, excluding the DHCP range.
- **Next free IP** button on every subnet: jumps to it and opens the card.
- **Search** by IP, device name or MAC, highlighting the cell and expanding its block.
- **Multi-select** (click, drag or Shift+click) to reserve or release whole ranges at once.

**Sites or networks**
- A site selector: each one with its own VLANs and subnets, fully independent.

**Bring your devices from RackScope**
- Import a JSON exported from RackScope to get its device list (patch panels and blank spaces are skipped).
- Devices that already have an IP written in RackScope that falls inside one of your subnets get it assigned straight away; the rest go to the **Equipos sin IP** (devices without IP) list, where you assign them one with a single click.

**Get the documentation out**
- **CSV** for Excel with every assigned and reserved IP.
- **PDF** with the VLAN table, a subnet summary and, for each subnet, its grid and IP listing.
- **PNG** image of the grids.
- **JSON** backup.
- Any of them for one site or for all of them at once.

## How to use it

1. Download `index.html` and double-click it.
2. Hit **▶ Ver demo** for a 30-second guided tour.
3. It ships with a sample office (server, user, voice and guest VLANs) to play with. When you want to start for real: **＋** in the site selector → *en blanco* (blank).
4. Create VLANs with **＋ VLAN** and subnets with **＋ Subred** in the left panel.
5. Hit **💾 Archivo** and pick a `.json` of your own: from then on the app rewrites it every time you change something.

## Where the data lives

On your machine and nowhere else. No server, no account, not a single network request. It is stored in the browser's local storage and, if you link a file, in that `.json` you chose.

One important caveat: browser storage is tied to the file's path. Move the HTML or download another copy into a different folder and that storage does not follow. So link a file, or export the JSON now and then. The app shows a red warning if it detects the browser will not let it save.

## What it does not do (yet)

SubnetScope is manual documentation: no network scanning, no ping, no SNMP and no IPv6.

## Compatibility

Tested on Chromium-based browsers (Chrome and Edge). Automatic file saving uses the File System Access API; where that is unavailable, everything still works through JSON export and import.

Note: the interface is in Spanish.

## Status

A personal project, built to solve a real problem at work. Published in case it helps someone else. Suggestions welcome — open an issue describing what you would need.

## License

MIT. Do whatever you want with it.
