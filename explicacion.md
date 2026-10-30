# Inicio de sesión — sin servidor

La página pide iniciar sesión (o crear una cuenta) antes de entrar al tocadiscos.

**No hace falta instalar nada ni correr ningún servidor.** Abrís
"redonditos-tocadiscos.html" con doble clic y listo.

## Cómo funciona

Las cuentas se guardan en el **localStorage del navegador**, que hace de base
de datos. Las contraseñas nunca se guardan en texto plano: se guarda un hash
con *salt* aleatorio por usuario.




# Patricio Rey y sus Redonditos de Ricota — Tocadiscos 3D

Una página web de un solo archivo que recrea un **tocadiscos en 3D** para
escuchar la discografía de estudio de Patricio Rey y sus Redonditos de Ricota,
más una **wiki** con la ficha de cada disco. Toda la estética (negro profundo,
rojo bandera, verde ácido del logo, púrpura y oro de *Luzbelito*, textura de
grabado y grano de film) está tomada del universo visual de la banda.

## Qué hace la página

La página tiene tres vistas: el **tocadiscos**, la **wiki** y la **ficha de
cada álbum**. Para entrar hay que iniciar sesión (ver más abajo).

### 1. Tocadiscos 3D

Es la pantalla principal. Una escena 3D (hecha con Three.js) muestra una mesa
con un tocadiscos, una estantería con las tapas de los discos y un sobre donde
descansa el vinilo.

Cómo se usa:

1. **Tocá una tapa** de la estantería para elegir el disco.
2. **Arrastrá el vinilo** desde el sobre hasta el plato.
3. Al soltarlo sobre el plato, **el brazo baja solo** y arranca la música.
4. Para cambiar de disco, sacá el vinilo del plato (botón de expulsar, o la
   tecla `E`) y elegí otro.

También podés **rotar la cámara** arrastrando fuera del vinilo, **acercar o
alejar** con la rueda del mouse o con pellizco en el celular, y volver a la
vista inicial con el botón *Centrar cámara*.

### 2. Reproductor

Abajo a la izquierda hay un reproductor con:

- Tapa, nombre del disco y del tema que suena.
- Barra de progreso clickeable y tiempos.
- Play/pausa, tema anterior, tema siguiente, expulsar vinilo y volumen.
- **Lista de temas** desplegable para saltar a cualquier canción del disco.



**De dónde sale el audio.** La página no trae música incluida. Cada tema se
reproduce con este orden de prioridad:

1. Un **MP3 propio**, si completás el campo `audioUrl` de ese tema.
2. Un **preview de 30 segundos** buscado automáticamente en la API pública de
   iTunes (sin cuenta ni clave). Al terminar, pasa al tema siguiente.
3. Si no se encuentra nada, una **reproducción simulada** con barra de
   progreso, para que la interfaz siga funcionando igual.


### 3. Wiki y fichas de álbum

La pestaña **Wiki** muestra la discografía de estudio: **nueve discos entre
1985 y 2000**, cada uno como una tarjeta con su tapa, año, cantidad de temas
(y si es álbum doble).




### 4. Inicio de sesión

Antes de entrar, la página pide **iniciar sesión o crear una cuenta**. Es un
login local: no hay servidor, las cuentas viven en el navegador y las
contraseñas se guardan hasheadas.


