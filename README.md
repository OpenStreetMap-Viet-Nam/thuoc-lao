# OpenStreetMap thuốc lào
[🗺 xem](https://zelonewolf.github.io/openstreetmap-americana/)

The purpose of 'thuốc lào' map style and 'điếu cày' backend is to:

- Promote collaboration in OpenStreetMap’s Vietnamese and Southeast Asian mapping community
- Allow private deployment by small businesses and organizations with minimal cost and regulatory hurdles (more below)
- Showcase the richness of OpenStreetMap data in a harmonious and beautiful way

'Thuốc lào' is the Vietnamese word for a kind of raw tobacco and 'điếu cày' is the Vietnamese word for "water pipe". They are a national symbol of Vietnam culture. In particular, the water pipe is praised for its versatility, strong build quality, and enhancing the richness of tobacco even though it is only made from cheap materials. This style hopes to exemplify these qualities, and forking from the more developed [Americana](https://github.com/ZeLonewolf/openstreetmap-americana) map style is the perfect choice for realizing them.

<img src="doc-img/dieu_cay.png" alt="Logo" width="200"/>


## How to use

You can install the OpenStreetMap thuốc lào package and [deploy it anywhere](CONTRIBUTING.md#Production%20builds) as a static webpage. For your convenience, we’ve deployed it [on GitHub Pages](https://zelonewolf.github.io/openstreetmap-americana/). Click the Legend button to learn the meaning of each symbol, line, and color based on the features currently visible on the map.

The map's UI is by default in Vietnamese, though it can be changed to other languages. The Paracel and Spratly islands in particular will show different maritime borders depending on your chosen country.

The style will tries to label places in Vietnamese by default with a fall back to English. You can choose another language at the bottom-right corner. You can also override this preference by adding `&language=` to the URL, followed by a comma-separated list of [IETF language tags](https://www.w3.org/International/articles/language-tags/). For example, here’s a map labeled [in Portuguese, falling back to Spanish](https://zelonewolf.github.io/openstreetmap-americana/#language=pt,es). If we don’t have the name of a place in any of your preferred languages, the style shows the name in the local language as a last resort.

## Contributor’s guide

_Contributors welcome!_

The repository is organized as follows:

- **src/** - The map style. See [CONTRIBUTING.md](CONTRIBUTING.md).
- **dev/** - Development tools used for style development. See [Style Developer Tools](dev/README.md)
- **test/** - Automated unit tests.
- **shieldlib/** - Maplibre [shield rendering library](shieldlib/README.md) ([npm entry](https://www.npmjs.com/package/@americana/maplibre-shield-generator?activeTab=readme)).

Some general guidelines:

- Please follow the coding style guidelines described in each sub-folder. These guidelines are designed to make it easier for collaboration and reduce the chance of edit conflicts.
- New contributors are welcome!
- This style operates on the principle of consensus. Maintainers should ensure that changes represent a broad consensus within the American mapping community.
- Maintainers are also responsible to ensure that this principle of consensus does not cause stagnation or inaction. Contributor time is valuable; accepting the responsibility of being a maintainer means committing to responding to issues and PRs on a reasonable timeline that encourages community participation.

## Technology stack

The technology stack for this style can be summarized below:

<img src="doc-img/architecture.drawio.svg" alt="Technology stack" />

The dynamic shield generator is included as a [module](shieldlib/README.md) in this repository and also [published to npm](https://www.npmjs.com/package/@americana/maplibre-shield-generator).

## Data sources

The OpenStreetMap thuốc lào style is built upon the [OpenMapTiles schema](https://openmaptiles.org/schema/), which includes:

- Feature data from OpenStreetMap
- Translated name labels from [Wikidata](https://www.wikidata.org/wiki/Wikidata:Main_Page) for places, POIs, airports, roads, bodies of water, parks, and mountain peaks.
- Low-zoom ocean/water, boundary, and urbanized area data from [Natural Earth](https://www.naturalearthdata.com/).

The legend’s “Route markers” section is labeled using labels of Wikidata items that are tagged with the [corresponding OSM tag](https://www.wikidata.org/wiki/Property:P1282).

## Coverage

Thuốc lào style is compatible with vector tiles covering the entire world and optimized specifically for Vietnam.

As a feature inherited from Americana, thuốc lào style displays custom route shields in the following countries:

<img src="doc-img/shield_map_world.svg" width="500" alt="Countries">

You can help adding more shields by going to [OSM Americana's dedicated page](https://github.com/ZeLonewolf/openstreetmap-americana/projects/1)!

## Tile Server

Although the source code in this repository is dedicated to the public domain under a CC0 waiver, it is configured by default to load map tiles from a privately-donated community [tile server](https://tile.ourmap.us). This server is available for use by other hobbyist and community projects with constraints. See the [tile server usage policy](TILE_USAGE.md) for more details. This usage policy describes the allowable usage of the tiles for other projects, separate from this style or the application being developed in this repository.
