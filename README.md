# Barrio Burgos · Reserva de Recursos Tecnológicos

Aplicación web de una sola página (`barrio-burgos-reservas.html`) para que las organizaciones del Barrio Burgos reserven los recursos tecnológicos disponibles (Smart TV, Laptop y Proyector de Video), soliciten apoyo adicional (como impresiones) y para que un administrador pueda gestionar todas las reservas.

No requiere instalación, servidor ni base de datos externa: es un único archivo HTML que se abre directamente en el navegador.

---

## Cómo usarla

1. Abre el archivo `barrio-burgos-reservas.html` en cualquier navegador (Chrome, Safari, Firefox, Edge).
2. Funciona igual en computador, tablet o celular (diseño mobile-first / responsive).
3. No necesitas crear cuenta para reservar un recurso; solo el panel de administrador pide credenciales.

---

## Funcionalidades

### 1. Reservar un recurso
- Selección de **organización**: Cuórum de Elderes, Sociedad de Socorro, Mujeres Jóvenes, Hombres Jóvenes, Primaria, Escuela Dominical de Adultos, Escuela Dominical de Jóvenes 11–14, Escuela Dominical de Jóvenes 15–17, JAS, Obispado.
- Selección de **recurso**: Smart TV (clase mediana), Laptop (clase pequeña), Proyector de Video (clase numerosa).
- Fecha, hora de inicio y hora de fin.
- Nombre de la persona que reserva y propósito/clase (opcional).
- **Detección automática de choques de horario**: si el recurso ya está reservado en ese rango de fecha/hora, la app avisa y no permite guardar hasta elegir otro horario.
- **Apoyo adicional** (casilla opcional):
  - *Impresiones*: cantidad de copias + archivo adjunto (máximo 3 MB).
  - *Otro*: descripción libre del apoyo requerido.

### 2. Reservas programadas
- Lista completa de todas las reservas, con **filtros por recurso y por fecha**.
- Cada reserva se muestra como una tarjeta tipo "boleto" con toda la información relevante.

### 3. Panel de administración
- Acceso con:
  - **Usuario:** `Admin`
  - **Contraseña:** `Burgos`
- Una vez dentro, el administrador puede:
  - **Editar** cualquier reserva (organización, recurso, fecha, horario, persona, propósito), con la misma validación de choques de horario.
  - **Eliminar** cualquier reserva (con confirmación previa).

---

## Dónde se guardan los datos

Las reservas **no se guardan en la caché ni en el almacenamiento local del navegador** (no usa `localStorage` ni datos temporales del dispositivo). En su lugar, se guardan en el **almacenamiento persistente y compartido del artefacto** (una especie de "repositorio" asociado a esta app), lo cual significa que:

- Todas las personas que abran esta misma app (mismo enlace/artefacto) ven **las mismas reservas**, sin importar el navegador o dispositivo que usen.
- Los datos **persisten entre sesiones**: no se pierden al cerrar la pestaña, recargar la página o cambiar de dispositivo.
- No se necesita servidor propio ni configuración adicional.

### Limpieza automática cada 2 semanas

Para no acumular datos indefinidamente, la app aplica una política de retención automática:

- Cualquier reserva cuya **fecha del evento tenga más de 14 días de antigüedad** se elimina automáticamente del repositorio.
- Esta limpieza se ejecuta cada vez que alguien abre la app, y además se vuelve a revisar cada hora mientras la app permanece abierta (por si alguien la deja abierta varios días).
- No requiere intervención del administrador ni de ningún usuario: es completamente automática.
- Si necesitas conservar reservas antiguas para historial (por ejemplo, para un reporte anual), deberás exportarlas o anotarlas antes de que se cumplan las 2 semanas, ya que la app no guarda un respaldo aparte.
- Si el archivo HTML se abre de forma completamente independiente (por ejemplo, descargado y abierto fuera de Claude), el almacenamiento compartido puede no estar disponible; para que todas las organizaciones vean los mismos datos, lo recomendable es seguir usando el enlace del artefacto dentro de Claude.

---

## Notas importantes de seguridad

- El acceso de administrador (`Admin` / `Burgos`) es una validación simple dentro del propio navegador, pensada para uso interno del barrio. **No es un sistema de seguridad robusto**: cualquier persona que conozca esas credenciales puede entrar a editar o eliminar reservas. Se recomienda compartir la contraseña solo con quienes deban administrar el sistema (por ejemplo, Obispado o el especialista de recursos).
- Los archivos adjuntos para impresión se guardan junto con la reserva. Si un archivo pesa más de 3 MB, la app pedirá adjuntar uno más liviano.
- No hay registro de "quién hizo qué" más allá del nombre que cada persona escribe al reservar, así que se sugiere pedir que siempre se indique el nombre real de quien reserva.

---

## Personalización futura (ideas)

Si en algún momento se quiere ampliar la app, algunas opciones sencillas de agregar más adelante:

- Permitir más de una unidad por recurso (por ejemplo, dos laptops).
- Añadir recordatorios o notificaciones antes de la reserva.
- Cambiar la contraseña de administrador.
- Exportar el listado de reservas a un archivo Excel o PDF.

---

*Última actualización: julio de 2026.*
