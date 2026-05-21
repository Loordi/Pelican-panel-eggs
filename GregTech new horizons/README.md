# GT New Horizons — Pelican Egg

Server egg for GregTech: New Horizons modpack — versions 2.8.0+
Supports Java 17–25

Supports GTNH daily builds.
Requires github token.

This egg automates much of the manual setup described in the official documentation.
just change the version and reinstall to update.

JourneyMapServer data, ops.json, whitelist.json, banned-players.json, banned-ips.json, serverutilities/server/ranks.txt is kept when reinstalled.
REMEMBER TO ENABLE SERVERUTIL RANKS AFTER REINSTALL!
/Files/serverutilities/serverutilities.cfg

⚠️ Always back up your world before reinstalling!

Added version with Twist space technology.
Toggle updating the addon in the env and reinstall

Changes:
05.05.2026
Memory env now deprecated and now this egg uses the containers memory value for the server
Added support for daily builds

10.5.2026
Daily build downloading fixed from expecting double zipped server file
New env for downloading specified daily
Container reserved memory changed from 90% to 95% for gtnh

12.05.2026
Now preserves serverutil ranks, ops, whitelist and banned players on reinstall

21.05.2026
removed serverutilities.cfg from the automatic backup/restore system

---

Pterodactyl version found [here](https://github.com/Loordi/Pterodactyl-eggs/tree/main/GregTech%20new%20horizons)

---

## More Information
- [GTNH Wiki — Server Setup & Update Guide](https://wiki.gtnewhorizons.com/wiki/Server_Setup#Server_Update)
- [GTNH Official Downloads](https://www.gtnewhorizons.com/downloads/)
- [GTNH Discord](https://discord.gg/gtnh)
