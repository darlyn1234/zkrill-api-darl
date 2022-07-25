# darlyn Npmjs

Install package
```sh
npm i @darlyn1234/zkrill-api-darl
```
Install latest version from github (not recommended)
```sh
npm i github:@darlyn1234/zkrill-api-darl
```

## What's updated?
- Using [zod](https://www.npmjs.com/package/zod) to validate data input and output. (not finished yet)
- Some bug fixes.
- Breaking changes. see [this](#from-v200-to-v300)

## Ejemplo de uso
```js
// ESM 
import * as scraper from '@darlyn1234/zkrill-api-darl'
// CJS
const scraper = require('@darlyn1234/zkrill-api-darl')
```
### Instagram Downloader
```js
// Instagram Downloader
import { 
    instagramdl, 
    instagramdlv2, 
    instagramStory,
    instagramStoryv2
} from '@darlyn1234/zkrill-api-darl'
const url = 'https://www.instagram.com/reel/CdI2rVDoagj/?utm_source=ig_web_copy_link'
instagramdl(url).then(console.log).catch(console.error)
instagramdlv2(url).then(console.log).catch(console.error)
// use both to handle error
instagramdl(url).catch(_ => instagramdlv2(url)).then(console.log)
// Use async/await or top level await
console.log(await instagramdl(url).catch(console.error))
console.log(await instagramdlv2(url).catch(console.error))
// Instagram Story downloader
const username = 'darlyn1234'
const story = await instagramStory(username).catch(async _ => await instagramStoryv2(username))
console.log(story)
```
- `instagramdl` website https://snapinsta.app, 
- `instagramdlv2` website https://downloadgram.org
- `instagramdlv3` website https://downvideo.quora-wiki.com
- `instagramdlv4` website https://instadownloader.co
- `instagramStory` website https://storydownloader.app
- `instagramStoryv2` website https://www.instadp.com [**not working**]


### Youtube Downloader
```js
// Youtube downloader
import { 
    youtubedl,
    youtubedlv2 
} from '@darlyn1234/zkrill-api-darl'
const url = 'https://youtu.be/dyRsYk0LyA8'
youtubedl(url).catch(_ => youtubedlv2(url)).then(({ video }) => {
    video['240p'].download().then(console.log).catch(console.error)
})
// Use async/await 
const yt = await youtubedl(url).catch(async () => await  youtubedlv2(url))
const dl_url = await yt.video['240p'].download()
console.log(dl_url)
```
- `youtubedl` website https://www.y2mate.com
- `youtubedlv2` website https://yt5s.com
- `youtubedlv3` website https://onlinevideoconverter.pro
- `youtubeSearch` website https://www.youtube.com


### Tiktok downloader
```js
// Tiktok downloader
import { 
    tiktokdl,
    tiktokdlv2 
} from '@darlyn1234/zkrill-api-darl'
// Tiktok downloader v1
const url = 'https://www.tiktok.com/@aphr.odite/video/7040499087094877445'
tiktokdl(url).then(console.log).catch(console.error)
// tiktokdl v2
tiktokdlv2(url).then(console.log).catch(console.error)
// async / await 
console.log(await tiktokdl(url).catch(console.error))
console.log(await tiktokdlv2(url).catch(console.error))
```
- `tiktokdl` website https://snaptik.app
- `tiktokdlv2` website https://api.tikmate.app
- `tiktokdlv3` website 'https://ssstik.io
- `tiktokfyp` website https://t.tiktok.com [**Not Working**]

### All in One Downloader
```js
import {
    aiovideodl,
    savefrom,
    snapsave
} from '@darlyn1234/zkrill-api-darl'
// Facebook video downloader
console.log(await aiovideodl('https://fb.watch/euSKCMQI7I/'))
// Twitter video downloader
console.log(await aiovideodl('https://twitter.com/jen_degen/status/1458167531869458440?s=20'))

// Tiktok downloader
console.log(await savefrom('https://www.tiktok.com/@aphr.odite/video/7040499087094877445?is_from_webapp=1&sender_device=pc&web_id=6971114554768229893'))
// Instagram downloader
console.log(await savefrom('https://www.instagram.com/reel/CdI2rVDoagj/?utm_source=ig_web_copy_link'))

// Instagram downloader
console.log(await snapsave('https://www.instagram.com/reel/CdI2rVDoagj/?utm_source=ig_web_copy_link'))
// Facebook video downloader
console.log(await snapsave('https://fb.watch/euSKCMQI7I/'))
```
- `aiovideodl` use website https://aiovideodl.ml [**Not Working**]
- `savefrom` use website https://id.savefrom.net
- `snapsave` use website https://snapsave.app

### Primbons
```js
// Primbons
import { 
    getZodiac,
    nomorhoki
} from '@darlyn1234/zkrill-api-darl'
// Get zodiac
console.log(getZodiac(1, 1))
// Get nomor hoki
console.log(await nomorhoki(6213353))
```
- `artimimpi` website https://www.primbon.com
- `artiname` website https://www.primbon.com
- `nomorhoki` website https://www.primbon.com
- `getZodiac` https://github.com/Nurutomo/wabot-aq/blob/master/plugins/zodiac.js


### Images
```js
// Images
import {
    googleImage,
    pinterest,
    wallpaper,
    stickerTelegram,
} from 'darlyn1234/zkrill-api-darl'
const keyword = 'blackpink'
// Google image
console.log(await googleImage(blackpink))
// Pinterest image
console.log(await pinterest(blackpink))
// Wallpaper
console.log(await wallpaper(blackpink))
// Sticker telegram
console.log(await stickerTelegram(blackpink))
```
- `googleImage` website https://www.google.com
- `pinterest` website https://www.pinterest.com
- `stickerTelegram` website https://combot.org
- `stickerLine` website https://store.line.me
- `wallpaper` website https://www.shutterstock.com
- `wallpaperv2` website https://wall.alphacoders.com
- `wallpaperv3` website https://www.hdwallpapers.in

### News
```js
// News
import {
    cnbindonesia,
    antaranews,
    kompas
} from '@darlyn1234/zkrill-api-darl'
// Cnbindonesia
console.log(await cnbindonesia())
// Antaranews
console.log(await antaranews())
// Kompas
console.log(await kompas())
```
- `antaranews` website https://www.antaranews.com
- `cnbindonesia` website https://www.cnbcindonesia.com
- `kompas` website https://www.kompas.com
- `liputan6` website https://www.liputan6.com
- `merdeka` website https://www.merdeka.com
- `suaracom` website https://www.suara.com

### Encryption
```js
// Encryption
import {
    toBase64,
    fromBase64ToString,
    randomUUID,
    randomBytes,
    createHash
} from '@darlyn1234/zkrill-api-darl'
// To base64
const base64 = toBase64('Darlyn-Npmjs')
console.log(base64)
// From base64 to string
console.log(fromBase64ToString(base64)) // 'Darlyn-Npmjs'
// Random UUID
console.log(randomUUID())
// Random Bytes
console.log(randomBytes(16))
// Hash
console.log(createHash('sha256', 'Darlyn Npmjs'))
```
- `randomUUID` source: https://github.com/uuidjs/uuid/blob/main/src/v4.js and https://github.com/nodejs/node/blob/master/lib/internal/crypto/random.js
- `randomBytes` use `crypto` module
- `createHash` use `crypto` module

### Bioskop
```js
// Bioskop
import {
    bioskopNow,
    bioskop
} from '@darlyn1234/zkrill-api-darl'
// Bioskop 
console.log(await bioskop())
// Bioskop Now
console.log(await bioskopNow())
```
- `bioskop` use website https://jadwalnonton.com
- `bioskopNow` use website https://jadwalnonton.com

### Downloader 
```js
import {
    mediafiredl,
    sfilemobi,
    sfilemobiSearch,
    zippyshare
} from '@darlyn1234/zkrill-api-darl'
// Mediafire
console.log(await mediafiredl('https://www.mediafire.com/file/gpeiucmm1xo6ln0/hello_world.mp4/file'))
// Sfilemobi
console.log(await sfilemobi('https://sfile.mobi/oGm8kAIQCs7'))
// Sfilemobi Search
console.log(await sfilemobiSearch('blackpink'))
// Zippyshare
console.log(await zippyshare('https://www53.zippyshare.com/v/Gajlfjd4/file.html'))
```
- `mediafiredl` use website https://www.mediafire.com
- `sfilemobi` use website https://www.sfilemobi.com
- `sfilemobiSearch` use website https://www.sfilemobi.com
- `zippyshare` use website https://www.zippyshare.com

### Chord 
```js
import {
    chord
} from '@darlyn1234/zkrill-api-darl'
// Chord
console.log(await chord('Until i found you'))
```
- `chord` website https://www.gitagram.com

## Breaking Changes
### - from v1.0.0 to v1.0.4
- `savefrom` now output array of object instead of object