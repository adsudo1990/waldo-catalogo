# Waldo Deco — Catálogo Web

Catálogo de productos con carrito y pedidos por WhatsApp, alojado en GitHub Pages.

---

## Estructura de archivos

```
/
├── index.html            ← el catálogo (no modificar a mano)
├── admin-productos.html  ← herramienta local para cargar/editar productos y exportar products.json
├── products.json         ← tus productos (se genera con admin-productos.html o se edita a mano)
├── robots.txt            ← indica a Google que puede indexar el sitio
├── sitemap.xml           ← mapa del sitio para buscadores
├── README.md
└── imgs/
    ├── LAMP-001_1.jpg
    ├── LAMP-001_2.jpg
    └── ...
```

---

## Cargar productos con la herramienta local (recomendado)

En vez de editar `products.json` a mano, abrí `admin-productos.html` haciendo doble click (no necesita internet ni servidor).

1. Si ya tenés productos cargados, hacé click en **↑ Importar products.json** y seleccioná tu archivo actual.
2. Completá el formulario de la izquierda para cada producto nuevo (o hacé click en uno de la lista para editarlo).
3. Los cambios se guardan automáticamente en tu navegador mientras trabajás, así que si cerrás la pestaña por error no perdés lo cargado.
4. Cuando termines, hacé click en **↓ Exportar products.json** y subí ese archivo a GitHub reemplazando el anterior.

La herramienta avisa si hay IDs repetidos, categorías que no existen en el catálogo, o productos sin fotos.

---

## Cómo agregar o editar productos

Abrí `products.json` con Sublime Text y editá la lista.  
Cada producto sigue este formato:

```json
{
  "id": "LAMP-002",
  "name": "Lámpara Esfera",
  "category": "Lámparas",
  "desc": "Descripción del producto. Materiales, uso, medidas.",
  "price": 5500,
  "images": [
    "imgs/LAMP-002_1.jpg",
    "imgs/LAMP-002_2.jpg"
  ]
}
```

### Campos obligatorios

| Campo | Descripción |
|---|---|
| `id` | Identificador único, sin espacios. Ej: `LAMP-002` |
| `name` | Nombre visible en el catálogo |
| `category` | Ver categorías válidas abajo |
| `desc` | Descripción del producto |
| `price` | Precio en números, sin `$` ni puntos. Ej: `5500` |
| `images` | Lista de rutas. Mínimo una imagen |

### Categorías válidas

```
"Centros de mesa"
"Lámparas"
"Souvenirs"
"Macetas"
"Tortas y repostería"
"Portarretratos"
"Otros"
```

### Convención de nombres de imágenes

```
imgs/ID-DEL-PRODUCTO_1.jpg   ← foto principal
imgs/ID-DEL-PRODUCTO_2.jpg   ← foto adicional (opcional)
imgs/ID-DEL-PRODUCTO_3.jpg   ← etc.
```

Ejemplo para el producto con id `LAMP-002`:
```
imgs/LAMP-002_1.jpg
imgs/LAMP-002_2.jpg
```

---

## Cómo subir cambios a GitHub

1. Editá `products.json` en Sublime Text
2. Agregá las imágenes nuevas en la carpeta `imgs/`
3. En GitHub.com → tu repositorio → arrastrá los archivos modificados
4. O usá GitHub Desktop para sincronizar la carpeta completa

Los cambios se ven en el sitio en 1-2 minutos.

---

## Modo administrador

Para acceder al panel de administración (solo vos):

- **Teclado:** `Shift + Ctrl + F5`
- **O:** 5 clicks rápidos sobre el candado 🔒 en la barra del catálogo

Desde el panel admin podés:
- Configurar tu número de WhatsApp
- Descargar el `products.json` actualizado con el botón **↓ Exportar JSON**

> La contraseña se cambia en `index.html` buscando `ADMIN_PASS`.

---

## Configurar tu número de WhatsApp

1. Activá el modo admin (`Shift + Ctrl + F5`)
2. Ingresá tu número en formato internacional sin `+` ni espacios
3. Ejemplo Argentina: `5491155556666`
4. Hacé click en **Guardar número**

---

## SEO

El `index.html` ya incluye título y descripción para buscadores, vista previa para WhatsApp/redes (Open Graph), y datos estructurados de productos para Google (schema.org). Todo eso usa como dirección del sitio:

```
https://adsudo1990.github.io/waldo-catalogo/
```

Si en algún momento comprás un dominio propio (ej. `waldodeco.com.ar`), buscá esa URL en `index.html`, `robots.txt` y `sitemap.xml` y reemplazala por la nueva — son 3 archivos, unos 6 lugares en total.

---

## Publicar en GitHub Pages

1. Creá un repositorio en [github.com](https://github.com) (público)
2. Subí todos los archivos: `index.html`, `products.json`, carpeta `imgs/`
3. Andá a **Settings → Pages → Branch: main → Save**
4. Tu catálogo estará en: `https://tuusuario.github.io/nombre-del-repo`

---

## Flujo de pedidos

Cuando un cliente hace click en **"Enviar pedido por WhatsApp"** te llega:

```
🛍 NUEVO PEDIDO — Waldo Deco
────────────────────────
Lámpara Colgante Árbol  id:LAMP-001  →  $7.200
Souvenirs Personalizados (x20)  id:FAVOR-001  →  $13.000
────────────────────────
Total del pedido: $20.200
Seña 50%: $10.100
────────────────────────
📅 Fecha: 12/3/2026
```
