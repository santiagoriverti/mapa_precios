# Mapa Interactivo de Precios

Mapa georreferenciado de precios de productos en supermercados argentinos.

🗺️ **[Ver mapa](https://santiagoriverti.github.io/mapa_precios/)**

---

## ¿Qué muestra el mapa?

Cada punto es una **sucursal de supermercado**, ubicada por sus coordenadas reales. El color indica
el precio del producto seleccionado en esa sucursal: **verde = más barato**, **rojo = más caro**. La
escala se recalcula para cada producto (percentiles 5 a 95), así que los colores siempre comparan
sucursales **entre sí para el mismo producto**.

**Agosto 2026 · 2.208 sucursales · 19 productos.** No todos los productos están en todas las
sucursales: el panel de arriba dice cuántas informan el producto que está seleccionado (por ejemplo,
2.066 para la Cerveza Imperial Lager 473 Cc).

Los precios son los **promedios del mes** por sucursal, con los valores atípicos removidos.

---

## Cómo usar el mapa

**Panel de filtros** — abajo a la izquierda en la computadora; en el celular es la barra
*🔍 Filtros* del pie, que se abre y se cierra tocándola:

- **Producto** — cambia el producto que se está mapeando; la escala de color y el promedio se
  recalculan solos
- **Cadena** — deja sólo Coto, DIA, Carrefour, Disco, etc.
- **Provincia** — aísla una jurisdicción
- **Restablecer** — vuelve al estado inicial

**Pasar el mouse** sobre una sucursal muestra cadena, provincia y precio. **Al hacer click** se abre
el detalle: nombre del local, cadena, barrio o localidad, provincia, tipo de comercio y el precio del
producto seleccionado.

El mapa tarda unos segundos en dibujarse la primera vez: son ~2.000 puntos que se generan en el
navegador. Mientras tanto se ve el cartel *Cargando el mapa*.

---

## Datos y método

- **Fuente**: [SEPA](https://datos.produccion.gob.ar/dataset/precios-claros-base-sepa) (Sistema
  Electrónico de Publicidad de Precios Argentinos) — precios de lista publicados por las cadenas.
  No incluye descuentos por tarjeta ni promociones.
- **Pipeline que genera este mapa**: [`precios_minoristas_supermercados`](https://github.com/santiagoriverti/precios_minoristas_supermercados)
  (notebook `05_evolucion_productos_representativos`, CELDA 17). Este repo sólo publica el HTML.
- **Fondo del mapa**: la página prueba varios proveedores de mosaicos (Esri, OpenStreetMap,
  OpenTopoMap, CartoDB) y se queda con el primero que responda desde la red de quien la abre. Si no
  responde ninguno, avisa: los datos y los puntos igual se ven, lo que falta es el fondo.

---

## Actualizar el mapa

Correr el notebook 05 en Colab, descargar `mapa_interactivo_MMAAAA_prom.html` de
`MyDrive/carga/output_productos/`, renombrarlo a `index.html` y reemplazar el de este repo.
GitHub Pages lo publica solo en menos de un minuto.

---

## Contacto

Santiago Riverti
✉️ santiagoriverti@gmail.com
