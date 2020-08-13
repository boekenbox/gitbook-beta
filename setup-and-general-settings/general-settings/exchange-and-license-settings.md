# Exchange settings

{% hint style="info" %}
API key management is done in Gunbot. Every registered API key can also be used in bitRage.
{% endhint %}

To start using bitRage, you need to connect it to one or more exchanges. 

To do so, go to **Settings &gt; Trading &gt; Exchanges**.

Select your exchange and fill in the required fields.

**image**



## API settings

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Master Key</b>
      </td>
      <td style="text-align:left">
        <p>The API key registered to be used with Gunbot.</p>
        <p>This key may have read only access as long as you use a different Key
          for actual trading.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Master Secret</b>
      </td>
      <td style="text-align:left">The API secret for the Master Key.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Key</b>
      </td>
      <td style="text-align:left">
        <p>The API key used for trading, can be the same as Master Key.</p>
        <p>This key must exist in the same exchange account as the Master Key.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Secret</b>
      </td>
      <td style="text-align:left">The API secret for the Key.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Key2</b>
      </td>
      <td style="text-align:left">The API key used for stage 3 orders, must be a different API key than
        &quot;Key&quot;.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Secret2</b>
      </td>
      <td style="text-align:left">The API secret for Key2.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Delay</b>
      </td>
      <td style="text-align:left">
        <p>The delay factor (in seconds) for processing pairs on this exchange.</p>
        <p>Setting this to 10 should work in almost all cases, you can lower it later
          to speed up pair processing after you&apos;ve verified that everything
          works.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Trading Fees</b>
      </td>
      <td style="text-align:left">
        <p>Set the trading fees <b>for one trade. </b>
        </p>
        <p>Enter it as a number, representing a percentage. Entering 0.1 means that
          0.1% fees are expected for each trade.</p>
      </td>
    </tr>
  </tbody>
</table>

{% hint style="info" %}
Not all exchanges require a second API key, called `key2.`
{% endhint %}

Some exchanges require extra settings like a passphrase. These are described below. 

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>clientId</b>
      </td>
      <td style="text-align:left">Your CEX client ID. Only relevant for CEX.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>passphrase</b>
      </td>
      <td style="text-align:left">
        <p>Your API passphrase. Only relevant for GDAX and KuCoin.</p>
        <p>
          <br />In case you use a different trading key than your master key, make sure
          that both keys use the same passphrase.</p>
      </td>
    </tr>
  </tbody>
</table>

## Delay settings

| Field | Description |
| :--- | :--- |
| **Delay** | The delay in seconds between polling tickers. Used in websocket mode. |
| **REST delay** | Delay in seconds between processing pairs. Used in REST mode. |
| **Trades interval** | Delay in seconds between firing trades. Relevant for `crazybitch` mode. Increase this value when you notice trade execution errors after stage 1. |

## Filter settings

Each exchange has various options to filter pairs and volume. The options are:

<table>
  <thead>
    <tr>
      <th style="text-align:left">Field</th>
      <th style="text-align:left">Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left"><b>Filtered pairs</b>
      </td>
      <td style="text-align:left">Comma separated list of coins to exclude.
        <br />
        <br />Triples that include any of the filtered coins will never be traded.</td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Include Coins</b>
      </td>
      <td style="text-align:left">
        <p>Comma separated list of coins to include.</p>
        <p></p>
        <p>Only triples that contain explicitly included coins will be traded.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Filtered Bags</b>
      </td>
      <td style="text-align:left">
        <p>Comma separated list of coins that are exempt from <code>COMPOUND_BAGS.</code>
        </p>
        <p></p>
        <p>Any coin listed here is will trade as if <code>COMPOUND_BAGS</code> is disabled.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Volume 1st</b>
      </td>
      <td style="text-align:left">
        <p>Volume filter for stage 1 orders. Only triples will be traded when they
          match the volume filters for all stages.</p>
        <p></p>
        <p>Volume can be defined per coin as a comma separated list, expressed in
          base.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Volume 2nd</b>
      </td>
      <td style="text-align:left">
        <p>Volume filter for stage 2 orders. Only triples will be traded when they
          match the volume filters for all stages.</p>
        <p></p>
        <p>Volume can be defined per coin as a comma separated list, expressed in
          base.</p>
      </td>
    </tr>
    <tr>
      <td style="text-align:left"><b>Volume 3rd</b>
      </td>
      <td style="text-align:left">
        <p>Volume filter for stage 3 orders. Only triples will be traded when they
          match the volume filters for all stages.</p>
        <p></p>
        <p>Volume can be defined per coin as a comma separated list, expressed in
          base.</p>
      </td>
    </tr>
  </tbody>
</table>

## Config example

When you prefer to use the config file instead of the GUI, find an example below of a successfully added exchange.

```text
 "binance": {
            "masterkey": "Registered API",
            "mastersecret": "SECRET",
            "key": "API (can be same as masterkey)",
            "secret": "SECRET",
            "key2": "Different API",
            "secret2": "SECRET",
            "delay": 10,
            "REST_delay": 10,
            "TRADING_FEES": 0.25,
            "TRADES_INTERVAL": 10,
            "filteredPairs": ["BTC","USD","USDT"],
            "includeCoins": ["BTC","USD","USDT"],
            "filteredBags": ["BTC","USD","USDT","EUR"],
            "Volume1st": {"XMR":100},
            "Volume2nd": {"XMR":100,"MAID":100},
            "Volume3rd": {"MAID":100}
        }
```



{% page-ref page="exchange-and-license-settings.md" %}

