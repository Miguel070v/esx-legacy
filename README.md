<h1 align='center'>ESX Legacy</a></h1><p align='center'><b><a href='https://discord.gg/cNx6HF9P5J'>Development Discord</a> - <a href='https://esx-framework.org/esx'>Website</a> - <a href='https://discord.gg/J6VqFPwvVp'>Support Discord</a></b></h5>


##### ESX es el marco más popular para crear servidores de juegos de rol basados ​​en la economía en FiveM, con muchos recursos oficiales y comunitarios diseñados para utilizar las herramientas que se proporcionan aquí. Para una muestra de lo que está disponible:
> esx_identity: permite el registro de personajes definiendo el nombre, el sexo, la altura y la fecha de nacimiento de un jugador

> esx_society: permite que los recursos laborales registren una sociedad, obtengan gestión de empleados, fondos de la sociedad y más

> esx_billing: permite a los miembros de algunas sociedades enviar multas o facturas a otros jugadores

> esx_vehicleshop: permite a los jugadores comprar vehículos en un concesionario o configurar el apoyo de la sociedad para un concesionario administrado por jugadores

> esx_ambulancejop: agrega un sistema de muerte y reaparición al tiempo que permite a los jugadores trabajar como EMS para curar y revivir a otros

Se incluyen muchos más recursos en este repositorio, o puede navegar por [ESX Community Github] (https://github.com/esx-community/) o [Cfx.re Releases board] (https: //forum.cfx. re / tag / esx) para obtener más información.

### Información
##### Legacy proporciona algunas correcciones de errores y mejoras necesarias para optimizar el marco antes de llegar al final del soporte oficial por parte del equipo de desarrollo.
##### La mayoría de los recursos diseñados para 1.2 no tendrán problemas con Legacy, las excepciones notables son aquellas que modifican el comportamiento de generación / carga. Hay varias actualizaciones de funciones menores que no afectan la compatibilidad con recursos antiguos.
##### NOTA: El sistema de equipamiento en ESX siempre ha sido problemático, y arreglarlo requeriría una revisión completa. Tu mejor opción es usar un recurso que maneje armas como elementos.

#### Optimización
- Utilice el hash jenkins en tiempo de compilación sobre el nativo de GetHashKey
- Actualice las consultas de MySQL antiguas para usar MySQL.store para mejorar el rendimiento, especialmente durante el guardado del reproductor
- Varios bucles ahora se suspenderán cuando sus tareas no sean necesarias para realizar
- Soporte mejorado al usar ESX Identity para reducir eventos y consultas durante el inicio de sesión del jugador
- Soporte para las últimas armas y componentes.

#### Características
- Soporte integrado para datos de identidad
- Comandos integrados de esx_adminplus
- Todos los jugadores se guardarán inmediatamente antes de un reinicio programado de txAdmin
- Detecta si un jugador es nuevo y envía el resultado al evento playerLoaded
- Soporte para jugadores que cierran la sesión cuando usan recursos de varios personajes
- Almacene en caché el ID de ped de los jugadores y el estado de muerte en ESX.PlayerData
- Se agregó un archivo de importaciones (similar a locales.lua) para configurar eventos y funciones en otros recursos
- Antes de definir todos los archivos de script de manifiesto, agregue `shared_script '@ es_extended / imports.lua'`
- Recupere automáticamente el objeto ESX, eliminando la necesidad de enviar un evento de devolución de llamada tanto en el cliente como en el servidor
- Asegura que la información actual siempre se devuelva cuando se usa `ESX.PlayerData` (excepto la carga y el inventario)
- Spawnmanager se está utilizando para manejar correctamente los engendros de jugadores
- Posibles conflictos con algunos recursos de terceros que no esperan spawnmanager
- Se agregó una función mejorada al realizar bucles de xPlayer para evitar grandes problemas de servidor
- Usando `ESX.GetExtendedPlayers ()` en lugar de `ESX.GetPlayers ()`
- También puede usar argumentos con la nueva función, como
- ESX.GetExtendedPlayers ('trabajo', 'policía')
- ESX.GetExtendedPlayers ('grupo', 'admin')

#### Correcciones
- La tabla ESX.Jobs se completa después de que se configuran todos los trabajos, lo que permite que otros recursos la recuperen si es necesario
- Todas las armas se eliminan correctamente cuando se usa el comando clearloadout
##### Para crear o actualizar recursos, consulte el [texto estándar actualizado] (/ esx_example).

### 1.2 Características
- Sistema de inventario basado en peso
- Soporte de armas, incluido el soporte para accesorios y tintes.
- Admite diferentes cuentas de dinero (incumplidas con efectivo, banco y dinero negro)
- Muchos recursos oficiales disponibles en nuestro GitHub
- Sistema de trabajos, con notas y soporte de ropa.
- Admite varios idiomas, la mayoría de las cadenas están localizadas
- API fácil de usar para que los desarrolladores integren fácilmente ESX en sus proyectos
- Registre sus propios comandos fácilmente, con validación de argumentos, sugerencia de chat y usando FXServer ACL

### Requisitos
- Todos los recursos de la carpeta `core`
- [spawnmanager] (https://github.com/citizenfx/cfx-server-data)
- [mysql-async] (https://github.com/brouznouf/fivem-mysql-async/releases/tag/3.3.2)


### Instalación
- Descargue archivos a la carpeta de recursos y, si lo desea, prepare directorios para la organización (es decir, recursos / [core] / es_extended)
- Importar `es_extended.sql` en su base de datos
- Importe cualquier otro archivo sql para los recursos que está utilizando
- Asegúrese de que todos los archivos de configuración de recursos se hayan ajustado a sus preferencias
- Utilice o consulte el archivo server.cfg incluido para conocer el orden de inicio y la configuración

### Conflictos
* Los siguientes recursos no deben usarse con ESX Legacy
- essentialmode
- basic-gamemode
- modo de juego básico
- mapa-patinador de cinco metros
- mapa-hipster de cinco metros
- default_spawnpoint

### Información
ESX fue desarrollado inicialmente por Gizz en 2017 para su amigo, ya que estaban creando un servidor FiveM y no había ningún marco de juego de roles económico disponible. El código original se escribió dentro de una semana o dos y luego fue de código abierto, desde entonces se ha mejorado y se han reescrito partes para mejorarlo aún más.
- [Foro de ESX] (https://forum.esx-framework.org/)
- [Documentación de ESX] (https://wiki.esx-framework.org/)
- [ESX Development Discord] (https://discord.me/esx)
- [Referencia nativa de FiveM] (https://runtime.fivem.net/doc/reference.html)


### Legal

Licencia ###

es_extended - marco ESX para FiveM

Copyright (C) 2015-2021 Jérémie N'gadi

Este programa es software libre: puede redistribuirlo y / o modificarlo según los términos de la licencia pública general GNU publicada por la Free Software Foundation, ya sea la versión 3 de la licencia, o (a su elección) cualquier versión posterior.

Este programa se distribuye con la esperanza de que sea útil, pero SIN NINGUNA GARANTÍA; incluso sin la garantía implícita de COMERCIABILIDAD O APTITUD PARA UN PROPÓSITO PARTICULAR. Consulte la Licencia pública general GNU para obtener más detalles.

Debería haber recibido una copia de la Licencia Pública General GNU junto con este programa. De lo contrario, consulte http://www.gnu.org/licenses/.
