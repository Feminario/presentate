# Preséntate · Club 365 · Feminario

Formulario de bienvenida de la comunidad del Club 365 (colores y tipografía de Feminario), calendario de eventos suscribible y correo de bienvenida para Kajabi.

```
index.html                    El formulario (3 pasos, foto, pantalla final con presentación + grupo + calendario)
assets/                       Logos y fotos (ya comprimidos). Opcional: fondo.jpg (si existe, se usa como fondo)
calendario/club-365-2027.ics  Eventos del Club: las clientas se suscriben y se actualiza solo
correo/bienvenida-kajabi.html Correo automático de bienvenida (HTML para Kajabi)
supabase/perfiles.sql         Tabla, seguridad y bucket de fotos (ya aplicado en Supabase)
```

## Cómo se actualizan los eventos
Edita `calendario/club-365-2027.ics`, agrega o cambia un bloque `BEGIN:VEVENT … END:VEVENT`, súbelo (commit + push) y las clientas lo ven en su calendario en unas horas, sin hacer nada.

## Dónde ver los perfiles
Supabase → Table Editor → `perfiles_club`. La vista `tarjetas_bienvenida` trae el texto de presentación listo para pegar en el grupo (sin edad, ingresos ni datos financieros). Las fotos están en Storage → `fotos-bienvenida` (privado).

## Seguridad
La llave de `index.html` es **pública por diseño**: solo permite *enviar* un perfil (y solo si aceptó los permisos). Desde la web nadie puede leer, editar ni borrar perfiles ni fotos.
