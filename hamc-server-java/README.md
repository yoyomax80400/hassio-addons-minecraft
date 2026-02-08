# 🧱 HAMC Server Java (Home Assistant Add-on)

Host a fully configurable **Minecraft Java Server** directly inside **Home Assistant**.

Supports vanilla and major server types, plus compatibility with web-based mods like **BlueMap**, **Dynmap**, and analytics tools like **Plan**.

---

## ✨ Features

* 🎮 Minecraft Java server inside Home Assistant
* 🧩 Supports multiple server types:

  * Vanilla
  * Fabric
  * Forge
  * Paper / Spigot / Bukkit
  * Quilt, Mohist, Magma, etc.

* 🗺️ Compatible with **BlueMap** and **Dynmap**
* 📊 Compatible with **Plan analytics**
* 🛠️ RCON support
* 🔧 Full server.properties configuration via add-on options
* 🌐 Customizable exposed ports for web mods \& services

---

## 🔌 Exposed Ports

|Port|Usage|
|-|-|
|**25565**|Minecraft game server|
|**25575**|RCON remote console|
|**8100**|BlueMap 3D web map|
|**8123**|Dynmap web map|
|**8800**|Plan analytics dashboard|
|8080 / 9000|Generic web UI ports for mods|
|30000–31001|Extra ports for custom services|

Ports marked configurable in Home Assistant can be changed in the **Network** tab of the add-on.

---

## ⚙️ Configuration

All main `server.properties` values can be configured directly in the add-on options.

Example:

```yaml
TYPE: FABRIC
VERSION: 1.20.4
MODE: survival
DIFFICULTY: hard
MAX\_PLAYERS: 20
MEMORY: 2G
```

---

## 🗺️ Using BlueMap

1. Install Fabric server type
2. Add BlueMap mod to `/addons/hamc-java/data/mods`
3. Ensure BlueMap config uses:

```yaml
ip: 0.0.0.0
port: 8100
```

4. Expose port **8100** in the add-on network settings
5. Open in browser:

```
http://HOME\_ASSISTANT\_IP:8100
```

---

## 🧭 Using Dynmap

1. Use Paper/Spigot server type
2. Install Dynmap plugin
3. Default port:

```
8123
```

Access:

```
http://HOME\_ASSISTANT\_IP:8123
```

---

## 🛠️ RCON

Enable RCON in options:

```yaml
RCON\_PASSWORD: "your\_password"
```

Default port: **25575**

---

## 📂 Data Location

|Path in container|Description|
|-|-|
|`/data`|Server files, worlds, mods, plugins|
|`/hassio\_data`|Persistent storage|

---

## ⚠️ Notes

* Mods/plugins must listen on **0.0.0.0**, not `127.0.0.1`
* Ports must be exposed in Home Assistant to be reachable
* Large modpacks require increasing memory

---

## 🧩 Supported Architectures

* amd64
* aarch64
* armv7

---

## ❤️ Credits

Fork Based on the Home Assistant Add-on : https://github.com/williamcorsel/hassio-addons

---

## 🧑‍💻 Maintainer

Replace with your GitHub username


