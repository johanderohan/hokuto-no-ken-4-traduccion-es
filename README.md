# Hokuto no Ken 4: Shichisei Haken Den — Traducción al castellano

[![Invítame a un café en Ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/johanderohan)

Ficha del proyecto, capturas y más traducciones al castellano en **[Parches en Castellano](https://parchesencastellano.com/traducciones/nes/hokuto-no-ken-4)**.

Traducción al **español de España** de *Hokuto no Ken 4: Shichisei Haken Den —
Hokuto Shinken no Kanata e* (北斗の拳4 七星覇拳伝 北斗神拳の彼方へ, Famicom,
Toei Animation / Shouei System, 1991), el RPG del *Puño de la Estrella del
Norte*, hecha desde la ROM japonesa original. El juego nunca salió de Japón.

Año 20XX. Kenshiro ha desaparecido y el mundo vuelve a las tinieblas. Un joven
del Linaje de Hokuto descubre la marca de las siete estrellas en su brazo y
parte a buscarlo, enfrentándose a las Seis Estrellas del Ura Nanto, al Gento
Ryuken y a Haken-oh.

La traducción se reparte como **parche**: no incluye el juego. Necesitas tu
propia copia para aplicarlo.

## Estado

Última versión: **[v1.0 — Guion, menús e interfaz en castellano](../../releases/tag/v1.0)**.

| Parte | Estado |
|---|---|
| Guion | Los 1.228 mensajes del juego traducidos del japonés (diálogos, narraciones, pistas, combate, tiendas y mensajes del sistema), con biblia de términos y revisión independiente de todos los lotes |
| Nombres | Personajes, pueblos, objetos y equipo, técnicas, gritos y grupos de enemigos |
| Interfaz | Título y diarios, pantalla de nombre con letras latinas, menús de campo, objetos, estado, equipo, tiendas, posada, centro de entrenamiento, viaje y todo el combate |
| Fuente | Nueva fuente española con minúsculas, **á é í ó ú ü ñ Á É Í Ó Ú Ñ ¡ ¿**, en el estilo de las cifras originales y con el mismo color y contraste |
| Rótulos gráficos | Se conserva el logotipo 北斗の拳4, que es la imagen de marca del juego |

Los nombres siguen la edición española del manga (Planeta Cómic) cuando la
hay: Kenshiro, Raoh, Toki, Yulia, Bat, Lin, el Hokuto Shinken, los arcanos y
los puntos de presión. Los gritos míticos (¡Abeshi!, ¡Hidebu!, ¡Tawaba!) se
conservan.

El castellano ocupa mucho más que el japonés (que va solo en kana), así que el
parche amplía la ROM de 256 a **512 KB** (placa MMC1 SUROM, la de *Dragon
Warrior III/IV*) y rehace muchas ventanas para que quepan los textos: menús
más anchos, listas de técnicas y objetos en una columna en combate y la
ventana del hablante en dos líneas (nombre arriba, grito o daño debajo). Por
espacio, Kazemaru y Kuroyasha aparecen como **Kaze** y **Yasha** en las
ventanas del grupo y del combate; en el diálogo van completos.

### Comprobaciones y trabajo pendiente

- Cada mensaje se vuelve a leer desde la ROM construida y coincide con el guion.
- 1.225 de los 1.227 mensajes de texto se han mostrado uno a uno en el
  emulador (fceumm mediante libretro) y se ha leído su texto en pantalla:
  todas sus líneas aparecen completas (los otros dos son prefijos de combate
  con un gráfico).
- Dos rondas de pruebas jugando desde partida nueva: título y diarios, nombre,
  prólogo, Maredo y Monpasa, todas las órdenes del menú, tiendas (comprar,
  vender, bolsa llena), posada, guardar y cargar, Soseiko, muerte y vuelta al
  centro, y más de 280 combates con uno y dos personajes, técnicas, objetos,
  subida de nivel y avisos de OP. Para llegar antes a algunas pantallas
  (segundo personaje, listas largas de técnicas) se modificó la RAM en las
  pruebas.
- El parche aplicado a la ROM japonesa reproduce byte a byte la ROM probada.

**Falta una partida completa de principio a fin**, la prueba en consola física
y una revisión humana independiente: la traducción y las revisiones se han
hecho con ayuda de IA. Detalles conocidos:

- En combate, la lista de técnicas cambia de página eligiendo la marca ▷▷▷▷
  (←/→ no pasan de página) y en alguna página queda un hueco entre técnicas.
- Al cerrar algunas ventanas de tienda asoman trozos de la lista de debajo,
  como en el original, aunque ahora se nota más.
- Los estados alterados se muestran abreviados en el estado de combate
  (KO, Tox, Par, Zzz).

## Cómo aplicar el parche

1. Descarga el parche `.xdelta` de la sección **[Releases](../../releases)**.
2. Consigue tu copia del juego en versión **japonesa**. El parche solo funciona
   con esa versión exacta.
3. **Comprueba que tu copia es la correcta** antes de nada:

   | | |
   |---|---|
   | Archivo | `Hokuto no Ken 4 - Shichisei Haken Den - Hokuto Shinken no Kanata e (Japan).nes` |
   | Tamaño | 262.160 bytes (con cabecera NES 2.0) |
   | CRC32 | `2CDE09BE` (sin cabecera: `63469396`) |
   | MD5 | `d72fc0676ae28fbdde98fbbbaf1e1ab2` |
   | SHA-256 | `6237aafed56a8f137a79deaf2c0e0caf9094bd82c61165c6fda0a4ab6b161a7d` |

   ```bash
   md5sum "Hokuto no Ken 4 - Shichisei Haken Den - Hokuto Shinken no Kanata e (Japan).nes"     # Linux
   md5 "Hokuto no Ken 4 - Shichisei Haken Den - Hokuto Shinken no Kanata e (Japan).nes"        # macOS
   CertUtil -hashfile "Hokuto no Ken 4 - Shichisei Haken Den - Hokuto Shinken no Kanata e (Japan).nes" MD5   # Windows
   ```

   Si no coincide, el parche fallará o dará un resultado corrupto.
4. Aplica el parche con una de estas herramientas:
   - **Windows**: [Delta Patcher](https://github.com/marco-calautti/DeltaPatcher/releases)
   - **Linux / macOS**: `xdelta3 -d -s "juego original.nes" parche.xdelta "juego traducido.nes"`
5. Comprueba que la ROM resultante tiene **524.304 bytes** y MD5
   **`f3f5d075622aeaa44ea5546aa227ce0d`** (SHA-256 `01a0c73ba5b7759fcc0bd33959e4f355ecd43f26cfde8185b864e0f80b45a8e7`).
6. Carga la ROM resultante en tu emulador o flashcard (con soporte de mapper 1
   de 512 KB) y empieza una partida nueva.

Aplica cada versión sobre la **ROM japonesa original**, no sobre una ROM ya
traducida.

## Cambios

- **v1.0** (6 de octubre de 2026): primera publicación. Guion, nombres, menús e
  interfaz en castellano de España; fuente española nueva; ROM ampliada a 512 KB.

## Errores

Para comunicar un error, abre una incidencia con la versión del parche, el
emulador, el lugar del juego y la frase o pantalla afectada. No adjuntes la ROM.

## Aviso

Este proyecto es una traducción hecha por afición, sin ánimo de lucro y sin
relación alguna con Toei Animation, Shouei System, Buronson, Tetsuo Hara ni
los titulares de *Hokuto no Ken*. Aquí no se distribuye el juego ni ninguna
parte de él: solo un parche que modifica una copia que ya tengas. Este
repositorio contiene únicamente el README; el parche está en Releases.

Si eres el titular de los derechos y quieres que retire esto, abre una
incidencia y lo hago.
