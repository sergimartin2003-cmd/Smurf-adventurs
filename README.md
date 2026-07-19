# 📦 Inventario & Rentabilidad

Programa sencillo para llevar el **registro de inventario** de tu pequeña empresa y ver **qué productos rentan y cuáles no a largo plazo**.

Todo funciona dentro de un solo archivo (`index.html`). Funciona **sin instalar nada**. Puedes usarlo de dos formas:

- **Modo local** (por defecto): los datos se guardan en tu propio dispositivo. Cero configuración.
- **Modo nube (sincronizado)**: los mismos datos en vivo en el móvil, el ordenador, etc. Requiere una configuración inicial gratuita de ~10 min (ver más abajo).

---

## ▶️ Cómo empezar

1. Abre el archivo **`index.html`** haciendo doble clic (se abre en tu navegador: Chrome, Edge, Safari, Firefox…).
2. Pulsa **«➕ Añadir mi primer producto»** o **«🧪 Cargar datos de ejemplo»** para ver cómo funciona.
3. ¡Listo! El programa recuerda tus datos aunque cierres el navegador.

> 💡 **Consejo:** guarda el archivo en un sitio fácil (Escritorio) y arrástralo a la barra de marcadores de tu navegador para abrirlo de un clic. También puedes usarlo desde el móvil enviándote el archivo y abriéndolo con el navegador.

---

## 🧭 Qué puedes hacer

### 📊 Panel
Vista rápida de tu negocio: **beneficio acumulado**, ingresos, valor del inventario, avisos (productos en pérdidas o con poco stock), gráfico de los últimos 6 meses y una **proyección de beneficio anual** según tu ritmo.

### 📦 Productos
El apartado donde metes **toda la información** de cada cosa:
- Nombre, categoría y código.
- **Coste de compra** y **gastos extra** por unidad (envío, embalaje…).
- **Precio de venta** por unidad.
- **Stock actual** y aviso de stock mínimo.

Desde aquí puedes **añadir, editar o borrar** productos, y con un clic **Vender** o **Reponer**. También puedes **exportar a Excel (CSV)**.

### 🔁 Movimientos
El historial de cada **venta**, **reposición/compra** y **ajuste** de stock. El stock se actualiza solo. Puedes borrar un movimiento y el stock se corrige automáticamente.

### 💹 Rentabilidad
El análisis clave: separa tus productos en **los que más rentan**, **los que no rentan** (los vendes por debajo del coste o dan pérdidas) y **los que aún no has vendido**. Así sabes en qué apostar y qué precio revisar.

---

## ☁️ Verlo desde varios sitios (sincronización en la nube)

Si quieres que **los mismos datos aparezcan en todos tus dispositivos** (añades algo en el móvil y lo ves en el ordenador, y al revés), activa el modo nube. Es gratis, usa **Supabase** y se configura una sola vez.

Pulsa el botón **☁️** (arriba a la derecha) y sigue la guía que aparece dentro del programa. En resumen:

1. Crea una cuenta gratis en **supabase.com** y un **New project** (guarda la contraseña de la base de datos).
2. En **SQL Editor**, pega el código que te muestra el programa (botón «Copiar código») y pulsa **Run**. Crea la tabla donde se guardan tus datos, protegida para que solo tú puedas verlos.
3. En **Project Settings → API**, copia el **Project URL** y la clave **anon public**, y pégalos en el programa.
4. Recomendado: en **Authentication → Sign In / Providers → Email**, desactiva **Confirm email** (así entras sin tener que confirmar el correo).
5. Crea tu cuenta con email y contraseña dentro del programa. ¡Listo!

A partir de ahí, cada cambio se guarda en la nube automáticamente. Para usarlo en otro dispositivo, abre la misma web, conecta el mismo proyecto y entra con tu email. El botón **☁️** muestra el estado: *Local*, *Sincronizado ✓*, *Guardando…* o *Sin conexión*. Si te quedas sin internet, se guarda en local y se sube cuando vuelves a tener conexión.

> 🔒 **Privacidad:** tus datos solo son visibles para tu cuenta (con contraseña). El código SQL activa la seguridad por filas (RLS) de Supabase para que nadie más pueda leerlos.

---

## 💾 Copias de seguridad (importante)

Como los datos se guardan en tu dispositivo, conviene hacer copias:

- **⬇️ Copia** (arriba a la derecha): descarga un archivo con todos tus datos. Guárdalo de vez en cuando.
- **⬆️ Restaurar**: vuelve a cargar esos datos (por ejemplo en otro ordenador o móvil).

Así también puedes **pasar tus datos de un dispositivo a otro**.

---

## 🧮 Cómo se calcula la rentabilidad

- **Coste real por unidad** = coste de compra + gastos extra.
- **Margen por unidad** = precio de venta − coste real.
- **Beneficio de un producto** = suma del margen de todas sus ventas.
- **Beneficio anual estimado** = media del beneficio de los meses con ventas × 12.

Cada venta guarda el coste que tenía el producto en ese momento, así el cálculo del beneficio a largo plazo es fiable aunque luego cambies precios o costes.

---

## ❓ Preguntas frecuentes

**¿Se pierden los datos si cierro el navegador?** No. Se guardan solos. Solo se borrarían si limpias los datos del navegador o cambias de dispositivo (por eso existen las copias de seguridad).

**¿Puedo cambiar la moneda?** Sí, con el selector de arriba a la derecha (€, $, £, MXN, COP, ARS).

**¿Necesito internet?** No. Funciona sin conexión.
