# OpenStreetMap thuốc lào

_dành cho anh em nghiện bản đồ_ [🗺 xem](https://zelonewolf.github.io/openstreetmap-americana/)

<img src="doc-img/dieu_cay.png" alt="Logo" width="200"/>

> _Hút thuốc lào bằng điếu cày tiện lợi, vừa ngon vừa phát ra âm thanh giòn giã. Ngoài ra thân điếu được lắp thêm móc sắt vào để treo, nhằm tránh làm nước trong thân điếu đổ ra ngoài. Điếu cày thường được chế tác bằng vật liệu sẵn có, dễ mang xách, giá thuốc rẻ, lại nặng đô nên được tầng lớp bình dân, lao động dùng một cách phổ biến._ <br/><sub>[Wiki tiếng Việt](<https://vi.wikipedia.org/w/index.php?title=Thu%E1%BB%91c_l%C3%A0o&oldid=70884217>)</sub>

> _Smoking tobacco with a water pipe is convenient, delicious and produces a crisp satisfying sound. The body of the pipe has an iron hook to hang it and prevent the water from spilling out. Water pipes are often made from cheap available materials, yet has a solid build and easy to carry, so they are commonly used by the commoners and working class._ <br/><sub>[Translated from Vietnamese Wikipedia](<https://vi.wikipedia.org/w/index.php?title=Thu%E1%BB%91c_l%C3%A0o&oldid=70884217>)</sub>

<br />

The purpose of the Americana style is to:

- Promote collaboration and common purpose in OpenStreetMap’s American mapping community
- Express the American experience through cartography, taking inspiration from the familiar features of North American paper maps
- Challenge the status quo by showcasing innovation and invention

Americana has demonstrated or pioneered several cartographic techniques of importance to Americans that we hope will someday become commonplace among OpenStreetMap-based map styles:

- Nuanced line styles help you distinguish roads, raiload tracks, and waterways based on a variety of intuitive characteristics.
- Highway routes are identified by shields that resemble the signs on the road, with special support for roads that carry multiple routes concurrently.
- Place labels throughout the world appear in both your preferred language and the local language, reflecting linguistic diversity both in the U.S. and abroad.
- A dynamic legend communicates these design choices intuitively, regardless of the visual language you’re accustomed to.

We do this proudly in an open source project using vector tile technology.

## How to use

You can install the OpenStreetMap Americana package and [deploy it anywhere](CONTRIBUTING.md#Production%20builds) as a static webpage. For your convenience, we’ve deployed it [on GitHub Pages](https://zelonewolf.github.io/openstreetmap-americana/). Click the Legend button to learn the meaning of each symbol, line, and color based on the features currently visible on the map.

The style tries to label places in [your browser’s preferred language](https://www.w3.org/International/questions/qa-lang-priorities). To change this preference, consult your browser’s documentation: [Chrome](https://support.google.com/chrome/answer/173424), [Firefox](https://support.mozilla.org/en-US/kb/use-firefox-another-language), [Safari for macOS](https://support.apple.com/guide/mac-help/change-the-system-language-mh26684/mac), [Safari for iOS](https://support.apple.com/en-us/HT204031). You can also override this preference by adding `&language=` to the URL, followed by a comma-separated list of [IETF language tags](https://www.w3.org/International/articles/language-tags/). For example, here’s a map labeled [in Portuguese, falling back to Spanish](https://zelonewolf.github.io/openstreetmap-americana/#language=pt,es). If we don’t have the name of a place in any of your preferred languages, the style shows the name in the local language as a last resort.

## Contributor’s guide

_Contributors welcome!_

The repository is organized as follows:

- **src/** - The map style. See [CONTRIBUTING.md](CONTRIBUTING.md).
- **dev/** - Development tools used for style development. See [Style Developer Tools](dev/README.md)
- **test/** - Automated unit tests.
- **shieldlib/** - Maplibre [shield rendering library](shieldlib/README.md) ([npm entry](https://www.npmjs.com/package/@americana/maplibre-shield-generator?activeTab=readme)).

Some general guidelines:

- Please follow the coding style guidelines described in each sub-folder. These guidelines are designed to make it easier for collaboration and reduce the chance of edit conflicts.
- Innovation is encouraged! Please open a new ticket with your great ideas as a centralized focal point for discussion.
- New contributors are welcome!
- This style operates on the principle of consensus. Maintainers should ensure that changes represent a broad consensus within the American mapping community.
- Maintainers are also responsible to ensure that this principle of consensus does not cause stagnation or inaction. Contributor time is valuable; accepting the responsibility of being a maintainer means committing to responding to issues and PRs on a reasonable timeline that encourages community participation.

## Technology stack

The technology stack for this style can be summarized below:

<img src="doc-img/architecture.drawio.svg" alt="Americana technology stack" />

The dynamic shield generator is included as a [module](shieldlib/README.md) in this repository and also [published to npm](https://www.npmjs.com/package/@americana/maplibre-shield-generator).

## Data sources

The OpenStreetMap Americana style is built upon the [OpenMapTiles schema](https://openmaptiles.org/schema/), which includes:

- Feature data from OpenStreetMap
- Translated name labels from [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page) for places, POIs, airports, roads, bodies of water, parks, and mountain peaks.
- Low-zoom ocean/water, boundary, and urbanized area data from [Natural Earth](https://www.naturalearthdata.com/).

The legend’s “Route markers” section is labeled using labels of Wikidata items that are tagged with the [corresponding OSM tag](https://www.wikidata.org/wiki/Property:P1282).

## Coverage

Americana is compatible with vector tiles covering the entire world.

Americana displays custom route shields for routes in all U.S. states and territories, and for routes in the following countries:

<img src="doc-img/shield_map_world.svg" width="500" alt="Countries">

We are hoping that it will support more countries; you can [help us](https://github.com/ZeLonewolf/openstreetmap-americana/projects/1)!

## Tile Server

Although the source code in this repository is dedicated to the public domain under a CC0 waiver, it is configured by default to load map tiles from a privately-donated community [tile server](https://tile.ourmap.us). This server is available for use by other hobbyist and community projects with constraints. See the [tile server usage policy](TILE_USAGE.md) for more details. This usage policy describes the allowable usage of the tiles for other projects, separate from this style or the application being developed in this repository.
