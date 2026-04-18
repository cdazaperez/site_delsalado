# 🌿 Del Salado — Guía de administración

**Versión con archivos separados** — fácil de administrar y cambiar imágenes.

---

## 📁 ¿Qué hay en esta carpeta?

```
delsalado-administrable/
├── index.html     ← El sitio web principal
├── img/           ← Carpeta de imágenes (puedes cambiarlas aquí)
│   ├── miel-tarro.jpg
│   ├── cafe-bolsa.jpg
│   ├── tostando-cafe.jpg
│   ├── polen-bolsa.jpg
│   ├── aguacate-rama.jpg
│   ├── productor-aguacate.jpg
│   ├── apicultor.jpg
│   └── ... (12 imágenes total)
└── ADMIN.md       ← Esta guía
```

---

## ✏️ Cómo cambiar precios y productos (SÚPER FÁCIL)

### 1. **Abre `index.html`** con cualquier editor de texto:
   - **Windows:** Notepad, Notepad++, VS Code
   - **Mac:** TextEdit, VS Code, Sublime Text
   - **Online:** Puedes usar CodePen.io si no tienes editor

### 2. **Busca la palabra `CONFIG`** — verás un bloque así:

```javascript
const CONFIG = {
  // --- Contacto ---
  whatsapp:  "573124479914",   // ← cambiar WhatsApp aquí
  telefono2: "573003528083",
  instagram: "delsaladoorigen",
  
  // --- Productos ---
  productos: [
    {
      nombre: "Miel de abejas",
      precio: 25000,              // ← cambiar precios aquí
      imagen: "img/miel-tarro.jpg"  // ← cambiar imagen aquí
    },
    // más productos...
  ]
}
```

### 3. **Para cambiar un precio:**
```javascript
// ANTES
{ presentacion: "Tarro 500 cc", precio: 25000 }

// DESPUÉS (ejemplo: subir a $30.000)
{ presentacion: "Tarro 500 cc", precio: 30000 }
```
**⚠️ Importante:** No uses puntos ni comas en los números: `30000`, NO `30.000`

### 4. **Guarda el archivo** y listo — todos los precios se actualizan automáticamente

---

## 🖼️ Cómo cambiar las imágenes de productos

### **Opción 1 — Reemplazar imagen (más fácil):**
1. **Comprime tu nueva imagen:**
   - Ve a https://squoosh.app (gratis)
   - Sube tu foto
   - Ajusta a máximo **1200px de ancho**
   - Calidad **75%**
   - Descarga como JPG

2. **Ponle el mismo nombre** que la imagen que quieres cambiar:
   - Si quieres cambiar la miel → nombra tu imagen `miel-tarro.jpg`
   - Reemplaza el archivo en la carpeta `img/`

3. **¡Listo!** La nueva imagen aparece automáticamente

### **Opción 2 — Nueva imagen con nuevo nombre:**
1. Comprime la imagen como arriba
2. Ponle un nombre descriptivo: `mi-nueva-miel.jpg`
3. Guárdala en la carpeta `img/`
4. En `index.html`, busca el producto y cambia:
   ```javascript
   // ANTES
   imagen: "img/miel-tarro.jpg",
   
   // DESPUÉS
   imagen: "img/mi-nueva-miel.jpg",
   ```

---

## 📱 Cómo agregar un producto nuevo

**Copia este bloque completo** y pégalo dentro del array `productos:`:

```javascript
{
  id: "nuevo-producto",                    // ID único (sin espacios)
  categoria: "De la huerta",              // Categoría que aparece arriba
  nombre: "Nuevo producto",               // Nombre principal
  descripcion: "Descripción del producto aquí.",
  imagen: "img/mi-nueva-imagen.jpg",      // Imagen (debe estar en img/)
  tamaño: "third",                        // Tamaño: "wide", "half", "third"
  variantes: [
    { presentacion: "Presentación 1", precio: 15000 },
    { presentacion: "Presentación 2", precio: 25000 }
  ]
},
```

**No olvides la coma `,` al final del bloque!**

---

## 🗑️ Cómo quitar un producto

1. Busca el producto en el array `productos:`
2. Borra **todo el bloque** (desde `{` hasta `},`)
3. Guarda el archivo

---

## 🌐 Cómo publicar en internet

### **Opción 1 — Netlify (GRATIS, 2 minutos):**
1. Ve a https://app.netlify.com/drop
2. **Arrastra toda la carpeta `delsalado-administrable`** al navegador
3. Te dan una URL como: `https://delsalado-abc123.netlify.app`
4. **Para actualizar:** arrastra la carpeta de nuevo

### **Opción 2 — GitHub Pages (GRATIS, más pro):**
1. Crea cuenta en https://github.com
2. Sube toda la carpeta a un repositorio
3. Settings → Pages → Branch: main
4. URL: `https://tuusuario.github.io/delsalado`

### **Opción 3 — Dominio propio:**
- Compra `delsalado.co` en GoDaddy (~40mil COP/año)
- Conecta a Netlify (instrucciones automáticas)

---

## 🛠️ Cambiar contacto/WhatsApp

En el bloque `CONFIG`, cambia:

```javascript
whatsapp:  "573124479914",   // Número principal (con código 57, sin +)
telefono2: "573003528083",   // Segundo teléfono  
instagram: "delsaladoorigen",// Usuario de Instagram (sin @)
```

**Todos los botones de WhatsApp se actualizan automáticamente.**

---

## 🎨 Cambiar colores (avanzado)

En `index.html`, busca `:root{` y cambia:

```css
:root{
  --cream:        #f5eedf;   /* Color de fondo crema */
  --honey-deep:   #9a5e16;   /* Acento dorado principal */
  --olive:        #5c6a3a;   /* Verde de detalles */
  --ink:          #2a1d12;   /* Color de texto principal */
}
```

Usa códigos hexadecimales. Herramienta: https://coolors.co

---

## ❓ Problemas comunes

### **Las imágenes no se ven:**
- Verifica que el nombre del archivo coincida exactamente
- Mayúsculas y minúsculas importan: `Miel.jpg` ≠ `miel.jpg`
- El archivo debe estar en la carpeta `img/`

### **Error en el sitio después de editar:**
- Revisa que no hayas borrado una coma `,` o llave `{}`
- Busca la línea del error en el navegador (F12 → Console)
- Restaura el bloque `CONFIG` desde esta guía

### **WhatsApp no funciona:**
- Número debe tener código país: `573124479914`
- Sin espacios, sin `+`, sin guiones

---

## 🚀 Checklist antes de publicar

- ✅ **Imágenes comprimidas** (usar https://squoosh.app)
- ✅ **Precios actualizados** en CONFIG
- ✅ **WhatsApp funcionando** (probar botones)
- ✅ **Ver el sitio en celular** (navegador → F12 → modo móvil)
- ✅ **Subir carpeta completa** a Netlify (no solo el HTML)

---

## 🆘 Soporte rápido

**Si algo no funciona:**
1. Copia todo el bloque `CONFIG` desde esta guía
2. Pégalo en tu `index.html` (reemplaza el que está)
3. Cambia solo los valores que necesites
4. Guarda y prueba

**¿Necesitas ayuda?** Escribe a tu WhatsApp del sitio y pregunta por soporte técnico.

---

**¡Listo para vender! 🎉**

*Esta guía cubre el 95% de los cambios que necesitarás. Manténla a mano.*
