## Mirror Protocol Price Feed
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fcrypt0grapher%2FmirrorProtocolFeed.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2Fcrypt0grapher%2FmirrorProtocolFeed?ref=badge_shield)

### App
The app provides info on MAssets over time from [Mirror Protocol](https://mirrorprotocol.app/) on [Terra blockchain ](https://terra.money/) aiming to assist traders with possible arbitrage opportunities.
The prices of an Asset recieved from Oracle and its Mirrored MAsset counterpart are aimed to be equal, but they are not exactly the same. This difference which can be quite significant forms a traders' premium. 
This tool monitors the premiums and provides a minimal statistical analysis.

### Overview
Over the most recent 10K records [the app shows](https://mirror.planeta.money/):
- Traders' premium for MAssets as _1 - *Real (Oracle) Price*/*MirrorPrice*, and some stats: mean, standard deviation, and charts.
- bLuna price is also collected, "premium" is a simulation response of 1 minus how many bLuna can be bought for 1 uluna.  

### Frameworks
- Backend - [Express](https://expressjs.com/) .
- Frontend - [Pug](https://pugjs.org/) with [Bootstrap](https://getbootstrap.com/).
- Database - [MongoDB](https://mongodb.com/) with Mongoose.
- CSV Libs - [json2csv](https://www.npmjs.com/package/json2csv).
- Chart -  [TimeChart](https://github.com/huww98/TimeChart).
- Blockchain - [Terra.js](https://terra-money.github.io/terra.js/), [Mirror.js](https://mirror-protocol.github.io/mirror.js/).

### Architecture
The bundle basically consists of two Express.js apps running on the single Node.js instance: the API (serving at port 4000 by default) and the Host (default port 3000).
- **API** is a server polling Mirror protocol every 60 seconds and saving the feed to MongoDB database, extracts the data on request and generates HTML pages with Pug templates.
- **Host** is a simple HTML/TS application with Bootstrap v5 serving a minimal UI and user interaction.

### Installation
- Clone the repo.
- Install the bundle with `yarn` (or `npm install`).
- Make sure you got MongoDB instance running.
- Create `.env` file from `.env.example`. Just renaming the file will suffice.
- Run with `yarn start dev` for testing.
- Enjoy, [http://localhost:3000](http://localhost:3000) by default.

### Using chart interface
With touch screen:
* 1 finger to pan
* 2 or more finger to pan and zoom

With mouse:
* Left button drag to pan
* wheel scroll translate X axis
* Alt + wheel scroll to translate Y axis
* Ctrl + wheel scroll to zoom X axis
* Ctrl + Alt + wheel scroll to zoom Y axis
* Hold Shift key to speed up translate or zoom 5 times

With trackpad:
* Pan X or Y direction to translate X axis
* Alt + Pan X/Y direction to translate X/Y axis
* Pinch to zoom X axis
* Alt + pinch to zoom Y axis
* Hold Shift key to speed up translate or zoom 5 times

## License
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2Fcrypt0grapher%2FmirrorProtocolFeed.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2Fcrypt0grapher%2FmirrorProtocolFeed?ref=badge_large)
