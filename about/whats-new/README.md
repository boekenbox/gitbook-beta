---
description: >-
  Esta es una descripción rápida de los cambios más importantes introducidos en
  la V20
---

# Que es lo nuevo?

Gunbot v20 introduce una interfaz completamente nueva construida usando la librería de gráficos de TradingView. con opciones más fáciles para crear y editar los parámetros de la estrategia. También incluye muchos cambios y mejoras en la estabilidad.

## **Mejorando**

{% hint style="success" %}
**Nuevo: herramienta de importación de configuración**

Ahora es realmente fácil cargar un archivo config.js o autoconfig.json en la interfaz e importar solo las partes que necesita de él. Puede usar esto para configurar una instalación limpia v20 mientras migra sus pares, estrategias y otras configuraciones antiguas.

**Pasos para comenzar con una instalación limpia:** extraiga v20 y ejecute, ingrese la dirección de tu cartera Gunthy en el asistente, seleccione "otro" en la pestaña intercambio y guarde los cambios. Luego vaya a Perfil &gt; Importar parámetros y seleccione las partes que quiera importar de su configuración antigua. 
{% endhint %}

No hay cambios de configuración importantes para v20. En caso de que esté actualizando desde v18.x, lo único que necesita es reemplazar el archivo ejecutable  _\(gunthy-win.exe / gunthy-linux / gunthy-macos\)_  y la carpeta _node\_modules_.

![La GUI requiere que la autenticaci&#xF3;n de contrase&#xF1;a est&#xE9; habilitada en config.js. Config&#xFA;relo as&#xED;.](../../.gitbook/assets/image%20%2874%29.png)

Los nuevos parámetros de estrategia se fusionan automáticamente en sus estrategias tan pronto como inicie sesión en la interfaz gráfica del navegador.

En caso de que esté actualizando desde una versión anterior a la v18, consulte los registros de cambios de versiones anteriores para obtener instrucciones o comience una instalación nueva.

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}

## Cambios en v20

Solo se enumeran los cambios más importantes.

### Núcleo / GUI

* **Interfaz gráfica completamente nueva:** rendimiento mejorado, más fácil de usar, mejores gráficos, terminal manual de trading mejorado, más estadísticas, asistente de configuración para novatos
* **Guardar cambios en configuración sin reiniciar:** el ciclado de pares ya no se reinicia cuando se guarda un cambio en la configuración. Los nuevos ajustes entran en vigor en el siguiente ciclo
* **Nuevos intercambios asociados :** Bitget y Nash
* **Nueva estrategia para trading en spot**: [Support / Resistance](../../trading-strategy-options/regular-strategies-spot-trading/support-resistance.md)
* **Cierre con PND**: una alternativa al seguimiento de ROE para conseguir mayores beneficios en estrategias de margen. PND intenta esperar hasta que se desarrolle un movimiento antes de cerrar posición
* **Método alternativo de seguimiento de ROE para estrategias de margen:** con `ROE_SCALPER` el rango de seguimiento es un valor absoluto de ROE
* **Generador de liquidez para los mercados spot:** proporciona liquidez y beneficios de la diferencia ente oferta y demanda \(bid/ask\)
* **Compartir estrategias más fácil**: importa partes de `config.js` o `autoconfig.json` usando la interfaz gráfica
* **Almacena más historial de ordenes:** para mejorar los cálculos de beneficios / perdidas y evitar advertencias innecesarias de "introduzca precio de compra" \("bought price"\), el historial completo de ordenes ahora se guarda localmente a lo largo del tiempo
* **Alertas de TradingView**: ahora puede cambiar de estrategia a través de una alerta, habilita `TV_TRADING_LIMIT_CAP` para Bitmex, mejor manejo de múltiples correos entrantes
* **Alertas \(beta\):** cree su propia estrategia de forma visual utilizando los gráficos integrados de TradingView

### Market Maker

* **Nuevas variantes de estrategias**: Grid, Support/Resistance, Fibonacci, Pullback, One Scalper, x125 & Moto

### AutoConfig

* **Editor y estadísticas en la interfaz gráfica \(GUI\)**: cada función de AutoConfig ahora se puede editar a través de la GUI, cada cambio de configuración es visible en el panel de AutoConfig
* **Más tipos de filtros**: agregue pares con filtros de regresión lineal, más opciones para filtrar sus propias variables
* **Use su propia lógica:** la mayoría de los valores en los trabajos de AutoConfig a hora pueden usar opcionalmente [expresiones personalizadas de JavaScript](../../how-to-work-with-gunbot/extras/autoconfig.md#calculated-config-values-and-custom-filters). Las expresiones tienen acceso a casi todos los datos internos del bot
* **Modo silencioso**: Deshabilite los registros de la consola para AutoConfig

### Corrección de errores

* Numerosas correcciones de ejecución de operaciones especificas de intercambio
* Corrección de aleras de cierre largo / corto \(closelong / closeshort\) para Kraken Futures y Binance Futures 
* Solución al problema del exchange Kraken con la biblioteca ccxt
* Soporte para todos los pares nuevos en Kraken \(en otros intercambios, esto sucede automáticamente\)
* Previene de enviar ordenes si el bot MM recibe un valor extraño / repentino de saldo o ROE
* Soluciona un problema que impedía pasar de DU a RT

{% page-ref page="../../setup-and-general-settings/installation/download.md" %}

