# Sistema de Cotizaciones — Agencia de Viajes

Aplicación web de una sola página (SPA) para generar, gestionar y administrar cotizaciones de viajes. Diseñada específicamente para agencias de viajes, con soporte para 3 formatos (América, Europa/Asia, Cruceros), módulos de clientes, ventas con checklist, historial, y calculadora de costos integrada.

## Características principales

### Editor de cotizaciones
- **3 formatos de cotización**: América, Europa/Asia, Cruceros
- **Vista previa en vivo** que refleja exactamente el PDF final
- **Selector de destino con imagen de encabezado** personalizada por país/destino
- **Hospedajes con rango de fechas** (selector de calendario + traducción automática a texto)
- **Itinerario propuesto** tipo Excel con copy/paste desde hoja de cálculo y auto-rellenado de fechas
- **Calculadora estilo Excel** por hotel: Boleto + Hotel + Tours + Transporte + Fee = Total automático
- **Adjuntos internos** (imágenes de vuelos, hospedajes, tours) con lightbox, no visibles al cliente
- **Logo y marca de agua** personalizables
- **Exportación a PDF** nativa del navegador (Ctrl+P)

### Gestión CRM
- **Historial**: todas las cotizaciones guardadas, filtrables por estado (aceptadas/pendientes)
- **Ventas**: se crean automáticamente al marcar una cotización como "Oferta aceptada", con checklist de coordinación editable
- **Clientes**: base de datos de clientes con todos los campos relevantes para agencias (pasaporte, nacionalidad, programa viajero frecuente, etc.)
- **Encabezados**: gestor de imágenes de header organizado por país y destino

### Configuración
- Todos los datos de la agencia son editables sin tocar código:
  - Nombre, teléfono, cédula, eslogan
  - Lista de encargados
  - Servicios incluidos por defecto (por formato)
  - Políticas de viaje (por formato)
  - "No incluye" (por formato)
  - Cuentas bancarias para pagos
  - Items del checklist de ventas
  - Fees de la calculadora (reserva, adulto, niño, bebé)

## Cómo usarla

### Opción 1: Desde la web (GitHub Pages)
Abrí la aplicación directamente en tu navegador: **https://tony20154689-ui.github.io/cotizaciones-deseos-viajeros/**

No requiere instalación. Los datos se guardan en el `localStorage` del navegador.

### Opción 2: Archivo local
Descargá `cotizacion.html` y abrilo en cualquier navegador moderno (Chrome, Edge, Firefox).

## Primeros pasos

1. **Abrí la app** en tu navegador
2. **Andá a Configuración → Agencia** y completá los datos de tu empresa (nombre, teléfono, cédula, eslogan)
3. **Configurá las cuentas bancarias** en Configuración → Cuentas bancarias
4. **Agregá tus encargados** en Configuración → Encargados
5. **Cargá las imágenes de encabezado** para cada país/destino en la sección Encabezados
6. Ya podés crear tu primera cotización en Editor

## Almacenamiento de datos

Todos los datos se guardan localmente en el navegador del usuario usando `localStorage`:

| Clave | Contenido |
|-------|-----------|
| `dv_config` | Configuración de la agencia |
| `dv_cotizaciones` | Historial de cotizaciones guardadas |
| `dv_encabezados` | Imágenes de encabezado por país/destino |
| `dv_ventas` | Ventas (generadas desde cotizaciones aceptadas) |
| `dv_clientes` | Base de datos de clientes |
| `dv_form_panel_width` | Ancho preferido del panel del editor |

**Importante**: los datos viven en el navegador de cada usuaria. Si se borra el caché o se cambia de navegador, los datos se pierden. Para backup, considerar exportar las cotizaciones del historial periódicamente.

## Stack técnico

- **HTML5 + CSS3 + JavaScript vanilla** — sin frameworks, sin build step
- **LocalStorage** para persistencia
- **Tipografías**: Playfair Display, Open Sans, Dancing Script (Google Fonts)
- **Un solo archivo** (`cotizacion.html`) con todo embebido — fácil de distribuir y hostear

## Desarrollo

Para hacer cambios, editá directamente `cotizacion.html` y refrescá el navegador. No hay build, no hay dependencias.

```bash
# Clonar el repo
git clone https://github.com/tony20154689-ui/cotizaciones-deseos-viajeros.git
cd cotizaciones-deseos-viajeros

# Abrir en navegador (Windows)
start cotizacion.html
```

## Licencia

Uso privado. Todos los derechos reservados.
