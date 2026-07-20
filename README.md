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

Las reservas se guardan en un **almacenamiento compartido** asociado a este artefacto. Esto significa que:

- Todas las personas que abran esta misma app (mismo enlace/artefacto) ven **las mismas reservas**, lo cual permite que las organizaciones se coordinen entre sí sin pisarse los horarios.
- No se necesita servidor propio ni configuración adicional.
- Si se abre el archivo HTML de forma completamente independiente (por ejemplo, descargado y abierto fuera de Claude), el almacenamiento compartido puede no estar disponible; en ese caso, lo recomendable es seguir usando el enlace del artefacto dentro de Claude para que todos accedan a los mismos datos.

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
