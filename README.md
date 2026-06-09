# roleplay-gifs

A curated collection of high-quality anime roleplay GIFs, organized by action category and ready to use in bots, apps, or anything else.

---

## Stats

| Stat | Value |
|------|-------|
| Total categories | **70** |
| Total GIFs | **1114** |
| Hosted on | GitHub Raw CDN |
| Index file | [index.json](./index.json) |

---

## Direct URL pattern

```
https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/{category}/{n}.gif
```

Replace `{category}` with any category name and `{n}` with a number from `1` to the category's count.

---

## index.json

The [index.json](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/index.json) file at the root of this repo contains all category names and their GIF counts. Fetch it once and use it to resolve valid ranges without hardcoding anything.

```json
{
  "base_url": "https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main",
  "total_categories": 70,
  "total_gifs": 1114,
  "categories": {
    "hug": 17,
    "slap": 16,
    ...
  }
}
```

---

## Usage examples

### JavaScript

```js
async function randomGif(category) {
  const index = await fetch(
    "https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/index.json"
  ).then((r) => r.json());

  const count = index.categories[category];
  if (!count) throw new Error(`Unknown category: ${category}`);

  const n = Math.floor(Math.random() * count) + 1;
  return `${index.base_url}/${category}/${n}.gif`;
}

// Example
const url = await randomGif("hug");
console.log(url);
// https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/hug/7.gif
```

### Python

```python
import httpx
import random

def random_gif(category: str) -> str:
    index = httpx.get(
        "https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/index.json"
    ).json()

    count = index["categories"].get(category)
    if not count:
        raise ValueError(f"Unknown category: {category}")

    n = random.randint(1, count)
    return f"{index['base_url']}/{category}/{n}.gif"

# Example
print(random_gif("pat"))
# https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/pat/3.gif
```

### Fetching a specific GIF

If you already know the category and want a specific GIF, you can construct the URL directly:

```
https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/hug/1.gif
https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/slap/4.gif
https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/cry/11.gif
```
---

## npm package

An npm wrapper is also available if you prefer installing via a package manager.

```bash
npm install gifcdn
```

→ [npmjs.com/package/gifcdn](https://www.npmjs.com/package/gifcdn)

```js
import { random, get, list, categories } from "gifcdn";

await random("hug");        // → full URL to a random hug GIF
await get("slap", 3);       // → .../slap/3.gif
await list("cry");          // → array of all 22 cry GIF URLs
await categories();         // → ["airkiss", "angrystare", ...]
```

The package ships with TypeScript types and zero dependencies — it's a thin wrapper around the same raw CDN URLs above.

---

## Categories

All categories listed alphabetically with their GIF count, URL pattern, and a preview.

| Category | Count | URL pattern | Preview |
|----------|------:|-------------|---------|
| `airkiss` | 6 | `.../airkiss/{1..6}.gif` | ![airkiss](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/airkiss/1.gif) |
| `angrystare` | 32 | `.../angrystare/{1..32}.gif` | ![angrystare](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/angrystare/1.gif) |
| `bite` | 20 | `.../bite/{1..20}.gif` | ![bite](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/bite/1.gif) |
| `bleh` | 7 | `.../bleh/{1..7}.gif` | ![bleh](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/bleh/1.gif) |
| `blush` | 41 | `.../blush/{1..41}.gif` | ![blush](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/blush/1.gif) |
| `brofist` | 9 | `.../brofist/{1..9}.gif` | ![brofist](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/brofist/1.gif) |
| `celebrate` | 7 | `.../celebrate/{1..7}.gif` | ![celebrate](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/celebrate/1.gif) |
| `cheers` | 6 | `.../cheers/{1..6}.gif` | ![cheers](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/cheers/1.gif) |
| `clap` | 8 | `.../clap/{1..8}.gif` | ![clap](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/clap/1.gif) |
| `confused` | 8 | `.../confused/{1..8}.gif` | ![confused](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/confused/1.gif) |
| `cool` | 4 | `.../cool/{1..4}.gif` | ![cool](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/cool/1.gif) |
| `cry` | 46 | `.../cry/{1..46}.gif` | ![cry](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/cry/1.gif) |
| `cuddle` | 29 | `.../cuddle/{1..29}.gif` | ![cuddle](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/cuddle/1.gif) |
| `dance` | 33 | `.../dance/{1..33}.gif` | ![dance](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/dance/1.gif) |
| `drool` | 12 | `.../drool/{1..12}.gif` | ![drool](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/drool/1.gif) |
| `evillaugh` | 10 | `.../evillaugh/{1..10}.gif` | ![evillaugh](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/evillaugh/1.gif) |
| `facepalm` | 5 | `.../facepalm/{1..5}.gif` | ![facepalm](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/facepalm/1.gif) |
| `handhold` | 10 | `.../handhold/{1..10}.gif` | ![handhold](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/handhold/1.gif) |
| `happy` | 15 | `.../happy/{1..15}.gif` | ![happy](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/happy/1.gif) |
| `headbang` | 8 | `.../headbang/{1..8}.gif` | ![headbang](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/headbang/1.gif) |
| `hug` | 40 | `.../hug/{1..40}.gif` | ![hug](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/hug/1.gif) |
| `huh` | 6 | `.../huh/{1..6}.gif` | ![huh](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/huh/1.gif) |
| `kiss` | 36 | `.../kiss/{1..36}.gif` | ![kiss](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/kiss/1.gif) |
| `laugh` | 17 | `.../laugh/{1..17}.gif` | ![laugh](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/laugh/1.gif) |
| `lick` | 14 | `.../lick/{1..14}.gif` | ![lick](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/lick/1.gif) |
| `love` | 9 | `.../love/{1..9}.gif` | ![love](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/love/1.gif) |
| `mad` | 25 | `.../mad/{1..25}.gif` | ![mad](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/mad/1.gif) |
| `nervous` | 18 | `.../nervous/{1..18}.gif` | ![nervous](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/nervous/1.gif) |
| `no` | 8 | `.../no/{1..8}.gif` | ![no](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/no/1.gif) |
| `nom` | 46 | `.../nom/{1..46}.gif` | ![nom](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/nom/1.gif) |
| `nosebleed` | 5 | `.../nosebleed/{1..5}.gif` | ![nosebleed](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/nosebleed/1.gif) |
| `nuzzle` | 10 | `.../nuzzle/{1..10}.gif` | ![nuzzle](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/nuzzle/1.gif) |
| `nyah` | 8 | `.../nyah/{1..8}.gif` | ![nyah](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/nyah/1.gif) |
| `pat` | 27 | `.../pat/{1..27}.gif` | ![pat](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/pat/1.gif) |
| `peek` | 6 | `.../peek/{1..6}.gif` | ![peek](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/peek/1.gif) |
| `pinch` | 11 | `.../pinch/{1..11}.gif` | ![pinch](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/pinch/1.gif) |
| `poke` | 17 | `.../poke/{1..17}.gif` | ![poke](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/poke/1.gif) |
| `pout` | 29 | `.../pout/{1..29}.gif` | ![pout](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/pout/1.gif) |
| `punch` | 15 | `.../punch/{1..15}.gif` | ![punch](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/punch/1.gif) |
| `roll` | 7 | `.../roll/{1..7}.gif` | ![roll](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/roll/1.gif) |
| `run` | 26 | `.../run/{1..26}.gif` | ![run](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/run/1.gif) |
| `sad` | 5 | `.../sad/{1..5}.gif` | ![sad](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sad/1.gif) |
| `scared` | 43 | `.../scared/{1..43}.gif` | ![scared](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/scared/1.gif) |
| `shout` | 9 | `.../shout/{1..9}.gif` | ![shout](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/shout/1.gif) |
| `shrug` | 3 | `.../shrug/{1..3}.gif` | ![shrug](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/shrug/1.gif) |
| `shy` | 17 | `.../shy/{1..17}.gif` | ![shy](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/shy/1.gif) |
| `sigh` | 8 | `.../sigh/{1..8}.gif` | ![sigh](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sigh/1.gif) |
| `sing` | 19 | `.../sing/{1..19}.gif` | ![sing](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sing/1.gif) |
| `sip` | 12 | `.../sip/{1..12}.gif` | ![sip](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sip/1.gif) |
| `slap` | 25 | `.../slap/{1..25}.gif` | ![slap](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/slap/1.gif) |
| `sleep` | 34 | `.../sleep/{1..34}.gif` | ![sleep](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sleep/1.gif) |
| `slowclap` | 3 | `.../slowclap/{1..3}.gif` | ![slowclap](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/slowclap/1.gif) |
| `smack` | 18 | `.../smack/{1..18}.gif` | ![smack](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/smack/1.gif) |
| `smile` | 20 | `.../smile/{1..20}.gif` | ![smile](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/smile/1.gif) |
| `smug` | 21 | `.../smug/{1..21}.gif` | ![smug](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/smug/1.gif) |
| `sneeze` | 4 | `.../sneeze/{1..4}.gif` | ![sneeze](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sneeze/1.gif) |
| `sorry` | 4 | `.../sorry/{1..4}.gif` | ![sorry](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sorry/1.gif) |
| `stare` | 20 | `.../stare/{1..20}.gif` | ![stare](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/stare/1.gif) |
| `stop` | 9 | `.../stop/{1..9}.gif` | ![stop](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/stop/1.gif) |
| `surprised` | 19 | `.../surprised/{1..19}.gif` | ![surprised](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/surprised/1.gif) |
| `sweat` | 4 | `.../sweat/{1..4}.gif` | ![sweat](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/sweat/1.gif) |
| `thumbsup` | 6 | `.../thumbsup/{1..6}.gif` | ![thumbsup](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/thumbsup/1.gif) |
| `tickle` | 9 | `.../tickle/{1..9}.gif` | ![tickle](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/tickle/1.gif) |
| `tired` | 15 | `.../tired/{1..15}.gif` | ![tired](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/tired/1.gif) |
| `wave` | 22 | `.../wave/{1..22}.gif` | ![wave](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/wave/1.gif) |
| `wink` | 32 | `.../wink/{1..32}.gif` | ![wink](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/wink/1.gif) |
| `woah` | 8 | `.../woah/{1..8}.gif` | ![woah](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/woah/1.gif) |
| `yawn` | 10 | `.../yawn/{1..10}.gif` | ![yawn](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/yawn/1.gif) |
| `yay` | 10 | `.../yay/{1..10}.gif` | ![yay](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/yay/1.gif) |
| `yes` | 9 | `.../yes/{1..9}.gif` | ![yes](https://raw.githubusercontent.com/itsfizys/roleplay-gifs/main/yes/1.gif) |

---

## License

[MIT](LICENSE) &copy; 2026 [itsfizys](https://github.com/itsfizys)