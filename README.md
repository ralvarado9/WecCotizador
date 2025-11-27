# 🛒 Cotizador de Cámaras CCTV (Web)

Formulario web para levantar información de clientes interesados en sistemas de videovigilancia (CCTV).  
Permite **registrar, consultar y descargar cotizaciones** usando únicamente el navegador, sin necesidad de servidor o base de datos externa.

---

## 🌟 Funcionalidades principales

- **Formulario completo de datos del cliente**
  - Nombre completo
  - WhatsApp y teléfono adicional
  - Tipo de lugar (Casa, Negocio, Bodega, Terreno, Escuela)
  - Colonia o zona
  - Áreas a monitorear

- **Características técnicas del sistema**
  - Si ya tiene cámaras instaladas (marca / modelo)
  - Qué desea adquirir (kit completo, solo cámaras, solo instalación, accesorios)
  - Tipo de cámara (interior / exterior)
  - Resistencia (normal / uso rudo)
  - Tecnología (WiFi, cableada o “no sé”)
  - Visión nocturna (infrarroja, a color o no)
  - Resolución en megapíxeles (2MP, 5MP, 8MP)
  - Cantidad de cámaras necesarias
  - Metros de cable por cámara
  - Tipo de grabación (24/7 o por movimiento)
  - Si desea ver desde el celular
  - Presupuesto aproximado
  - Comentarios adicionales

- **Generación automática de folios**
  - Folios con el formato: `COTIZA0001`, `COTIZA0002`, etc.
  - El folio se almacena en `localStorage` para llevar el consecutivo.

- **Almacenamiento local de cotizaciones**
  - Las cotizaciones se guardan en `localStorage` del navegador bajo la llave `cotizacionesCCTV`.
  - Permite **consultar una cotización por folio** y rellenar el formulario con sus datos.

- **Descarga automática de archivo de texto**
  - Al guardar una cotización, se descarga un archivo `.txt` con todos los datos capturados.
  - El archivo se nombra con el folio, por ejemplo: `COTIZA0001.txt`.

- **Interfaz amigable y responsiva**
  - Estilos con CSS puro, integrados en el mismo archivo HTML.
  - Diseño adaptado para escritorio y pantallas pequeñas (grid responsivo).

---

## 🧱 Tecnologías utilizadas

- **HTML5**  
- **CSS3** (incluido dentro del mismo archivo HTML)  
- **JavaScript** (incluido dentro del mismo archivo HTML)  
  - Uso de `localStorage` para almacenar datos en el navegador.
  - Manejo de eventos de formulario (`submit`) y botones.
  - Generación y descarga de archivos de texto con `Blob` y `URL.createObjectURL`.

---

## 📂 Estructura del proyecto

Actualmente el proyecto está contenido en un solo archivo:

- `index.html`  
  - Contiene:
    - La estructura del formulario (HTML)
    - Los estilos (CSS en la etiqueta `<style>`)
    - La lógica de negocio (JavaScript en la etiqueta `<script>`)

> Si lo deseas, en el futuro puedes separar el código en:
> - `index.html`
> - `styles.css`
> - `app.js`

---

## ▶️ Cómo ejecutar el proyecto

No requiere instalación ni servidor especial.

1. Clona o descarga este repositorio.
2. Abre el archivo `index.html` en un navegador moderno:
   - Doble clic sobre el archivo, o
   - Arrástralo a una ventana de Chrome/Edge/Firefox.
3. Comienza a capturar los datos de tus clientes y presiona **“Guardar Cotización”**:
   - Se generará un **folio nuevo**.
   - Se guardará una copia en `localStorage`.
   - Se descargará un archivo `.txt` con la información.

---

## 🔍 Consulta de cotizaciones por folio

En la parte superior del formulario:

1. Escribe el folio (por ejemplo `COTIZA0001`) en el campo **“Folio”**.
2. Haz clic en **“Buscar”**.
3. Si existe una cotización con ese folio:
   - El formulario se rellenará automáticamente con sus datos.
   - Se mostrará un mensaje indicando que la cotización fue cargada.
4. Si no existe:
   - Se mostrará un mensaje de error indicando que no se encontró ese folio.

El botón **“Nuevo”**:
- Limpia el formulario.
- Genera visualmente el siguiente folio disponible.

---

## 💾 Dónde se guardan los datos

El proyecto **no usa base de datos en servidor**.  
Toda la información se guarda en el navegador del usuario mediante:

- `localStorage['cotizacionesCCTV']` → objeto JSON con todas las cotizaciones.
- `localStorage['ultimoFolioCCTV']` → número del último folio usado.

> Esto significa que:
> - Los datos solo estarán disponibles en **ese navegador y ese dispositivo**.
> - Si borras el caché o los datos del navegador, se perderán las cotizaciones guardadas.

---

## ✅ Requisitos

No hay un `requirements.txt` ni dependencias externas, solo necesitas:

- Un **navegador moderno**:
  - Google Chrome, Microsoft Edge, Mozilla Firefox, etc.
- (Opcional) Un servidor estático para desarrollo, por ejemplo:
  - Extensión **Live Server** de VS Code, o cualquier servidor web simple.
  
---

## 📝 Notas y posibles mejoras

Algunas ideas para futuras versiones:

- Exportar las cotizaciones en formato **JSON** o **CSV**.
- Enviar la cotización por **correo** o **WhatsApp** automáticamente.
- Conectar a un backend (API o base de datos real) para centralizar la información.
- Agregar validaciones más estrictas (teléfono, presupuesto, campos obligatorios, etc.).
- Panel administrativo para listar y filtrar todas las cotizaciones guardadas.

---

## 👨‍💻 Autor

Proyecto desarrollado por **RothSoft / Cyber Junior’s**  
- Facebook: [RothSoft](https://www.facebook.com/rothsoft)  
- Página: [Cyber Junior’s](https://www.facebook.com/cyberjuniorss)
