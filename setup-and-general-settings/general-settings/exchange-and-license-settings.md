# Exchange settings

{% hint style="info" %}
API key management is done in Gunbot. Every registered API key can also be used in bitRage.
{% endhint %}

To start using bitRage, you need to connect it to one or more exchanges. 

To do so, go to **Settings &gt; Trading &gt; Exchanges**.

Select your exchange and fill in the required fields.

**image**

Select your exchange and fill in all the fields for this exchange.

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
</table>## Config example

When you prefer to use the config file instead of the GUI, find an example below of a successfully added exchange.

```text
"exchanges": {
        "huobi": {
            "key": "key",
            "secret": "secret",
            "masterkey": "registered key",
            "mastersecret": "secret for registered key",
            "type": "huobi",
            "TRADING_FEES": 0.2,
            "delay": 1
        }
    }
```



{% page-ref page="exchange-and-license-settings.md" %}

