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

## ☁️ Datos compartidos en la nube (sin login)

Los datos se guardan en una base de datos **Supabase** compartida por todo el proyecto. La conexión va **incrustada en la app**: no hay que iniciar sesión ni pegar ninguna clave. Abres la app, los datos ya aparecen, añades cosas y **se guardan solos**. Quien abra la app (en cualquier dispositivo) ve y edita los mismos datos.

**Configuración (una sola vez, ya hecha):** en el **SQL Editor** de Supabase se creó la tabla compartida con este código:

```sql
create table if not exists inventario_datos (
  id text primary key,
  data jsonb not null default '{}'::jsonb,
  updated_at timestamptz not null default now()
);
grant all on table inventario_datos to anon;
```

El botón **☁️** (arriba a la derecha) solo **muestra el estado**: *Guardando…*, *Guardado ✓* o *Sin conexión*. Si lo pulsas, refresca los datos desde la nube (por si alguien más añadió algo). No hay que sincronizar nada a mano; la app también trae los cambios de otros cada pocos segundos.

Si te quedas sin internet, la app sigue funcionando en local y sube los cambios cuando vuelve la conexión.

> ⚠️ **Nota:** al no haber login, cualquiera que tenga la app puede ver/editar estos datos. Como es una herramienta interna del proyecto (la app no se reparte a desconocidos), es un intercambio razonable de comodidad por seguridad. La clave incluida es la **anon** (pública), no la secreta.

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
