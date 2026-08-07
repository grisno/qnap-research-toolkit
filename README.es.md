# QNAP Research Toolkit

[English](README.md) | [Español](README.es.md)

Herramientas no oficiales para diagnóstico avanzado, recuperación y análisis
forense de sistemas QNAP.

> [!WARNING]
> Este proyecto contiene herramientas experimentales y de bajo nivel destinadas
> a usuarios con experiencia, laboratorios controlados e investigación técnica
> autorizada. Un uso incorrecto puede provocar pérdida de datos, interrupciones
> de servicio, pérdida de conectividad, corrupción de firmware o que el sistema
> no vuelva a arrancar.

## Descripción

QNAP Research Toolkit es una colección de scripts, utilidades, notas técnicas y
procedimientos reproducibles para el estudio de sistemas NAS QNAP.

El proyecto se centra en inspección de hardware, diagnóstico de bajo nivel,
análisis de arranque, resolución de problemas de almacenamiento y red,
recopilación de evidencias forenses y procedimientos de recuperación.

Es un proyecto comunitario e independiente. No está desarrollado, mantenido,
respaldado, patrocinado ni avalado por QNAP Systems, Inc.

## Alcance

El repositorio puede incluir material relacionado con:

- Inventario de hardware y creación de perfiles forenses
- Análisis de BIOS, UEFI, CSM, BBS y NVRAM
- Inspección de dispositivos y orden de arranque
- Análisis de dispositivos PCI y PCI Express
- Inspección de EEPROM, NVM y option ROM
- Diagnóstico de adaptadores de red e investigación de recuperación
- Diagnóstico de almacenamiento, iSCSI, iSER y SCSI target
- Análisis de módulos del kernel y pruebas de compatibilidad
- Inspección y resolución de problemas de servicios QTS
- Recopilación de logs y paquetes para soporte técnico
- Procedimientos controlados de recuperación y reversión

## Estructura del repositorio

```text
qnap-research-toolkit/
├── docs/                 Documentación técnica y procedimientos
├── scripts/              Scripts de shell y automatización
├── tools/                Utilidades de diagnóstico y análisis
├── profiles/             Perfiles de hardware y sistema anonimizados
├── examples/             Configuraciones y resultados de ejemplo
├── templates/            Plantillas para nuevas herramientas y scripts
├── LICENSES/             Textos de licencia y criterios de uso
├── .gitattributes
├── .gitignore
├── LICENSE
├── README.md
├── README.es.md
└── THIRD_PARTY_NOTICES.md
```

La estructura puede evolucionar a medida que se incorporen nuevas herramientas
y áreas de investigación.

## Requisitos

Los requisitos dependen de cada herramienta. Un componente puede necesitar:

- Acceso SSH a la NAS
- Privilegios de administrador
- Acceso a la shell de QTS
- Bash o una shell compatible con POSIX
- Utilidades estándar de línea de comandos de Linux
- Herramientas de compilación o cabeceras de kernel compatibles
- Un dispositivo externo de recuperación
- Una copia de seguridad verificada de la configuración y los datos

Cada herramienta debe documentar sus dependencias, sistemas compatibles y
posibles efectos.

## Instalación

Clona el repositorio:

```bash
git clone https://github.com/grisno/qnap-research-toolkit.git
cd qnap-research-toolkit
```

Revisa el código y la documentación antes de ejecutar cualquier herramienta:

```bash
find . -maxdepth 3 -type f | sort
```

Concede permisos de ejecución solo cuando sea necesario:

```bash
chmod +x scripts/example-tool.sh
```

Consulta primero la ayuda o ejecuta el modo de inspección:

```bash
./scripts/example-tool.sh --help
```

## Principios de seguridad

Las herramientas del repositorio deberían cumplir estos principios:

1. Funcionar en modo de solo lectura por defecto siempre que sea posible.
2. Exigir confirmación explícita antes de cambios destructivos o persistentes.
3. Crear y verificar copias antes de modificar configuración, firmware o NVRAM.
4. Validar el modelo, la plataforma y los identificadores del dispositivo.
5. Registrar acciones, entradas, resultados y códigos de retorno.
6. Proporcionar un procedimiento de reversión o recuperación cuando sea posible.
7. Diferenciar claramente operaciones estables, experimentales y destructivas.
8. Evitar la redistribución de firmware propietario o binarios de fabricantes.

## Compatibilidad

Que una herramienta funcione en un modelo QNAP no garantiza que funcione en
otro modelo, revisión de hardware, versión de QTS, compilación del kernel o
configuración de arranque.

Antes de utilizarla, verifica como mínimo:

```text
Modelo QNAP
Versión y compilación de QTS
Versión del kernel
Arquitectura de CPU
Modo de arranque
Hardware instalado
Identificadores PCI y de dispositivo
Interfaz de almacenamiento o red objetivo
```

## Madurez de las herramientas

Cada herramienta debería indicar uno de estos estados:

| Estado | Significado |
|---|---|
| `stable` | Probada repetidamente en el entorno objetivo documentado |
| `testing` | Funcional, pero todavía en proceso de validación |
| `experimental` | Código de investigación con validación limitada |
| `dangerous` | Puede modificar firmware, NVRAM, metadatos o estado del hardware |

La etiqueta no constituye ninguna garantía. Revisa siempre el código y prepara
un procedimiento de recuperación.

## Información sensible

Antes de publicar informes o registros, elimina o sustituye:

- Contraseñas, tokens y cookies de sesión
- Claves privadas y certificados
- Direcciones IP públicas cuando no sea necesario mostrarlas
- Direcciones MAC cuando identifiquen un entorno privado
- Números de serie, UUID e identificadores de chasis
- Nombres de host, usuarios y organizaciones
- Contenido de almacenamiento y datos de clientes

Los ejemplos anonimizados deben conservar únicamente los datos necesarios para
reproducir o comprender el comportamiento técnico.

## Componentes propietarios

Este repositorio no concede permiso para redistribuir componentes propietarios
de QNAP, AMI, Intel, NVIDIA Networking/Mellanox, Broadcom u otros fabricantes.

Las imágenes de firmware, volcados de BIOS, option ROM, contenidos de EEPROM,
utilidades de fabricante y controladores binarios siguen sujetos a sus
respectivas licencias y derechos.

Siempre que sea posible, las herramientas deben solicitar al usuario su propia
copia autorizada o permitir que la extraiga, en lugar de incluir material
propietario.

## Código de terceros

Los archivos de terceros conservan sus avisos de copyright y licencias
originales.

Los archivos copiados o derivados del kernel Linux, de fuentes del kernel de
QNAP o de otro proyecto exclusivamente GPL-2.0 deben conservar su licencia
original. No pasan automáticamente a GPLv3.

Utiliza un identificador SPDX por archivo cuando sea posible:

```text
SPDX-License-Identifier: GPL-3.0-or-later
```

Los archivos derivados del kernel pueden requerir:

```text
SPDX-License-Identifier: GPL-2.0-only
```

La licencia original y el identificador incluido en cada archivo prevalecen
para ese archivo. Consulta [LICENSES/README.md](LICENSES/README.md) y
[THIRD_PARTY_NOTICES.md](THIRD_PARTY_NOTICES.md).

## Contribuciones

Las contribuciones deberían incluir:

- Una descripción técnica clara
- Modelos QNAP y versiones de QTS compatibles
- Pasos de reproducción o validación
- Controles de seguridad y cambios esperados
- Instrucciones de reversión
- Resultados de ejemplo anonimizados
- El identificador SPDX correcto

No envíes secretos, datos personales, firmware propietario sin autorización ni
material confidencial de fabricantes.

## Exención de responsabilidad

Este software se proporciona sin garantía.

Los autores y colaboradores no son responsables de pérdidas de datos, daños de
hardware, interrupciones de servicio, problemas de seguridad ni otras
consecuencias derivadas del uso del proyecto.

Utiliza estas herramientas únicamente en sistemas de tu propiedad o para los
que dispongas de autorización expresa de inspección, prueba o reparación.

## Licencia

Salvo que un archivo indique otra cosa, el código original del proyecto se
publica bajo la GNU General Public License, versión 3 o cualquier versión
posterior:

```text
GPL-3.0-or-later
```

Los componentes de terceros y las obras derivadas conservan sus respectivas
licencias. Consulta [LICENSE](LICENSE), los identificadores SPDX de cada archivo
y el directorio [LICENSES](LICENSES/).

## Marcas registradas

QNAP y los nombres de sus productos son marcas comerciales o marcas registradas
de QNAP Systems, Inc. Otros nombres pueden ser marcas de sus respectivos
propietarios.

Este proyecto independiente no está afiliado, patrocinado ni avalado por QNAP
Systems, Inc.
