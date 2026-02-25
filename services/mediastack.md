# Media Stack
- Sonarr[:30113] / Radarr [:30025]
	Watches and detects missing episodes, and waits for new ones to come out.

- Prowlarr [:30050]
	Manages searches and torrent sites for use by Sonarr and Radarr.  Once Sonarr or Radarr finds missing episodes it tells Prowlarr.

- QBtorrent [pi:8080]
	Prowlarr sends the torrents to QBTorrent on a seperate Raspberry Pi.  This Pi starts the torrent download and writes it to the TrueNAS media downloads folder.

- Jellyfin [:30013]
	Streams media to the jellyfin web interface or jellyfin apps on TVs and phones.  
	Public access routed via Cloudflare DNS > Nginx reverse proxy > TrueNAS.