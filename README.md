# FiatAdapter

FiatAdapter makes it incredibly quick and easy to integrate multiple major fiat gateways into your website in just a couple lines of code, enabling your site's visitors to buy and sell cryptocurrencies and tokens with fiaat currency for the best available rate from over 160 countries.

## Quick Start
Integrating FiatAdapter into your site can be done in just two lines of code.

First, import FiatAdapter:
```
<script src="https://fiat-adapter.firebaseapp.com/fiat-adapter.js"></script>
```   
Then call the function `displayFiatAdapter` to display the purchasing widget. For example:
```
<button onclick="displayFiatAdapter()">BUY CRYPTO</button>
```
And that's everything! All together here's a simple example:
```
<html>
	<head>
		<script src="https://fiat-adapter.firebaseapp.com/fiat-adapter.js"></script>
	</head>
	<body>
		<button onclick="displayFiatAdapter()">BUY CRYPTO</button>
	</body>
</html>
```   

## Overview

FiatAdapter works by combining the integrations of all supported fiat gateways, saving you the time of integrating and managing each one yourself. Additionally FiatAdapter looks at the location of the user and chooses the fiat gateway that offers the user the lowest fee among the fiat gateways that support that user's region. You can also customize FiatAdapter to choose which cryptocurrencies you maake available to your users as well as payment methods, ssupported regions, and much more.

### Supported Fiat Gateways

Currently Fiat Adapter is integrated with 6 of the most established fiat gateways:
```
Wyre
Carbon
Safello
PayTrie
Ramp
Moonpay
```

## Customization

You can customize the experience for your users across all supported fiat gateways with a single set of options.

To customize, once the document is ready you can call the function `updateOptionsUrl`, like this:
```
updateOptionsUrl({
  name: 'YourCompany',
  allowedCryptos: ['ETH', 'DAI'],
  unsupportedDiv: '<div style="font-weight:bold;">Sorry, your region isn\'t supported</div>'
});
```

| Option        | Description   | Default |
| ------------- |-------------| --------- |
| logo      | A url pointing to your company or website's logo |  |
| name      | Your company or website's name      | |
| message | A messaage displayed during loading for the fiat gateway Carbon      | |
| address      | The wallet address that the transaction will deposit to. If not provided the widget will have the user fill it in, if provided it will auto-fill      | null (allow the user to fill it in) |
| wyreAccountId      | If you have an account with Wyre you can provide your ID here      | |
| safelloAppId      | If you have an account with Safello you can provide your ID here      | |
| carbonApiKey      | If you have an account with Carbon you can provide your API key here      | |
| moonpayApiKey      | If you have an account with Moonpay you can provide your API key here      | |
| preferredCurrency      | The 3 letter abbreviation of the fiat currency you'd like amounts to be displayed in, for example 'USD' or GBP'      | Chosen regionally if available, or USD |
| amount      | An amount to be pre-filled for purchase, if not provided the widget will let the user fill it in      | null (allow the usser to fill it in) |
| asset      | Choose a crypto asset to be pre-selected that the user will be limited to if supported      | null (allow user to choose, show whatever the default is for each fiat gateway) |
| redirect      | A redirect link to be used by Wyre after the transaction is completed      | |
| unsupported      | HIGHLY RECOMMENDED - A div to be shown if the region the user is in isn't supported with the custimization provided      | <div>Region not supported</div> |
| allowedProviders      | A list of providers allowed to be used, all others will be blocked | ['WYRE', 'RAMP', 'PAYTRIE', 'CARBON', 'MOONPAY', 'SAFELLO']      |
| blockedProviders      | A list of providers not allowed, all others available will be permitted      | none |
| allowedMethods      | A list of payment methods allowed to be used, all others will be blocked. | ['CREDIT_CARD', 'DEBIT_CARD', 'BANK_TRANSFER', 'APPLE_PAY', 'GOOGLE_PAY', 'PAYPAL']      |
| blockedMethods      | A list of payment methods not allowed, all others will be allowed. | []      |
| allowedCurrencies      | A list of payment methods not allowed, all others will be allowed. | ['USD', 'CAD', 'EUR', 'GBP']      |
| blockedCurrencies      | A list of payment methods not allowed, all others will be allowed. | []      |
| allowedCryptos      | A list of cryptocurrencies and tokens allowed, all others will be blocked. | ['SC', 'BTC', 'ETH', 'DAI', 'SAI', 'BAT', 'EOS', 'TRX', 'BCH', 'PAX', 'XLM', 'XRP', 'BNT_EOS', 'BTT', 'BNB', 'VGW', 'JAM', 'RSR', 'RSV', 'FXC', 'PMA', 'COIN', 'ORED', 'TRXD', 'CUSD', 'CUSD_EOS', 'CUSD_BNB', 'XDAI', 'TLOS', 'HBAR', 'TUSD', 'USDC', 'USDT', 'MIOTA', 'TLOSD']      |
| blockedCryptos      | A list of cryptocurrencies and tokens that aren't allowed, all others will be allowed. | []      |
| allowedRegions      | A list of regions (two letter country code) that are allowed, all others will be blocked. | ['US', 'CA', 'CN', 'RU', 'VN', 'BO', 'CO', 'EC', 'DZ', 'BD', 'ID', 'JO', 'KG', 'MA', 'NP', 'SA', 'IR', 'PK', 'TW', 'KH', 'CU', 'KP', 'AU', 'AT', 'BE', 'BR', 'BG', 'HR', 'CY', 'CZ', 'DK', 'EE', 'FI', 'FR', 'DE', 'GR', 'HK', 'HU', 'IS', 'IE', 'IT', 'JP', 'KR', 'LV', 'LI', 'LT', 'LU', 'MT', 'MX', 'NL', 'NO', 'PL', 'PT', 'RO', 'SK', 'SI', 'ZA', 'ES', 'SE', 'GB']|
| blockedRegions      | A list of regions (two letter country code) that are blocked, all others will be allowed. | []      |
| allowedStates      | If the US is an allowed region, a list of US states and territories (two letter state code) that are allowed, all others will be blocked. | ['AK', 'AL', 'AR', 'AZ', 'CA', 'CO', 'CT', 'DE', 'FL', 'GA', 'HI', 'ID', 'IL', 'IN', 'IA', 'KS', 'KY', 'LA', 'ME', 'MD', 'MA', 'MI', 'MN', 'MS', 'MO', 'MT', 'NE', 'NV', 'NH', 'NJ', 'NM', 'NY', 'NC', 'ND', 'OH', 'OK', 'OR', 'PA', 'RI', 'SC', 'SD', 'TN', 'TX', 'UT', 'VT', 'VA', 'WA', 'WV', 'WI', 'WY', 'AS', 'DC', 'FM', 'GU', 'MH', 'MP', 'PW', 'PR', 'VI']      |
| blockedStates      | If the US is an allowed region, a list of US states and territories (two letter state code) that are blocked, all others will be allowed. | []      |
| allowedProvinces      | If CA is an allowed region, a list of CA provinces and territories (two lette code) that are allowed, all others will be blocked. | ['AB', 'BC', 'MB', 'NB', 'NL', 'NS', 'ON', 'PE', 'QC', 'SK', 'NT', 'NU', 'YT']   |
| blockedProvinces      | If CA is an allowed region, a list of CA provinces and territories (two letter code) that are blocked, all others will be allowed. | []      |
| buyAllowed      | `true` allows people to purchase crypto with fiat, `false` blocks buying | true      |
| sellAllowed      | `true` allows people to sell crypto for fiat, `false` blocks selling | true      |
| customRegions      | If you want a specific fiat gateway for a given region you can define that here, in the format {country code: fiat gateway} for example: `[{'GB': 'MOONPAY'}, {'FR': 'CARBON'}]` | []      |
| sortMethod      | The method by which a fiat gateway is chosen. `rate_buy` to choose the lowest crypto purchasing fee. `rate_sell` to choose the lowest crypto selling fee. `daily_limit` to choose the highest daily conversion limit | rate_buy      |
| minimumLimit      | The minimum daily trade amount that the fiat gateway needs to be able to support, overrides sortMethod. For example, say based on your sort method providerA is chosen because it only charges 1%, however it has a daily trade limit of $500. If you set the minimumLimit to $1000, FiatAdapter would choose providerB because it allows for $2500 to be traded daily, even though it has a fee of 2.5% |       |


