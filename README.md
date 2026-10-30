# 🕒 Lucks Clock

Reloj para Android en pantalla completa y horizontal, con segundos, personalizable y con un mini reproductor de Spotify integrado.

## ✨ Características

**Reloj**
- Pantalla completa en horizontal, con segundos y fecha.
- Formato **24 h** o **12 h** (AM/PM).
- **9 fuentes** a elegir: Fina, Ligera, Clásica, Condensada, Gruesa, Serif, Mono, Manuscrita y Casual.
- Color de **fondo** y de **texto** a elección: paleta lista o color propio en HEX.
- Barra fina arriba que avanza con los segundos.
- La pantalla no se apaga mientras la app está abierta.
- Los ajustes se guardan solos.

**Reproductor de Spotify**
- Si hay una canción de Spotify, aparece un **icono redondo de música** abajo.
- Al tocarlo, el reloj se achica y sale una tarjeta de bordes redondeados con el **color de la portada** del álbum.
- La tarjeta muestra: portada a la izquierda, nombre, artista, **barra para elegir el segundo** de la canción, shuffle, anterior, pausa/play, siguiente y bucle.
- Animaciones al abrir, cerrar y al cambiar de canción.

## 📲 Cómo obtener el APK

El APK se compila solo en GitHub, no necesitas Android Studio.

1. Sube `lucks-clock.zip` a este repositorio (sin descomprimir).
2. Debe existir el archivo `.github/workflows/build.yml`.
3. Cada vez que haces un commit, la pestaña **Actions** compila la app (tarda unos 3 a 5 minutos).
4. Cuando salga el check verde, entra a **Releases** y descarga `lucks-clock.apk` de la versión más nueva.

## 🔧 Instalación

1. Abre el APK en el celular y permite instalar apps de orígenes desconocidos si te lo pide.
2. Si **Play Protect** lo bloquea: toca **Más detalles → Instalar de todos modos**. Esto pasa porque la app no viene de Play Store.
3. Si ya tenías una versión instalada, **desinstálala antes**: cada compilación se firma con una clave distinta y Android no deja actualizar encima. Se borran tus ajustes.

## 🎵 Conectar Spotify

La app lee lo que suena en Spotify a través de las notificaciones del sistema.

1. Al abrir la app por primera vez, toca **Abrir ajustes** y activa **Lucks Clock** en *Acceso a notificaciones*.
2. Si aparece bloqueado: Ajustes → Apps → Lucks Clock → ⋮ → **Permitir ajustes restringidos**, y vuelve a intentar.
3. Pon una canción en Spotify. Aparece el icono de música abajo.

## 🎛️ Uso

| Acción | Cómo |
| --- | --- |
| Abrir ajustes | Toca la pantalla y luego el botón de ajustes (arriba a la derecha) |
| Cambiar formato, fuente o colores | Panel de ajustes |
| Abrir el reproductor | Toca el icono redondo de música |
| Cerrar el reproductor | Flecha hacia abajo de la tarjeta, o el botón Atrás |
| Elegir el segundo de la canción | Arrastra la barra de la tarjeta |

## ⚠️ Limitaciones conocidas

- Requiere **Android 8.0 o superior**.
- **Shuffle y bucle** dependen de lo que Spotify permita controlar desde otra app. Pausa, anterior, siguiente y la barra de tiempo usan los controles estándar, pero el estado de shuffle y bucle que muestra la app es local y puede no coincidir con el de Spotify.
- La app compila como APK de depuración, firmado con la clave de prueba de GitHub.
- El código no se probó en un dispositivo real antes de publicarlo. Si algo falla, abre un *Issue* con el detalle.

## 🧱 Estructura

```
app/src/main/
├── java/com/lucks/clock/
│   ├── MainActivity.kt     # reloj, ajustes, tarjeta del reproductor y animaciones
│   ├── SpotifyBridge.kt    # lectura y control de la sesión de Spotify
│   ├── MediaListener.kt    # servicio que da acceso a las sesiones de medios
│   └── ColorUtil.kt        # color dominante de la portada y utilidades
├── res/                    # iconos y tema
└── AndroidManifest.xml
```

## 🛠️ Tecnologías

- Kotlin y vistas nativas de Android (sin librerías externas)
- Gradle 8.9 y Android Gradle Plugin 8.5
- GitHub Actions para compilar y publicar el APK

---

Hecho con ❤️ por Lukita.
