# Panel BX3

Panel del equipo de BX3: tareas, calendario del mes, rodajes y clientes en una sola página pensada para celular. Es una vista sobre Notion, no una base aparte: lee de Notion y solo cambia el campo `Estado`.

Todo el panel es un único archivo, `panel_bx3.html`. No tiene dependencias ni paso de compilación.

## Cómo funciona

- Está publicado como artifact privado de claude.ai (el «Panel BX3» de la cuenta de la agencia). No es un sitio web normal: usa el conector de Notion de quien lo abre, a través del artifact. Abierto como archivo suelto en el navegador carga la interfaz pero no trae datos.
- Lee tres vistas guardadas de Notion (constante `VIEWS` del archivo):
  - Clientes activos: `view://3efda35e-4c95-8165-ba03-000c01ea998d`
  - Equipo · Tareas abiertas: `view://3f5da35e-4c95-810d-a6eb-000c281ccbf0`
  - Producción (todas las piezas): `view://3efda35e-4c95-8108-a789-000ce94fe0b9`
- Consulta siempre en modo vista. En el plan gratuito de Notion, las consultas por filas gastan un cupo compartido que se agota; las de vista no.
- Si alguien cambia los filtros de esas vistas en Notion, cambia lo que muestra el panel.
- Oculta todo lo anterior al 2026-10-09 (`START_DATE`) y las filas sin nombre. Es un filtro del panel; en Notion no se borra nada.
- Pestañas: Semana, Mes, Rodajes y Clientes. Para que un mes aparezca en la pestaña Mes, sus piezas tienen que estar cargadas en Producción (Calendario de Contenido).

## Para seguir trabajándolo

1. Clonar el repo y abrir la carpeta con Claude Code.
2. Tener conectado en claude.ai el conector de Notion con acceso al espacio «BX3 Growth Agency».
3. Editar `panel_bx3.html` y publicarlo como artifact para probarlo con datos reales.

Publicar desde otra cuenta de Claude crea un artifact nuevo con otro enlace. Para que el equipo conserve el enlace de siempre, Leandro tiene que compartir el artifact original con permiso de edición, o volver a publicar él desde este repo.

## Reglas

- Las decisiones, precios y estrategia viven en el repo interno de BX3; Notion es donde el equipo marca avance. El panel no guarda nada por su cuenta.
- El panel solo escribe el campo `Estado`. Cualquier otra escritura en Notion se decide antes con Leandro.
