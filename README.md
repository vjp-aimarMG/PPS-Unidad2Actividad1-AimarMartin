# PPS-Unidad2Actividad1-AimarMartin
# Trazado
Podemos observar que se ha detectado una vulnerabilidad de severidad crítica en GoAnywhere MFT de Fortra que podría permitir a un ciberdelincuente crear un usuario administrador a través del portal de administración.

También nos indica la solución la cual recomienda actualizar a la versión 7.4.1 o superior

![](/img/1.png)

Podemos observar que si pulsamos sobre el enlace debajo de la lista de referencias veremos los principales problemas de GoAnywhere MFT y varios datos más.

# Información sobre Vulnerabilidades
Podemos observar algo de información sobre la vulnerabilidad como el **CVE**, la **importancia** de la vulnerabilidad, los **productos afectados**, la **fecha de descubrimiento**, además de una nota de la vulnerabilidad la cual nos explica cómo solucionarla

![](/img/2.png)

# Información sobre el riesgo o criticidad de una vulnerabilidad
Lo primero que nos encontramos, es la información de la criticidad que la vulnerabilidad presenta, así como el vector asociado a dicho nivel en la CVSS. En este caso vemos que tiene una valoración de 9.8, y está marcada como **crítica**.

![](/img/3.png)

Si ponemos el cursor sobre el Vector nos aparecerán los valores correspondientes a las diferentes métricas que se han usado para calcularlo.

![](/img/4.png)

# Información sobre las debilidades explotadas.
Otra información importante a obtener son las debilidades que son explotadas. Podemos obtener también esta información tanto en la información de la NVD como en la de CVE.ORG.

![](/img/5.png)

En esta ocasión podemos ver como son dos las debilidades explotadas por esta vulnerabilidad: CWE-425. Vamos a ver información sobre ella.
* CWE-425

### 1. Descripción:
**Problema:** La aplicación web no aplica correctamente el control de acceso a ciertas URLs, archivos o scripts restringidos. Esto significa que los usuarios pueden acceder a áreas protegidas sin la autorización adecuada.
### 2. Descripción extendida:
**Explicación adicional:** Las aplicaciones web a menudo caen en la trampa de suponer que los recursos solo se pueden acceder a través de rutas específicas (por ejemplo, a través de un formulario de inicio de sesión). Como resultado, solo aplican autorizaciones en ciertos puntos de acceso, lo que puede permitir que los atacantes accedan directamente a recursos restringidos mediante manipulación de la URL (ataques de **forced browsing**).
### 3. Términos alternativos:
**"Forced Browsing":** Este término describe cuando un atacante intenta acceder a una página restringida adivinando o manipulando la URL directamente. Sin embargo, el término puede confundirse con otros tipos de vulnerabilidades, como XSS o CSRF, por lo que se recomienda evitar su uso.
### 4. Consecuencias comunes:
**Impacto técnico:** Dependiendo de la vulnerabilidad, un atacante podría:
* **Leer o modificar datos:** Acceder o alterar información que no debería estar disponible.
* **Ejecutar código no autorizado:** Ejecutar comandos o código malicioso.
* **Obtener privilegios o suplantar identidad:** Escalar permisos o hacerse pasar por otro usuario.
### 5. Mitigaciones potenciales:
* **Fase de Diseño y Arquitectura:** Para evitar este problema, es fundamental implementar un control de acceso adecuado a cada URL, archivo o script restringido.
* **Uso de Frameworks:** Se sugiere usar marcos de trabajo basados en el patrón MVC (Model-View-Controller) como Struts, que facilitan una mejor gestión de los accesos y rutas.
### 6.Relaciones:
**Relaciones con otras debilidades:**
* **CWE-288:** Bypass de autenticación mediante una ruta alternativa.
* **CWE-424:** Protección incorrecta de rutas alternativas.
* **CWE-862:** Falta de autorización.
### 7. Modos de Introducción:
**Fases:** El problema puede surgir tanto en la fase de **implementación** como en la de **operación** de la aplicación.
### 8. Plataformas aplicables:
* **Lenguajes:** Este problema no está ligado a un lenguaje específico.
* **Tecnologías:** Afecta principalmente a aplicaciones **web**.
### 9. Ejemplo demostrativo:
Si un atacante puede hacer "forced browsing", podría intentar acceder a páginas sensibles directamente. Un ejemplo en **JSP** podría ser:
* http://somesite.com/someapplication/admin.jsp
### 10. Ejemplos observados:
* **CVE-2022-29238:** Una herramienta de colaboración no implementaba correctamente el control de acceso, permitiendo solicitudes directas a archivos ocultos.
* **CVE-2005-1654:** Bypass de autorización mediante solicitudes directas, lo que permitía acceder a funcionalidades privilegiadas sin autorización.
### 11. Membresías:
Este CWE (Common Weakness Enumeration) está relacionado con varias categorías en estándares y guías de seguridad como **OWASP** (por ejemplo, A10 - Failure to Restrict URL Access), lo que lo convierte en una debilidad común en el desarrollo web.
### 12. Notas de mapeo de vulnerabilidades:
**Uso aceptable:** Esta entrada se utiliza para mapear vulnerabilidades reales, ya que es un punto de abstracción adecuado para identificar la causa raíz de los problemas de seguridad en aplicaciones web.
### 13. Notas teóricas:
**"Forced Browsing":** En este caso, la manipulación de las URL para omitir pasos en el proceso de navegación puede conducir a un bypass de autenticación, revelando recursos que deberían estar protegidos.
### 14. Taxonomía de mapeos:
* **PLOVER:** El término "Forced Browsing" se utiliza en esta categoría.
* **OWASP:** Se relaciona con varios de los OWASP Top Ten, incluidos problemas de control de acceso y validación de entradas.
### 15. Patrones de ataque relacionados:
Se mencionan patrones de ataque específicos que se asocian con este tipo de vulnerabilidad, como la **indexación de directorios** (CAPEC-127) o la **detección de páginas web no publicadas** (CAPEC-143).

![](/img/6.png)

# Información sobre patrones de ataque
En el caso que nos atañe, hemos llegado a que la vulnerabilidad que estudiamos se puede explotar mediante los siguientes patrones:

[patrón de ataque CAPEC-127](https://capec.mitre.org/data/definitions/127.html)
[patrón de ataque CAPEC-143](https://capec.mitre.org/data/definitions/143.html)
[patrón de ataque CAPEC-144](https://capec.mitre.org/data/definitions/144.html)
[patrón de ataque CAPEC-668](https://capec.mitre.org/data/definitions/668.html)
[patrón de ataque CAPEC-87](https://capec.mitre.org/data/definitions/87.html)

![](/img/7.png)

Aquí también podemos seleccionar la información a mostrar, dependiendo de nuestras necesidades. En caso de que queramos ver toda la información, selecionamos la vista Complete.

Un atacante envía una solicitud a un objetivo para que este liste o indexe el contenido de un directorio. Esto suele ocurrir cuando una solicitud termina en el nombre de un directorio en lugar de un archivo, ya que muchas aplicaciones están configuradas para mostrar la lista de archivos en estos casos. Con esta técnica, el atacante puede explorar la estructura de directorios y descubrir archivos sensibles como pruebas, copias de seguridad, archivos temporales, ocultos, configuraciones, cuentas de usuario y scripts, lo que puede facilitar ataques adicionales.

![](/img/8.png)

Este proceso describe cómo los atacantes descubren y explotan directorios en servidores web. Primero, exploran enviando solicitudes para identificar directorios existentes, incluso si no son accesibles. Luego, experimentan intentando acceder a ellos y evadir controles de acceso mediante escaneos, trucos en URLs y fuzzing. Finalmente, explotan accediendo a archivos sensibles, listando contenidos y usando técnicas para evadir restricciones. Esto puede exponer configuraciones, credenciales o información crítica del sistema.


![](/img/9.png)

# Descarga del Registro CVE de la vulnerabilidad
El registro de CVE o CVE Record es un registro con información dela vulnerabilidad donde incluye información de dicha vulnerabilidad.

Este registro se utiliza para el tratamiento automatizado de la información, pudiendo ser utilizado por diferentes utilidades de seguridad.

En él está comprendida información en formato xml o JSON sobre CWE, CPE, CAPEC, etc..

Podemos descargarla o acceder a su información, desde la página de cve.org dándole al enlace **View JSON**

![](/img/10.png)

En algunas ocasiones nos podemos encontrar que en él figura información que no aparece en la página de la cve.

![](/img/11.png)