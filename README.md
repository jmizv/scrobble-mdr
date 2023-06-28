# Scrobble-MDR

🕳 **This is just a placeholder repository. Find the source code at [codeberg.de](https://codeberg.org/jmizv/scrobble-mdr)**.

This small application will simply retrieve the recent played tracks from the official
[MDR Sachsen-Anhalt](https://www.mdr.de/mdr-sachsen-anhalt/)
"[Titelliste](https://www.mdr.de/mdr-sachsen-anhalt/titelliste-mdr-sachsen-anhalt--102.html)",
put them in a PostgreSQL database and transfer (i.e. scrobble) them to the [unofficial last.fm
page](https://last.fm/user/mdrsaxenanhalt) for that radio station. Note that the username was chosen
because of length limitations.

This app is based on Spring Boot. It consumes the REST API at https://www.mdr.de/scripts4/titellisten/xmlresp-index.do

This development and the last.fm account are in no way affiliated with MDR and MDR Sachsen-Anhalt.

## Why?

1) If you have a last.fm account yourself, you can easily see how compatible the played music
is to your own scrobbled. For me, it is *low*.
2) Probably a statistic issue: which artists has been played most by that station. For now,
these are ABBA (33x) and the Bee Gees (28x). Let's see how this evolves over time.

## How?

- you need an API key from last.fm with the corresponding secret
- the user needs to authenticate the app with that API key which results in a token
- with that token a session key can be generated which will be used later to call other
API functions.
