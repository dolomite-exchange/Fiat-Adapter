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

| Option        | Description   |
| ------------- |-------------|
| logo      | A url pointing to your company or website's logo |
| name      | Your company or website's name      |
| message | A messaage displayed during loading for the fiat gateway Carbon      |
| address      | The wallet address that the transaction will deposit to. If not provided the widget will have the user fill it in, if provided it will auto-fill      |
| wyreAccountId      | If you have an account with Wyre you can provide your ID here      |
| safelloAppId      | If you have an account with Safello you can provide your ID here      |
| carbonApiKey      | If you have an account with Carbon you can provide your API key here      |
| moonpayApiKey      | If you have an account with Moonpay you can provide your API key here      |
| preferredCurrency      | The 3 letter abbreviation of the fiat currency you'd like amounts to be displayed in, for example 'USD' or GBP'      |
| amount      | An amount to be pre-filled for purchase, if not provided the widget will let the user fill it in      |
| asset      | Choose a crypto asset to be pre-selected that the user will be limited to if supported      |
| redirect      | A redirect link to be used by Wyre after the transaction is completed      |
| unsupported      | HIGHLY RECOMMENDED - A div to be shown if the region the user is in isn't supported with the custimization provided      |
| allowedProviders      | A list of providers allowed to be used. Default: ['WYRE', 'RAMP', 'PAYTRIE', 'CARBON', 'MOONPAY', 'SAFELLO']      |
