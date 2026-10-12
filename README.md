# Moss Kettle

A cozy idle game about a sleepy teapot. Tap it to steep tea, fill a lamp-lit nook with little helpers, make friends with the animals who stop by, and let the kettle keep brewing while you are away.

It is a single web page that installs to your phone's Home Screen like an app. There is nothing to download from an app store, no account, no ads, and no tracking. Your game is saved on your own device.

## Play it

**Live game:** `https://YOUR-USERNAME.github.io/moss-kettle/`

### Install on iPhone or iPad

1. Open the link above in **Safari**. Other browsers on iOS cannot add apps to the Home Screen.
2. Tap the **Share** button.
3. Tap **Add to Home Screen**, then **Add**.
4. Open Moss Kettle from your Home Screen. It runs full screen and works offline.

### Install on Android

1. Open the link in **Chrome**.
2. Tap the **three-dot menu**, then **Install app** (or **Add to Home screen**).

### On a computer

Just open the link in any modern browser. It works fine there too, but it is designed for phones.

## How to play

### The basics

- **Tap the teapot** to steep a cup of tea.
- **Spend cups on helpers** in the Nook tab. Each helper brews cups for you every second, and each one you buy appears in the scene. Prices go up about 15% with each copy you own.
- **Buy little extras** (one time each) for permanent boosts, like stronger taps or faster helpers.
- **Leave and come back.** The kettle keeps brewing while the app is closed, for up to 8 hours. You will see what you earned when you return.

### Blends

Open the **Blends** tab to choose a tea. You brew one blend at a time, and each plays a little differently: some boost your helpers, some boost your taps, one brings more visitors, and one makes the cups you earn while away bigger. New blends unlock as your lifetime cups grow.

### Regulars

Every so often an animal visits the nook. **Tap the visitor** to say hello and get a tip.

- The first time you meet someone, you get a big welcome gift.
- Every regular has a favorite blend. Brew it while they visit and their tip triples.
- The **Regulars** tab is your collection book. Silhouettes show who you have not met yet.
- Some visitors are seasonal and only appear at certain times of year.

### Goals

- **Daily gift:** open one gift per day to build a streak. Gifts grow with your streak, and every 7th day also gives a Golden Leaf. Missing a day resets the streak.
- **Wishes:** once you have met a regular, they will ask you for things, like tapping the teapot a number of times or welcoming visitors. Finish a wish and claim the reward.
- **Achievements:** each one you unlock adds a permanent +1% to everything you brew.
- **Pet the cat:** after you adopt the Sleepy Cat, tap it to hear it purr. Every few seconds a pet also gives a small bonus.

### Fresh Pot

Once you have steeped enough cups in a single run, you can start a **Fresh Pot** from its tab. Your helpers and extras start over, but you earn **Golden Leaves**, and each one adds 5% to everything you brew, for good. Your blends, regulars, achievements and Golden Leaves all stay. Later runs go much faster.

### Seasons and the sky

The window shows the real time of day on your device, with sunrise, daytime, sunset and starry night. The nook also changes with the calendar:

| Time of year | Look | Visitor |
| --- | --- | --- |
| Spring (Mar to May) | Drifting petals and tulips | Dot the ladybug |
| Summer (Jun to Aug) | Fireflies and a watermelon slice | Lily the frog |
| October | Falling leaves and pumpkins | Boo the ghost |
| Winter (Dec to Feb) | Falling snow and a snowman | Mochi the hare |

Seasonal visitors only come during their season, so check the Regulars tab to see who you are still missing.

### The More tab

- **Your nook in numbers:** total cups, taps, visitors, time spent and more.
- **Teapot color and wall color:** unlock new looks by playing, then pick your favorite.
- **Ambient sound:** soft rain or a crackling fireside. It is off by default and only starts when you tap it.
- **Back up your nook:** see below.

The **Sound** button at the top right turns the small tap and purchase sounds on and off.

## Saving and backups

Your progress is saved automatically in your browser or Home Screen app, on your device only. A few things to know:

- The Home Screen app and Safari keep **separate saves**. Pick one to play in.
- Clearing Safari's website data, or deleting the Home Screen app, **erases your save**.
- Your save does not sync between devices on its own.

To protect your nook or move it to a new phone:

1. Go to **More**, then **Back up your nook**, and tap **Make my code**.
2. Tap **Copy code** and keep it somewhere safe, like a note to yourself.
3. On the other device (or after a reset), paste the code into the box and tap **Restore from code**.

Restoring replaces whatever nook is on that device, so the game asks you to confirm first. Make a fresh code every so often, since a code is a snapshot from the moment you made it.

## Host your own copy

You can host the game for free on GitHub Pages.

1. Create a new **public** repository on GitHub, for example `moss-kettle`.
2. Upload every file from this project to the root of the repository.
3. Go to **Settings**, then **Pages**. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the `main` branch and the `/ (root)` folder, and save.
4. After about a minute, the game is live at `https://YOUR-USERNAME.github.io/REPO-NAME/`.

### What is in the project

| File | What it does |
| --- | --- |
| `index.html` | The whole game: page, styles, art and code in one file |
| `manifest.webmanifest` | Tells phones the name, icon and colors for the installed app |
| `sw.js` | The service worker that lets the game run offline |
| `icon-180.png` | Home Screen icon for iPhone |
| `icon-192.png`, `icon-512.png` | Icons for Android and other browsers |

There is no build step and nothing to install.

### Updating the game

1. Replace `index.html` in your repository with the new version.
2. In `sw.js`, change the version number in `const CACHE = 'moss-kettle-v1';` to a new one (for example `v2`). This tells phones to drop the old cached copy.
3. Commit the change. Players should close the app fully and open it again, once or twice, to get the update.

### Running it locally

Open `index.html` in a browser to play. To test the offline and install features, serve the folder over HTTP, because service workers do not run from `file://` links:

```
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

### Notes

- The game uses the Bagel Fat One and Nunito fonts from Google Fonts. They load on the first visit and are cached after that. If they cannot load, the game falls back to your device's rounded system font.
- Everything else, including all the art, is drawn in the page itself.

## Troubleshooting

**The game looks outdated after I updated it.** Close the app fully (swipe it away), then open it again. You may need to do this twice, because the old version loads first while the new one downloads.

**My progress is gone.** The browser's saved data was probably cleared. If you made a backup code, restore it from the More tab.

**There is no Add to Home Screen option on iPhone.** Make sure you are in Safari and not a browser inside another app.

**I do not hear any sound.** Check that your phone is not on silent, and that Sound (top right) or Ambient sound (More tab) is turned on. Browsers only play audio after you tap something.
