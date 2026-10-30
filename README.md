# SIGE – primera base instalable para Android

Este proyecto es un prototipo de aplicación web progresiva (PWA) para SIGE.

## Incluye
- Instalación como acceso de aplicación desde Chrome en Android (cuando se publica bajo HTTPS).
- Base de datos local IndexedDB en el navegador del dispositivo.
- Creación inicial de contraseña de administrador (hash PBKDF2 con salt).
- Registro de empresas, clientes, personal y órdenes de trabajo.
- Exportación e importación de respaldo JSON.
- Interfaz adaptable a teléfono y computador.
- Archivos de caché para una primera experiencia sin conexión.

## Importante: alcance de esta primera entrega
- No contiene sincronización en la nube.
- No tiene usuarios individuales para supervisores y trabajadores todavía.
- No incluye captura de cámara ni firma digital real todavía.
- No reemplaza un sistema de producción ni una solución de seguridad auditada.
- La contraseña protege el acceso a la interfaz; no cifra por sí sola los datos de IndexedDB.
- La base local depende del perfil del navegador y del dispositivo. Si se borran los datos del navegador o se pierde el teléfono, se pueden perder los registros. Exporta respaldos periódicamente.
- Para multiusuario, sincronización y recuperación de contraseña se debe desarrollar un backend seguro y una política de copias de seguridad.

## Cómo probar
La PWA necesita un origen seguro (HTTPS o localhost) para el service worker y la instalación.
1. Publica la carpeta completa en un hosting estático con HTTPS.
2. Abre la dirección en Chrome de Android.
3. Usa el menú de Chrome y selecciona **Instalar aplicación** o **Agregar a pantalla principal**.
4. Abre SIGE y crea la contraseña de administrador.

Para probar en un computador durante desarrollo, sirve esta carpeta con un servidor web local. Abrir index.html directamente como archivo no habilita todas las funciones PWA.

## Estructura
- `index.html`: interfaz
- `styles.css`: diseño adaptable
- `app.js`: lógica y base local IndexedDB
- `manifest.webmanifest`: configuración de instalación
- `sw.js`: caché para funcionamiento básico sin conexión
- `icons/`: iconos de la aplicación

## Próximas etapas recomendadas
1. Implementar edición y eliminación con confirmaciones y registro de auditoría.
2. Completar planificación diaria/semanal/mensual y alertas.
3. Captura y almacenamiento de fotos.
4. Firma de recepción con identificación del firmante y sello de tiempo.
5. Backend central, autenticación individual y sincronización con resolución de conflictos.
6. Cifrado de datos sensibles, respaldos automáticos y pruebas de seguridad.
