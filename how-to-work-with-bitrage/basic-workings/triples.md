# Valid Triplets / Pairs

## Triplets

Pairs in bitRage are added as "triplets": a combination of three trading pairs where the last trade sells back into the base currency of the first pair.

**Example of a valid triplet:**

| Stage | Pair | Normal trade |
| :--- | :--- | :--- |
| Stage 1 | BTC-ADA | Buys ADA with BTC |
| Stage 2 | ETH-ADA | Sells ADA for ETH |
| Stage 3 | BTC-ETH | Sells ETH for BTC |

The Reversal Trade option makes bitRage trade a triplet in a difference sequence, you do not need to input your pairs in a different way for this.



**Example of an invalid triplet:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Stage</th>
      <th style="text-align:left">Pair</th>
      <th style="text-align:left">Logical error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Stage 1</td>
      <td style="text-align:left">BTC-ADA</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left">Stage 2</td>
      <td style="text-align:left">ETH-ADA</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left">Stage 3</td>
      <td style="text-align:left">USDT-ETH</td>
      <td style="text-align:left">
        <p>Selling ETH for USDT would not lead to the triplet returning</p>
        <p>to the initially invested base currency, therefore it is invalid.</p>
      </td>
    </tr>
  </tbody>
</table>

## Quads

When you run bitrage in `QUAD` mode, a combination of 4 pairs is watched for opportunities.

**Example of a valid quad:**

| Stage | Pair | Normal trade |
| :--- | :--- | :--- |
| Stage 1 | BTC-MANA | Buys MANA with BTC |
| Stage 2 | ETH-MANA | Sells MANA for ETH |
| Stage 3 | ETH-POLY | Buys POLY with ETH |
| Stage 4 | BTC-POLY | Sells POLY for BTC |

The Reversal Trade option makes bitRage trade a quad in a difference sequence, you do not need to input your pairs in a different way for this.



**Example of an invalid quad:**

<table>
  <thead>
    <tr>
      <th style="text-align:left">Stage</th>
      <th style="text-align:left">Pair</th>
      <th style="text-align:left">Logical error</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td style="text-align:left">Stage 1</td>
      <td style="text-align:left">BTC-MANA</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left">Stage 2</td>
      <td style="text-align:left">ETH-MANA</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left">Stage 3</td>
      <td style="text-align:left">ETH-POLY</td>
      <td style="text-align:left">-</td>
    </tr>
    <tr>
      <td style="text-align:left">Stage 4</td>
      <td style="text-align:left">USDT-POLY</td>
      <td style="text-align:left">
        <p>Selling POLY for USDT would not lead to the quad returning</p>
        <p>to the initially invested base currency, therefore it is invalid.</p>
      </td>
    </tr>
  </tbody>
</table>

