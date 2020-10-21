# Support / Resistance





### Formula 

Gunbot uses the following formula to calculate support and resistance levels. The number of candles uses as input is user configurable with the `SMAPERIOD`setting.

```text
P = (H + L + C) / 3 
R1 = (P  2) - L 
R2 = P + (H - L) 
S1 = (P  2) - H 
S2 = P - (H - L)
```

