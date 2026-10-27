# Control de finanzas

Tablero personal de gastos, ingresos, tarjetas de crédito y plan de pagos.

- **Datos:** Supabase (proyecto `finanzas-eduardo`). Tablas `hojas` (copia de las pestañas de la hoja de Google Sheets) y `movimientos`.
- **Actualización:** una tarea programada de Claude lee cada mañana los correos de BCP, Yape e Izipay, actualiza la hoja de Google Sheets y escribe la copia en Supabase.
- **Acceso:** inicio de sesión con enlace al correo. Las políticas de seguridad (RLS) solo dejan leer los datos a la cuenta del dueño.
- **Sitio:** página estática (`index.html`) publicada en Vercel. No necesita compilación ni variables de entorno: la clave publicable de Supabase es pública por diseño y los datos los protege RLS.
