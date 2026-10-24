## Troubleshooting: 

### This is NOT easy stuff! It will be rough-going at times to get things set up and running consistently. Here are some troubleshooting things to try:

## System can't find the RX-888
### Common causes with an RX888:

- RX888 not detected. It’s unplugged, on a USB 2 port, or on a weak hub. It needs a USB 3 port, the blue one.
- Firmware file missing. radiod loads firmware onto the RX888 at startup and stops if it can’t find the file.
- Config error in /etc/radio/radiod@rx888-wsprdaemon.conf, often in the external clock (GPSDO) settings.

- Often the reason is simply that the PC and the RX-888 have stopped talking to each other via USB. This is a know issue with the RX-888 that it occasionally does this. Best fix is to pull the USB cord, wait a minute and plug it back into ANOTHER USB-3 (blue) port. That usually fixes that problem. If it happens again, pull it, wait 60 secs and plug it back into the original USB-3 (blue) port. Dumb but so what as long as it works!

## ka9q-web won't load / radiod keeps restarting

### Symptoms

You may see one or more of these, often at the same time:

- wsprdaemon reports: `start_systemctl_daemon() wsprdaemon.service is not running`
- The ka9q-web page at `http://<psws-ip>:8081` won't load
- `curl http://localhost:8081` returns **Connection refused**, even though the `ka9q-web` process is running
- radiod shows `activating auto-restart` instead of `active running`

These look like separate problems, but they usually have **one root cause**: radiod can't keep the RX888 running. ka9q-web waits for radiod's status stream (`hf-status.local`) before it opens port 8081, so when radiod is down, the web page is down too.

### Step 1 — Check radiod first

```bash
systemctl list-units 'radiod@*'
```

- **`active running`**: radiod is healthy. Skip to Step 4.
- **`activating auto-restart`**: radiod is crash-looping. Continue to Step 2.

### Step 2 — Read the radiod log

```bash
journalctl -u radiod@rx888-wsprdaemon -n 40 --no-pager
```

Look for the line where radiod finds the RX888. A healthy start shows:

```
found rx888 ... product 'RX888mk2' ... USB speed: Super (5 Gb/s)
...
rx888 running
45 static demodulators started
```

If the USB speed is **not** `Super (5 Gb/s)`, or the RX888 isn't found at all, the USB connection is the problem.

> **Note:** A line saying `wisdom-fftw-...-threaded not readable` is harmless and can be ignored.

### Step 3 — Fix the USB connection

The RX888 MkII needs a solid **USB 3** connection. Not every USB 3 port on a mini PC performs equally.

1. Move the RX888 to a different USB 3 port (usually the blue ones), connected directly to the PC with no hub.
2. Check radiod again after a minute:
   ```bash
   systemctl list-units 'radiod@*'
   ```
   It should show `active running` and stay that way.

**On the Beelink SER mini PC, moving the RX888 to a different USB port resolved the crash loop.**

### Step 4 — Restart ka9q-web and the wsprdaemon watchdog

ka9q-web may be stuck from when radiod was down. Restart it:

```bash
pgrep -a ka9q-web              # note the process ID
sudo kill <PID>
wd -z && wd -a                 # restart the wsprdaemon watchdog, which restarts ka9q-web
wd -A                          # (first time only) enable wsprdaemon as a service at boot
```

Wait about 30 seconds, then confirm:

```bash
curl -s http://localhost:8081 | head -5
```

If HTML comes back, open `http://<psws-ip>:8081` in a browser on your LAN to see the waterfall.

### Still not reachable from another computer?

If it works on the PSWS itself but not from other machines, check the firewall:

```bash
sudo ufw status
sudo ufw allow 8081/tcp        # only if ufw is active and 8081 isn't listed
```

### Quick reference

| Command | Purpose |
|---|---|
| `systemctl list-units 'radiod@*'` | Is radiod running? |
| `journalctl -u radiod@rx888-wsprdaemon -n 40 --no-pager` | Why is radiod failing? |
| `pgrep -a ka9q-web` | Is ka9q-web running, and on which port? |
| `curl -s http://localhost:8081 \| head -5` | Is ka9q-web actually serving pages? |
| `wd -a` / `wd -z` / `wd -s` | Start / stop / status of the wsprdaemon watchdog |
| `wd -A` | Enable wsprdaemon at boot |


