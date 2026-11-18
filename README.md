# Cambios de Moneda - Paradigma Declarativo

Script SQL **idempotente** para la base de datos `Monedas` (PostgreSQL). Registra los cambios diarios de varias monedas frente al dólar (USD).

## ¿Qué hace el script?

- Agrega las monedas que no existan (por ejemplo, **Bitcoin**).
- Registra los cambios diarios de **Peso colombiano (COP)**, **Euro (EUR)**, **Peso mexicano (MXN)** y **Bitcoin (BTC)** entre el 16 de septiembre y el 15 de noviembre de 2026.
- Si el cambio de una fecha ya existe, actualiza su valor.
- Se puede ejecutar las veces que se quiera y siempre deja el mismo resultado.

## Cómo usarlo

1. Tener creada la base de datos `Monedas` con sus tablas `Moneda` y `CambioMoneda`.
2. Verificar que la secuencia de `Moneda` esté sincronizada con los Id existentes.
3. Ejecutar `DML - Monedas - Cambios 2 Ultimos Meses.sql`.

## Datos

El cambio se expresa como unidades de la moneda por 1 dólar (USD).

Fuentes: currencybeacon.com (COP, EUR, MXN), Bitstamp y StatMuse (BTC).
