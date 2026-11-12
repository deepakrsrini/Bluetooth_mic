# VoiceCast: Bluetooth Mic

Turn your phone into a microphone for a Bluetooth speaker. VoiceCast is a web app: open it in your phone's browser and it plays your voice live through whatever speaker is connected.

## Features
- **Live or push-to-talk:** tap to stay live, or hold to talk.
- **Volume and mic gain**, with a limiter that protects the speaker.
- **Feedback and echo control**
  - Howl killer: detects the squeal from speaker-to-mic feedback, notches that frequency out and briefly ducks the volume.
  - Noise gate that silences the mic between words.
  - Toggles for the phone's own echo cancellation, noise suppression and auto gain.
- **Voice enhancement:** clarity and compression, pitch shift (±12 semitones), low cut, and bass, presence and air EQ.
- **Effects:** Robot, Alien, Radio and Megaphone voices, plus reverb (with room size) and echo (with time and repeats).
- **Presets:** Natural, Announcer, Stage, Stadium, Deep, Chipmunk and more.
- **Extras:** announcement chime, recording with download, keep-screen-awake, mic and speaker selection, and offline install as a home-screen app.

## Use it
1. Pair your Bluetooth speaker in your phone's settings.
2. Open the app's **HTTPS** link (for example GitHub Pages) in Chrome. Browsers only allow the microphone on HTTPS.
3. Tap the mic button, allow microphone access, and raise the volume slowly.
4. Optional: use the browser menu and choose **Add to Home Screen**.

### Hosting on GitHub Pages
Settings → Pages → Source: *Deploy from a branch* → `main` / `(root)`. The app is then at `https://<user>.github.io/Bluetooth_mic/`.

## Tips
- Keep a few metres between the phone and the speaker, with the speaker pointing away from you. Distance prevents feedback better than any setting.
- Bluetooth adds roughly 100–250 ms of delay that no app can remove. For speeches, use Hold to talk.
- Phone echo cancellation is off by default because on many Android phones it switches Bluetooth into lower-quality "call mode". Turn it on if you still hear echo.
- Works best in Chrome on Android. iOS Safari may send audio to the earpiece while the mic is active.

## Tech
A single static page with no build step and no dependencies. It uses the Web Audio API, with AudioWorklets for the pitch shifter and noise gate, an FFT-based feedback detector driving a bank of notch filters, a ConvolverNode for reverb, and a service worker for offline use.
