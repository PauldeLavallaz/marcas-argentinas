# Marcas Argentinas — Pool de Contenido

Pool de marcas argentinas reales para el pipeline de generación de contenido de Morfeo Labs.

## Estructura

```
marcas.json          → Lista de marcas con metadata
images/              → Imagen del producto de cada marca
```

## marcas.json

Cada entrada tiene:
- `id` — identificador único (snake_case)
- `nombre` — nombre de la marca tal como aparecerá en el guión
- `categoria` — tipo de producto
- `descripcion` — contexto para el guión (qué es, para qué sirve, qué emoción genera)
- `imagen` — path relativo a la imagen del producto

## Cómo agregar una marca

1. Agregar la imagen del producto en `images/` (JPG, mínimo 500px)
2. Agregar entrada en `marcas.json`:

```json
{
  "id": "mi_marca",
  "nombre": "Nombre de la Marca",
  "categoria": "Categoria",
  "descripcion": "Descripción del producto para contexto del guión.",
  "imagen": "images/mi_marca.jpg"
}
```

## Categorías actuales

- Alimentos
- Bebidas
- Lácteos
- Panadería / Confitería / Gastronomía
- Indumentaria / Accesorios
- Tecnología / Electrodomésticos
- Papelería / Infusiones

## Uso en el pipeline

El pipeline elige una marca aleatoriamente y usa:
- `nombre` → para el guión de Gemini
- `imagen` → como input `product` en Morpheus
- `descripcion` → como contexto adicional para el brief
