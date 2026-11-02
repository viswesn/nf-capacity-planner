# NF Capacity Planner

Plan how many nodes you need to run your xNFs (VNFs and CNFs) on a Red Hat OpenShift (RHOCP) or OpenStack (RHOSP) cluster. See where every instance lands, check what happens when a node or rack fails, and export a nodes-to-order list.

It is a **single HTML file**. There is no server, no build step and no install.

> Your data stays with you. Nothing is sent to or saved on a server. Everything runs in your browser. You can download the page and run it offline on your laptop.

## Quick start

1. Open `nf-capacity-planner.html` in a browser (double-click it, or host it on any web server).
2. A sample plan loads by default. Explore it to see how it works.
3. Click the **trash** icon to clear the sample and start with your own workloads. The **flask** icon reloads the sample.

## What it does

| Area | What you get |
|---|---|
| **Workloads** | Add VNFs and CNFs in a simple or advanced view. Advanced covers NUMA, hugepages, SR-IOV VFs, DPDK, bandwidth, and affinity / anti-affinity rules. |
| **Server profiles** | Define node models: CPU, RAM, OS disk, data disk, NIC speed, hugepages, VFs. |
| **Placement** | NUMA-aware placement. Drag and drop, auto-size, or place the unplaced. Cards and table views, with search, sort, filter and a column chooser. Conflicts are shown as messages under the node. |
| **Utilisation** | Max utilisation %, project buffer %, and "already in use" CPU / RAM / storage for existing nodes. Coloured bars per xNF, with a hover breakdown. |
| **HA check** | N+k spares and a plain-language what-if for node or rack loss, with one-click auto-fix. |
| **Platform nodes** | Control-plane and infra nodes are set by you and included in the order list. |
| **Racks** | Drag and drop equipment, RU fit validation, zoom or fit-to-page, and optional power details (kW, feeds, PDUs). |
| **Nodes to order** | A BoQ with node model, CPU cores, RAM, OS disks and data disks, exportable to Excel. |
| **Themes** | Light and dark. Layout works on desktop and mobile. |

## Import and export

- **JSON**: the full plan. Import it back to continue later.
- **Excel (.xlsx)**: a customer-ready workbook with Dashboard, Brief view, VNF-CNF view, Server detail, Rack view, Rack list, Racks, Nodes to order, Platform nodes, and Site & settings. A hidden `PlanData` sheet lets you re-import the workbook losslessly.
- Export and import are under the icons at the top right.

## Hosting

Copy `nf-capacity-planner.html` to any static host (GitHub Pages, Nginx, Apache, an internal web server).

Optional: put a file named `nf-capacity-planner.json` in the same folder as the HTML. When the page is served over http(s), it loads that plan instead of the built-in sample. This is useful for sharing a prepared plan with your team.

The page keeps your last plan in the browser's local storage, so a refresh does not lose your work. Export JSON if you want to keep or share it.

## Tips

- Drag an xNF chip from the pool onto a node to place it manually.
- Hover over any icon for a short description.
- The "?" icons explain fields in plain language.

## Author

Viswesuwara Nathan S SK, [github.com/viswesn](https://github.com/viswesn)
