# MMM-crypto-portfolio
A <a href="https://github.com/MichMich/MagicMirror">MagicMirror</a> module used to get real-time values of crypto currencies.

This module is orginally made By Matteo Danelli, many thanks for his great work.
I have adapted it to show the portfolio and assets.

## Installation
1. Navigate into your MagicMirror's `modules` folder and execute `git clone https://github.com/spoturdeal/MMM-crypto-portfolio.git`.
2. Add the module inside `config.js` placing it where you prefer ;)

## Version
25th April 2018 Added Feathercoin and Nexus Logos

## Config


|Option|Description|
|---|---|
|`currency`|One or more currencies you want to display.<br>**Type:** `multidimensional array`<br>**Options:** `bitcoin, ethereum, ripple, dash, bitcoin-gold, litecoin, iota, ethereum-classic, nem, stratis, bitcoin-cash, cardano, neo`<br>**Default:** <i>[{name:'bitcoin', portf: 1.2345678},{name:'xrp',    portf: 1.688014},{name:'litecoin',  portf: 0.382885},{name:'ethereum',  portf: 3.771212}]</i>|
|`conversion`|The currency used to convert crypto currency value.<br>**Type:** `string`<br>**Options:** `AUD, BRL, CAD, CHF, CNY, EUR, GBP, HKD, IDR, INR, JPY, KRW, MXN, RUB, USD`<br>**Default:** <i>EUR</i>|
|`showUSD`|When using other currencies than USD. Value can also be shown in USD.<br>**Type:** `boolean`<br>**Default:** <i>false</i>|
|`displayLongNames`| Option that show full name of the currency or the shortest version. (eg. Bitcoin/BTC ). <br> **Type** `boolean` <br> **Default** <i>false</i> |
|`displayType`| Sets the display of the module. <br>**Type:** `string`<br>**Options:** `detail, logo, logoWithChanges`<br/>**Default:** <i>detail</i>
|`showAssets`| Shows the value of your portfolio. <br>**Type:** `boolean`<br>**Options:** true, false<br/>**Default:** <i>true</i>
|`showPortfolio`| Show the amount of the coin in your wallet. <br>**Type:** `boolean`<br>**Options:** true, false<br/>**Default:** <i>false</i>
|`showAgainstBTC`| Show the BTC value of the coin. <br>**Type:** `boolean`<br>**Options:** true,false<br/>**Default:** <i>true</i>
|`showTotalMarketCap`| Show the total market cap only in US$. <br>**Type:** `boolean`<br>**Options:** true,false<br/>**Default:** <i>false</i>
|`logoHeaderText`| Defines the headline text if `displayType: logo` is set.<br/>**Type:** `string`<br>**Default:** <i>My Crypto portfolio</i>
|`headers`| Possibility to show currency change in the last hour, day or week. <br> **Type** One of the following: `change1h, change24h, change7d` <br> **Default** <i>None. All optionals.</i> |
|`significantDigits`|Total digits to use for rounding the price (including before and after decimal point).<br> **Type** `number` <br> **Default** <i>2</i> |
|`showGraphs`| Possibility to show currency graph over the last week in `displayType: logo`. <br> **Type:** `boolean` <br> **Default** <i>false</i> |
|`coloredLogos`| Toggles white or colored logos `displayType: logo`. <br> **Type:** `boolean` <br> **Default** <i>false</i> |
|`fontSize`| Dimension of price text. You can specify pixel values, em values or keywords.<br> **Type:** `string` <br>**Options:** `xx-small`, `x-small`, `small`, `medium`, `large`, `x-large`, `xx-large` <br> **Default** <i>small</i> |
|`limit`| Number of currencies to download, according to CoinMarketCap ranking. Increase this value only if you cannot display a currency. <br> **Type:** `string` <br> **Default** <i>200</i> |
|`showLabels`| Show text labels. <br> **Type:** `boolean` <br>**Options:** true, false <br>  **Default** <i>true</i> |
|`logoPosition`| Set the position for the logo. <br> **Type:** `string` <br>**Options:** `front`, `middle`, `back`<br>  **Default** <i>`front`</i> |
|`graphPosition`|Set the position for the graphic. <br> **Type:** `string` <br>**Options:** `front`, `back`<br> **Default** <i>`back`</i> |


Here is an example of an entry in `config.js`
```
{
	module: "MMM-crypto-portfolio",
	position: "top_right",   // see mirror setting for options
	config: {          // this is changed from Mateo`s Version
		           // enter currency as pairs (name is the coin and portf how much you own)
		currency: [{name: 'bitcoin',  portf:  1.2345678},
		           {name: 'xrp',      portf: 1.688014},
                           {name: 'litecoin', portf: 0.382885},
                           {name: 'ethereum', portf: 3.771212}],
		conversion: 'EUR',
		showPortfolio: true,    
                showAssets: true,       
		showAgainstBTC: true,      // only used in detail view
		showTotalMarketCap: false, // only used in detail view
		showUSD: false,
		fontSize: 'small',
		headers: ['change24h', 'change1h', 'change7d'],
		displayType: 'detail',   // or 'logoWithChanges',
		showGraphs: true,
		limit:100               // increase if your coin doesn't appear ther are more then 1000 
	}
},  // Don't forget this comma !
```

## Screenshots
#### Display type: details
![Screenshot of detail mode](/LogoAgainstBTC.png?raw=true "Included assets")

#### Display type: details 
![Screenshot of detail mode](/logowithassets.png?raw=true "Included assets")

#### Display type: logoWithChanges + showGraphs
![Screenshot with logo changes and graphs](/logoNewDetail.png?raw=true "displayType: 'logoWithChanges', showGraphs: 'true'")

## Cryptocurrency Logo

Logo provided only for the following currencies:
- Bitcoin, Bitcoin cash, Bitcoin gold
- Ethereum, Ethereum classic
- Ripple
- Stratis
- Nem
- Litecoin
- Dash
- Cardano
- Eos
- Iota
- Monero
- Neo
- Stellar
- Tron

Feel free to ask for support of your favorite currency. Else, just implement it (eg: to add Litecoin logo):
- Add `'litecoin'` to the currency module config
- Create the logo (png, 50x50px)
- Name the file `litecoin.png`
- Put it in the `/public/` `black-white/` and `colored` directory of the module
- Restart MagicMirror

## Notes
Data provided by <a href="https://coinmarketcap.com/">coinmarketcap.com</a>.
- Endpoints update every 5 minutes.

## Contributors
<a href="https://github.com/Klizzy/MMM-cryptocurrency">Klizzy</a> for translations and multiple currencies.

<a href="https://github.com/olexs/MMM-cryptocurrency">olexs</a> for currencies graphs and significant digits.

<a href="https://github.com/mateodanelli/MMM-cryptocurrency">Mateo</a> For the fantastic base of this module. Check his module for extra config information.

<a href="https://fontawesome.com/v4.7.0/icons/">Fontawesome</a> Providing great graphical fonts.

<a href="https://github.com/Caziopei">Caziopei</a> For Swedish translation. 

<a href="https://github.com/kurtern84">kurtern84</a> For Norwegian translation.

<a href="https://github.com/darkniki">darkniki</a> For Russian translation.

The MIT License (MIT)
=====================

Copyright © 2018 SpoturDeal - Carl 

Permission is hereby granted, free of charge, to any person
obtaining a copy of this software and associated documentation
files (the “Software”), to deal in the Software without
restriction, including without limitation the rights to use,
copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the
Software is furnished to do so, subject to the following
conditions:

The above copyright notice and this permission notice shall be
included in all copies or substantial portions of the Software.

**The software is provided “as is”, without warranty of any kind, express or implied, including but not limited to the warranties of merchantability,
fitness for a particular purpose and noninfringement. In no event shall the authors or copyright holders be liable for any claim, damages or other liability,
whether in an action of contract, tort or otherwise, arising from, out of or in connection with the software or the use or other dealings in the software.**
