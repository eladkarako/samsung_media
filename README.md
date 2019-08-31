# samsung_media
/system/media/audio
from Samsung Galaxy S4 (Android 5.1), from Samsung Galaxy S8+ (Android 7), from Samsung J400F (Android 9).

note that there are sometimes newer/older variation,
for example `Highlight.ogg` and `Highlight (2).ogg`.
the `(2)` is the older one (from Galaxy S4).

keep you favorite, if you want the second variation,
delete `Highlight.ogg` and rename `Highlight (2).ogg` to `Highlight.ogg`.

you need to modify the premissions to `0644` and owner/group to `(0) root` as explained in `http://icompile.eladkarako.com/android-custom-ringtone/`, and after two reboots it will be available in the ringtone selection screen(s).

<hr/>

Making "real" ringtone/notification (with an optional increased-volume, using FFMPEG)
<ol>
<li>
Get a media-file (video/audio) from YouTube for example (<code>video.mp4</code>).
</li>
<li>
Convert it to an <code>OGG</code> audio file, with a meaningful name: <code>ffmpeg -i video.mp4 -vn -sn -dn bubbles.ogg</code>
</li>
<li>
<strong>Optional:</strong> <br/>
increase its volume x4: <code>ffmpeg -i bubbles.ogg -filter:a "volume=4.0" bubbles4.ogg</code> <br/>
<sub>also, rename delete the old <code>bubbles.ogg</code> and rename <code>bubbles4.ogg</code> to <code>bubbles.ogg</code> .</sub>
</li>
<li>
Download Mp3tag from https://www.mp3tag.de/en/download.html <br/>
You can use 7-Zip (https://github.com/mcmilk/7-Zip-zstd/releases) to extract the content of the EXE without installing it.
</li>
<li>
A <strong>ringtone</strong> should have <strong>only</strong> those extended-tags:
<pre>
  ALBUM             Samsung
  ANDROID_LOOP      true
  ARTIST            Samsung
  COMMENT           Samsung
  GENRE             Ringtone
  TITLE             Bubbles
</pre>
A <strong>notification</strong> audio should have <strong>only</strong> those extended-tags:
<pre>
  ALBUM             Samsung
  ARTIST            Samsung
  COMMENT           Samsung
  GENRE             Alert Tone
  TITLE             Bubbles
</pre>

What that is written under <code>TITLE</code> will be shown in Samsung's UI not the filename, <br/>
so you can name your audio-file anything - better not use spaces, but use underscore, <br/>
and under <code>TITLE</code> write a more readable (with spaces) version, of the filename, for example.
</li>
<li>
You don't have to have ROOT-permissions on your phone, <br/>
create (if not already exist) a folder named <code>Notifications</code> under your internal-storage and copy your custom notification audio-file under there, <br/>
create (if not already exist) a folder named <code>Ringtones</code> under your internal-storage and copy your custom ringtone audio-file under there. <br/>
</li>
<li>
Reboot your device, and you'll find the new-entires under your device audio-settings.
</li>
</ol>