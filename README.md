# Control de finanzas

Tablero personal de gastos, ingresos, tarjetas de crédito y plan de pagos.

- **Datos:** Supabase (proyecto `finanzas-eduardo`). Tablas `hojas` (copia de las pestañas de la hoja de Google Sheets) y `movimientos`.
- **Actualización:** una tarea programada de Claude lee cada mañana los correos de BCP, Yape e Izipay, actualiza la hoja de Google Sheets y escribe la copia en Supabase.
- **Acceso:** código de 6 dígitos. La página llama a la función `finanzas_con_codigo` de Supabase, que compara el código con su versión cifrada (bcrypt) y solo entonces devuelve los datos. Tras 8 intentos fallidos se bloquea 15 minutos. Las tablas siguen cerradas al público (RLS).
- **Sitio:** página estática (`index.html`) publicada en Vercel. No necesita compilación ni variables de entorno: la clave publicable de Supabase es pública por diseño y los datos los protege RLS.
