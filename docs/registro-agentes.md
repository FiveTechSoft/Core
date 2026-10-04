# Registro de los agentes

Una vez cada 6 horas, GitHub abre Core en un navegador y hace trabajar a ALPHA, BETA y GAMMA.
Lo que hacen queda guardado en el repo, en la rama `registro`. Tú no tienes que hacer nada.

```
  GitHub Actions (cada 6 h)
          |
          v
  Abre la web de Core ---> ALPHA, BETA y GAMMA trabajan
                                   |
                                   v
                    Rama "registro": registro/ultimo.json
                                   |
                                   v
                      Instinct lo lee y te avisa
```

## Qué se guarda

- `registro/ultimo.json`: el informe de la última vez. Veredicto `OK`, `PARCIAL` o `CON_ERRORES`.
- `registro/actividad-AAAA-MM-DD.json`: el mismo informe, uno por día.
- `registro/ultima-captura.png`: captura de la web al terminar.

El informe incluye los eventos del Registro de actividad, cada llamada al modelo (tiempo y error si lo hay) y los errores de la página.

## Qué NO es

Es una sesión de prueba en el servidor de GitHub. No es el registro de tu navegador, que sigue guardado solo en tu PC.
No hay claves ni secretos. Usa el permiso que GitHub da a la Action y escribe solo en la rama `registro`, así no lanza otras pruebas ni vuelve a publicar la web.

## Lanzarlo a mano

En GitHub: Actions > "Registro de agentes" > Run workflow.

## Desactivarlo sin borrar nada

Cuando Olin termine de verificar que los agentes funcionan bien, puede desactivar la Action desde GitHub: Actions > "Registro de agentes" > menú de tres puntos > **Disable workflow**.

Esto detiene las ejecuciones. No borra el workflow, el script, esta guía ni la rama `registro`.

## Volver a usarlo

En la misma pantalla, elige **Enable workflow** y luego **Run workflow** para repetir la prueba a mano. Al habilitarlo vuelve también la ejecución automática cada 6 horas.
