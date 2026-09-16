# neoradio

**Version 1.0.2**

neoradio is an internet radio tuner that looks like the radio in an old car.
It has two knobs, a volume control, a power switch, and an amber dot-matrix
display. You turn the left knob to choose a type of radio. You turn the right
knob to move through the stations.

The whole app is one HTML file. There is nothing to install and nothing to
set up.

---

## How to use it

1. Press the **Power** switch. The display comes on.
2. Turn the **Source** knob (left) to choose what you want to hear.
3. Turn the **Channel** knob (right) to move through the stations.
4. Set the level with the **Volume** control.

You can turn a knob in three ways:

- **Drag** it with a mouse or a finger.
- **Scroll** the mouse wheel over it.
- **Click** it, then use the arrow keys.

Each step gives a small click, and the needle moves along the scale.

### What you hear between stations

The hiss between stations is not a fault. neoradio makes the sound to give
the feel of an analog tuner. The hiss becomes quiet when a station starts.

### Dead stations

Internet stations go down often. If a station does not answer, neoradio
steps over it and tries the next one. The display shows
`DEAD CHANNEL - SKIPPING` while it does this. If it cannot find a station
that works, it shows `NO SIGNAL - TURN THE KNOB`.

When you switch the power on again, neoradio gives every station a new
chance.

### The display

The top line shows the type of radio. The bottom line shows the station
name, or what the tuner is doing:

| Message | Meaning |
|---|---|
| `LOADING...` | neoradio is getting the station list. |
| `TUNING...` | neoradio is opening the station. |
| `BUFFERING...` | The stream stopped for a moment. |
| `READING FILE LIST...` | neoradio is getting the recordings for this channel. |
| `DEAD CHANNEL - SKIPPING` | The station did not answer. |
| `NO TRAFFIC - LISTENING` | A scanner channel is quiet. It will play the next call. |
| `NO SIGNAL - TURN THE KNOB` | No station on this list answered. |

---

## The eleven dial positions

| # | Position | What it plays |
|---|---|---|
| 1 | LOCAL FM | Popular stations from your country. |
| 2 | WORLD | Popular stations from everywhere. |
| 3 | SHORTWAVE | International broadcasters. |
| 4 | PUBLIC SAFETY | Recent police and fire radio calls, played in order. |
| 5 | WEATHER | Weather services and forecast channels. |
| 6 | HAM UTILITY | Amateur radio relays. |
| 7 | AIRBAND | Air traffic control feeds. |
| 8 | SOMA FM | The SomaFM music channels. |
| 9 | OLD TIME RADIO | Radio drama and comedy from the 1930s to the 1950s. |
| 10 | NUMBERS | Recordings of shortwave numbers stations. |
| 11 | SPACE | Space agency and astronomy channels. |

neoradio finds your country from your browser language. It does not ask for
your location.

---

## How to run it

Open `neoradio-v1.0.2.html` in a browser. That is all.

You can also put the file on a web server and open it as a web page.

**One point about web servers:** a secure page (`https://`) cannot play a
stream that is not secure (`http://`). neoradio hides these stations when you
open it from an `https://` address, so you will see fewer stations than you
see from the file on your disk. This is a browser rule, not a fault in
neoradio.

### What your browser needs

Any current version of Chrome, Edge, Firefox or Safari, on a computer, a
phone or a tablet. neoradio adjusts its layout for small screens.

On a phone, the lock screen and headset buttons control play, pause, and the
next and previous station.

---

## Privacy

neoradio keeps nothing.

- It writes no cookies and no data to your browser.
- It has no accounts and no sign-in.
- It collects no statistics and sends nothing to its own server.
- The station lists stay in memory for the visit only. When you close the
  page, they are gone.

Your browser connects directly to each station. The site that gives you the
neoradio page never sees or handles the audio.

---

## Sources and attribution

neoradio plays nothing of its own. Every station comes from one of four
public services. These services pay for the data and the bandwidth. Please
support them.

The footer of the app shows the service for the position on the dial, and
links to it.

### SomaFM

<https://somafm.com/>

SomaFM is a listener-supported radio station from San Francisco. It has run
since 2000 with no advertisements. It publishes a public channel list for
other players to use.

neoradio uses:
- `https://somafm.com/channels.json` — the channel list
- `https://somafm.com/songs/{channel}.json` — the song that is playing now

**SomaFM runs on donations.** If you listen, please give:
<https://somafm.com/support/>

### Radio Browser

<https://www.radio-browser.info/>

Radio Browser is a free, community-built database of internet radio stations.
It is in the public domain. Volunteers add and check the stations.

neoradio uses:
- `https://all.api.radio-browser.info/json/servers` — to find a server
- `/json/stations/search` — to search for stations
- `/json/url/{uuid}` — to report which station you chose

The last one matters. Radio Browser sorts stations by how often people choose
them. neoradio reports each choice, so your listening helps keep the database
in order.

Support Radio Browser: <https://www.radio-browser.info/users>

### Internet Archive

<https://archive.org/>

The Internet Archive is a non-profit digital library. It holds the old time
radio recordings and the numbers station recordings.

neoradio uses:
- `https://archive.org/advancedsearch.php` — to find collections
- `https://archive.org/metadata/{id}` — to get the recordings in a collection

The recordings in these collections are in the public domain or are shared
under an open licence by the people who uploaded them.

Support the Internet Archive: <https://archive.org/donate>

### OpenMHz

<https://openmhz.com/>

OpenMHz collects and shares recordings from trunked public safety radio
systems. Volunteers run the receivers.

neoradio uses:
- `https://api.openmhz.com/systems` — the list of radio systems
- `https://api.openmhz.com/{system}/calls` — the recent calls

If OpenMHz does not answer, neoradio falls back to scanner relays from Radio
Browser.

---

## How neoradio treats the streams

This is important, so it is stated plainly.

neoradio **hotlinks**. It gives the station address to your browser, and your
browser connects to the station. neoradio does not:

- copy the audio,
- record the audio,
- change the audio to a different format,
- send the audio on to other people,
- or remove the name of the station.

This is the same thing your browser does with a picture on a web page. The
station sees a usual listener and counts it in its own statistics.

The name of the service and the name of the station are always on the
display, so it is clear who you are listening to.

---

## Known limits

- **Dead stations.** About one internet station in six is down at any moment.
  This is normal. neoradio steps over them.
- **Fewer stations over HTTPS.** See *How to run it* above.
- **No search.** You turn the knob. That is the point of the design.
- **No presets.** neoradio keeps nothing between visits, so it cannot store
  them.
- **No recording.** neoradio is for listening only.
- **The signal needle** shows your position in the station list. It does not
  show a real signal strength. A browser cannot measure one.

---

## For developers

One file. No build step. No dependencies. No framework.

The source is in eleven numbered sections with comments. The parts you are
most likely to want:

| Section | Holds |
|---|---|
| 2 | The dial positions and the search recipes. |
| 4 | The service adapters. |
| 5 | The audio engine, the queue, and the dead-station logic. |
| 6 | The knobs. |
| 7 | The dot-matrix display. |

To add a dial position, add one entry to `SOURCES`. If it uses a service that
is already there, it gets its footer credit with no other change.

To change the level of the tuning hiss, set `NOISE_TRIM` in section 5.

---

## Licence and disclaimer

Each station, recording and call belongs to the service
that provides it and to the people who made it. Read the terms of each
service before you put neoradio on a public site. SomaFM in particular asks
that you credit it and that you do not remove its name.

neoradio is not connected to SomaFM, Radio Browser, the Internet Archive or
OpenMHz.
