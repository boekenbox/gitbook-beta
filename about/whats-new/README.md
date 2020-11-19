---
description: >-
  Esta es una descripción rápida de los cambios más importantes introducidos en
  la V20
---

# Que es lo nuevo?

Gunbot v20 introduce una interfaz completamente nueva construida usando la librería de gráficos de TradingView. con opciones más fáciles para crear y editar los parametros de la estrategia. También incluye muchos cambios y mejoras en la estabilidad.

## **Mejorando**

{% hint style="success" %}
**Nuevo: herramienta de importación de configuración**

Ahora es realmente fácil cargar un archivo config.js o autoconfig.json en la interfaz e importar solo las partes que necesita de él. Puede usar esto para configurar una instalación limpia v20 mientras migra sus pares, estrategias y otras configuraciones antiguas.

**Pasos para comenzar con una instalacion limpia:** extraiga v20 y ejecute, ingrese la dirección de tu cartera Gunthy en el asistente, seleccione "otro" en la pestaña intercambio y guarde los cambios. Luego vaya a Perfil &gt; Importar parametros y seleccione las partes que quiera importar de su configuración antigua. 
{% endhint %}

No hay cambios de configuración importantes para v20. En caso de que esté actualizando desde v18.x, lo único que necesita es reemplazar el archivo ejecutable  _\(gunthy-win.exe / gunthy-linux / gunthy-macos\)_  y la carpeta _node\_modules_.

![La GUI requiere que la autenticaci&#xF3;n de contrase&#xF1;a est&#xE9; habilitada en config.js. Config&#xFA;relo as&#xED;.](../../.gitbook/assets/image%20%2874%29.png)

Los nuevos parámetros de estrategia se fusionan automáticamente en sus estrategias tan pronto como inicie sesión en la interfaz gráfica del navegador.

En caso de que esté actualizando desde una versión anterior a la v18, consulte los registros de cambios de versiones anteriores para obtener instrucciones o comience una instalación nueva.

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}

## Cambios en v20

Solo se enumeran los cmabios más importantes.

### Núcleo / GUI

* **Interfaz gráfica completamente nueva:** rendimiento mejorado, más fácil de usar, mejores gráficos, terminal manual de trading mejorado, más estadísticas, asistente de configuración para novatos
* **Guardar cambios en config sin reiniciar:** el ciclado de pares ya no se reinicia cuando se guarda un cambio en la configuración. Los nuevos ajustes entran en vigor en el siguiente ciclo
* **Nuevos exchanges asociados :** Bitget y Nash
* **Nueva estrategia para trading en spot**: [Support / Resistance](../../trading-strategy-options/regular-strategies-spot-trading/support-resistance.md)
* **Cierre con PND**: una alternativa al seguimiento de ROE para conseguir mayores beneficios en estrategias de margin. PND intenta esperar hasta que se desarrolle un movimiento antes de cerrar posición
* **Método alternativo de seguimiento de ROE para estrategias de margin:** con `ROE_SCALPER` el rango de seguimiento es un valor absoluto de ROE
* **Generador de liquidez para los mercados spot:** proporciona liquidez y beneficios de la diferencia ente oferta y demanda \(bid/ask\)
* **Compartir estrategias más fácil**: importa partes de `config.js` o `autoconfig.json` usando la interfaz gráfica
* **Almacena más historial de ordenes:** para mejorar los cálculos de beneficios / perdidas y evitar advertencias innecesarias de "introduzca precio de compra" \("bought price"\), el historial completo de ordenes ahora se guarda localmente a lo largo del tiempo
* **Alertas de TradingView**: ahora puede cambiar de estrategia a través de una alerta, habilita `TV_TRADING_LIMIT_CAP`
* **Alerts \(beta\):** build your own strategy in a visual way using built-in TradingView charts

### Market Maker

* **New strategy variants**: Grid, Support/Resistance, Fibonacci, Pullback, One Scalper, x125 & Moto

### AutoConfig

* **Editor and stats in the GUI**: every single AutoConfig feature is now editable through the GUI, every config change is visible on the AutoConfig dashboard
* **More filter types**: add pairs with linear regression filters, more [options ](../../how-to-work-with-gunbot/extras/autoconfig.md#generic-filters)to filter your own variables
* **Use your own logic:** most values in Autoconfig jobs can now optionally use [custom JavaScript expressions](../../how-to-work-with-gunbot/extras/autoconfig.md#calculated-config-values-and-custom-filters). Expressions have access to almost all internal bot data
* **Silent mode**: disable console logs for AutoConfig

### Bugfixes

* Numerous exchange specific trading execution fixes
* Fix closelong / closeshort alerts for Kraken Futures and Binance Futures
* Work around Kraken cloudflare issue in ccxt library
* Add support for all new pairs on Kraken \(on other exchange this happens automatically\)
* Prevent firing orders if MM bots receive sudden strange balance or ROE values
* Fix problem that prevented proper handover from DU to RT

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}

