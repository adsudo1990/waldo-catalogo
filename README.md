# Waldo Deco — Catálogo Web

Catálogo de productos con carrito y pedidos por WhatsApp, alojado en GitHub Pages.

---

## Estructura de archivos

```
/
├── index.html        ← el catálogo (no modificar)
├── products.json     ← tus productos (editá este archivo)
├── README.md
└── imgs/
    ├── LAMP-001_1.jpg
    ├── LAMP-001_2.jpg
    └── ...
```

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
