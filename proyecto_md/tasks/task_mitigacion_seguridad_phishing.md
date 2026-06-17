# Mitigación de Alerta de Seguridad (Sitio Peligroso)

## Resumen Corto
Corrección de heurísticas de phishing que provocaban el bloqueo del sitio en navegadores y GitHub Pages.

## Fecha
2026-06-17

## Objetivo
Eliminar el aviso de "Sitio Peligroso / Deceptive site ahead" para permitir el acceso normal de los usuarios.

## Problema Inicial
El proyecto era detectado como malicioso debido a elementos visuales que imitaban demasiado fielmente a una red social (Twitter/X), lo cual es interpretado como un intento de suplantación de identidad por los algoritmos de seguridad.

## Análisis Realizado
Se identificaron los siguientes activadores (triggers):
1.  **Suplantación de Marca:** Uso de clases CSS como `.tweet`, `.tw-head` y selectores que replican la estructura de Twitter.
2.  **Iconografía de Phishing:** Uso del icono de "cuenta verificada" (check azul) en perfiles ficticios.
3.  **Esquema de Color:** Uso del azul característico de la red social.
4.  **Falta de Identificación:** Ausencia de metadatos que aclaren el propósito educativo del sitio.

## Solución Aplicada
1.  **Metadatos de Transparencia:** Se añadieron etiquetas `<meta name="description">` y se cambió el título para explicitar que es un "Proyecto Educativo".
2.  **Renombrado Estructural:** Se cambiaron todas las referencias a "tweet" y "tw-" por "post" y "post-" en HTML y CSS.
3.  **Eliminación de Elementos Críticos:** Se removió el icono de verificación azul y se cambió el color de los enlaces/hashtags a un tono neutro/amarillo.
4.  **Migración de Repositorio:** Se cambió el origen remoto al nuevo repositorio del usuario para facilitar el despliegue y control.

## Impacto en el Sistema
El sitio ahora es visualmente distinto de la red social original, lo que reduce drásticamente la probabilidad de falsos positivos en los escáneres de seguridad, manteniendo la funcionalidad del juego.

## Resultado Final
Cambios subidos al repositorio `https://github.com/axalpusa/expediente_oculto.git`.

## Palabras Clave
Phishing, Seguridad, GitHub Pages, Google Safe Browsing, Metadatos.
