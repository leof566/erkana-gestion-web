# ERKANA Gestión PRO

Agenda de pedidos, calendario de entregas, calculadora de precios, control de stock y tickets JPG/PDF para ERKANA Remeras, EK3D Impresiones, EK Laser y LD Mixto.

## Estado
- El código de la aplicación está publicado en este repositorio como `index.html`.
- El sitio web requiere habilitar **GitHub Pages** en la configuración del repositorio; publicar el código y publicar el sitio son cosas distintas.
- Los pedidos y clientes **no se almacenan en este repositorio público**.
- La aplicación empieza guardando en el navegador local. La sincronización GitHub debe activarse explícitamente y requiere autorización.

## Cómo abrir la aplicación desde celular y PC
1. Abrir [Settings → Pages](https://github.com/leof566/erkana-gestion-web/settings/pages).
2. Seleccionar **Source: Deploy from a branch**.
3. Seleccionar **Branch: main**, carpeta **/(root)** y pulsar **Save**.
4. Comprobar que GitHub Pages muestra el enlace publicado en la misma pantalla. Habitualmente es `https://leof566.github.io/erkana-gestion-web/`.
5. Abrir ese mismo enlace desde ambos equipos. El código se actualiza al subir cambios a `main`.

## Activar sincronización de pedidos

**Antes de conectar:** abrir [Settings del repositorio de datos](https://github.com/leof566/erkana-gestion-datos/settings) y verificar que **erkana-gestion-datos sea PRIVATE**. En GitHub, Settings → General → Danger Zone → Change repository visibility → Make private. La aplicación comprueba esta condición y **rechaza subir datos si el repositorio es público**.

1. En la cuenta GitHub generar un **Personal access token (fine-grained)** limitado exclusivamente al repositorio **erkana-gestion-datos**; dar **Contents: Read and write** (Metadata: Read es automático).
2. Dentro de la aplicación, ir a **Configuración → Sincronización GitHub**. Usuario: `leof566`, repo: `erkana-gestion-datos`, rama `main`, ruta: `data/gestion.json`.
3. Pegar el token **solamente en el campo de la aplicación**. Presionar **Guardar y sincronizar**.
4. Esperar a que muestre **Nube al día**. Repetir la configuración en el otro dispositivo usando la misma URL.
5. Verificar la sincronización creando un pedido de prueba y comprobando que aparece en el otro equipo.

**Seguridad:** nunca subir tokens ni respaldos con nombres, teléfonos o pedidos a `erkana-gestion-web`. No compartir el token por chat ni guardarlo en un equipo ajeno. La opción de recordar token usa el almacenamiento del navegador; se recomienda un dispositivo personal protegido. Un token del navegador puede quedar expuesto si el dispositivo o el sitio están comprometidos. Para un negocio con más operadores o controles avanzados conviene migrar a autenticación y base de datos privadas mediante un servidor.

**Limitación de simultaneidad:** las actualizaciones son periódicas; si dos dispositivos modifican el mismo pedido al mismo tiempo, prevalece el registro con la fecha de modificación más reciente. Hacer copias de seguridad JSON regularmente.

## Funciones
- Pedidos con cliente, teléfono, marca, fecha, detalle, cantidades, precios, descuentos, entrega, seña, saldo y estados.
- Agenda mensual y avisos de entregas pendientes.
- Productos, costos, SKU, movimientos de stock y alertas de stock mínimo.
- Calculadora de precio de venta con materiales, mano de obra, extras, comisiones y margen.
- Tickets PDF y JPG con elección de marca.
- Reportes, CSV y respaldo/restauración JSON.

Los tickets son comprobantes de pedido, **no facturas fiscales**.

## Desarrollo
Esta versión es una aplicación estática autocontenida en `index.html`, sin instalación ni compilación. Para modificaciones, editar el archivo y hacer commit en `main`. No guardar datos de clientes en este repositorio.
