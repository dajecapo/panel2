# Sección: Consultas a Sabios (Panel de Administración)

Esta sección del Panel de Administración permite visualizar y gestionar las preguntas enviadas por los usuarios a través del formulario de la Galería de Sabios. Está conectada en tiempo real con la pestaña `CONSULTAS` de la hoja de cálculo de Google Sheets.

## ✅ Funcionalidades principales

- Visualización ordenada de las consultas recibidas.
- Botones de **Aprobar** o **Eliminar** cada consulta.
- Lectura en tiempo real desde Google Sheets (pestaña `CONSULTAS`).
- Sincronización automática al cargar el panel.
- Interfaz clara y responsiva.

## 📄 Estructura esperada en Google Sheets

La pestaña `CONSULTAS` debe tener las siguientes columnas, **en este orden exacto** (todo en minúsculas y sin tildes):


> ⚠️ **Importante:** el orden y el nombre exacto de las columnas son clave para que el sistema funcione correctamente.

## 🧠 Lógica de conexión

Esta sección se alimenta desde un Web App publicado con Google Apps Script, que responde al parámetro `tipo=consultas` para diferenciar esta lectura de la de otras secciones (como `SUMATE` o `TESTIMONIOS`).

Ejemplo de llamada directa:


## ⚙️ Script de Apps Script relevante

El `doGet(e)` detecta el parámetro `tipo` y dirige la lectura a la hoja correspondiente (`CONSULTAS`, en este caso). El `doPost(e)` permite actualizar el estatus de una fila o eliminarla.

## 🧪 Verificación

- [x] Se probó correctamente el despliegue (`Deploy`) del Apps Script.
- [x] Se actualizó la versión activa para reflejar los cambios.
- [x] Se verificó que los datos mostrados pertenecen exclusivamente a la pestaña `CONSULTAS`.
- [x] Función `Aprobar` actualiza el campo `estatus`.
- [x] Función `Eliminar` borra la fila correspondiente.

## 🧼 Recomendaciones

- No alterar el orden ni el nombre de las columnas en la pestaña `CONSULTAS`.
- Siempre hacer **Deploy → Manage deployments → Deploy versión nueva** al modificar el Apps Script.
- Confirmar el despliegue visitando la URL con `?tipo=consultas`.

---

Este archivo forma parte del sistema completo **Adopta un Sabio**, orientado a la revalorización del conocimiento de los adultos mayores mediante contacto directo con jóvenes.
