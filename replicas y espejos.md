### QUE ES UN ESPEJO/MIRRORING ###

Base de Datos Espejo (Database Mirroring) es una configuración donde dos o más gestores o servicios de dase de datos independientes, se ejecutan al mismo tiempo y cooperan para mantener copias de la base de datos y archivo de registro de transacciones o auditoría (log) iguales.

El Mirroring (Base de Datos Espejo) proporciona una solución de alta disponibilidad de bases de datos, aumenta la seguridad y la disponibilidad, mediante la duplicidad de la base de datos.

Técnicamente un espejo es una copia idéntica de la base de datos original, para ser accedida en caso de una falla.

# Tipos de mirroring:

    - Alta disponibilidad: Garantiza la consistencia transaccional entre el servidor principal y el servidor de espejo y ofrece Automatic Failover mediante un servidor testigo.
    - Alta Protección: Garantiza la consistencia transaccional entre el servidor principal y el espejo.
    - Alto Rendimiento: Aplica las transacciones en el Servidor Espejo de manera asíncrona ocasionando mejoras significativas en el rendimiento del servidor principal pero no garantiza que dichas transacciones se hallan realizado de manera exitosa en el espejo.

# Beneficios

    - Incrementa la disponibilidad de una base de datos.
    - Si se produce un desastre en el modo de alta seguridad con conmutación automática por error, la conmutación por error pone en línea rápidamente la copia en espera de la base de datos, sin pérdida de datos. En los demás modos operativos, el administrador de bases de datos tiene la alternativa del servicio forzado (con una posible pérdida de datos) para la copia en espera de la base de datos.
    - Aumenta la protección de los datos.
    - La creación de un espejo de la base de datos proporciona una redundancia completa o casi completa de los datos, en función de si el modo de funcionamiento es el de alta seguridad o el de alto rendimiento.


### QUE ES UN REPLICA/REPLICATION ###

La replicación de un gestor de base de datos es una tecnología que nos permite copiar, distribuir datos de una base de datos a otra y luego poder sincronizar o seleccionar informaciòn entre bases de datos para mantener la consistencia e integridad de los datos.

La creación de una replica de la base de datos incluye la creación de un gestor adicional o más  de una base de datos principal que suelen residir en diferentes equipos o servicios. 
 
En cada momento, solo una copia de la base de datos está disponible para los clientes. Esta copia se conoce como la base de datos principal o master. Las actualizaciones realizadas  en la base de datos master se aplican a la otra copia de la base de datos, conocida como la base de datos reflejada o replica. 
 
La replica incluye  todas las inserciones, actualizaciones o eliminaciones efectuadas en la base de datos master.

# Tipos de replicación:

	- Replicación básica: las réplicas de tablas se gestionan para accesos de sólo lectura. Para modificaciones, se deberá acceder a los datos del sitio primario.

	- Replicación avanzada (simétrica): amplían las capacidades básicas de sólo- lectura de la replicación, permitiendo que las aplicaciones hagan actualizaciones a las réplicas de las tablas, a través de un sistema replicado de la base de datos. Con la replicación avanzada, los datos pueden proveer lectura y acceso a actualizaciones a los datos de las tablas.

# Beneficios

	- La replicación puede mejorar el funcionamiento y proteger la disponibilidad de las aplicaciones, porque alterna opciones de acceso de los datos existentes.

	- La creación de una replica de la base de datos se usa para mejorar la disponibilidad de la información.

	- Aumento de la fiabilidad: Mediante la replicación de base de datos a través de múltiples servidores, te aseguras que los datos van a estar disponibles incluso en el caso de que una de las máquinas tenga un fallo grave de hardware.

	- Mejora en el rendimiento: Al estar los datos distribuidos en diferentes servidores, los múltiples accesos no saturan los servidores

	- Mejora en la seguridad de los datos: en un sistema transaccional tradicional, todas las actualizaciones de una base de datos se guardan en un mismo disco. La seguridad de tus datos queda entonces en manos de la estrategia de copias de seguridad que tengas implementada en ese servidor. Con la replicación de base de datos aumentas la seguridad de los datos ya que las actualizaciones están siendo escritas en varios servidores, es decir, varios discos.

### RESUMEN Y EL USO EN LA PRÁCTICA ###

Mirroring: La creación de del espejo se refiere a mantener un servidor de base de datos de respaldo para un servidor de base de datos maestro. Si por alguna razón, la base de datos maestra está inactiva, entonces la base de datos espejo se puede utilizar como alternativa para la base de datos maestra. En principio, solo un servidor de base de datos está activo a la vez.

Replication: La replicación se refiere a mantener múltiples copias de bases de datos distribuidas en múltiples ubicaciones geográficas. El ejemplo clásico de replicación son los servidores de archivos que se replican en todos los continentes para que el usuario pueda descargar la información desde la ubicación más cercana para evitar retrasos en la red y cualquier respuesta lenta.