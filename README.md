# Waldo Deco — Catálogo Web

Catálogo de productos con carrito y pedidos por WhatsApp, alojado en GitHub Pages.

---

## Estructura de archivos

```
/
├── index.html      
├── products.json     
├── README.md
└── imgs/
    ├── LAMP-001_1.jpg
    ├── LAMP-001_2.jpg
    └── ...
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
