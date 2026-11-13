# Complementos Riwi · AWS desde la terminal

Material complementario de la ruta **AWS + Patrones de diseño**. Aquí encuentras los conceptos, los comandos y las actividades para trabajar con AWS usando la CLI.

## Objetivo de la semana 1

Comprender los fundamentos de AWS (modelo de nube, IAM y cómputo) para desplegar recursos básicos de forma segura.

**Reto:** levantar una instancia EC2 con acceso controlado mediante IAM y roles, aplicando en el código de despliegue al menos un patrón creacional.

## Contenido

| Carpeta | Tema | Qué vas a lograr |
|---|---|---|
| [`01-CONFIGURACION`](./01-CONFIGURACION) | AWS CLI | Instalar la CLI y conectar tu terminal con tu cuenta |
| [`02-IAM`](./02-IAM) | Identidad y permisos | Crear usuarios y políticas con menor privilegio |
| [`03-BUCKETS`](./03-BUCKETS) | Almacenamiento en S3 | Crear un bucket, subir archivos y protegerlo |
| [`04-ROLES`](./04-ROLES) | Roles y perfiles de instancia | Crear un rol para que una EC2 use otros servicios sin llaves |
| [`05-EC2`](./05-EC2) | Cómputo y redes | Lanzar un servidor web protegido que usa ese rol |

Recorre las carpetas en orden: cada una usa lo que aprendiste en la anterior.

## Cómo usar cada carpeta

| Archivo | Para qué sirve | Cuándo abrirlo |
|---|---|---|
| `01-info.md` | Explica el concepto: qué es, para qué sirve y una analogía | Primero, para entender el tema |
| `02-command.md` | Lista de comandos listos para copiar | Mientras practicas, como consulta |
| `03-activity.md` | La actividad que debes resolver y entregar | Al final, para poner a prueba lo aprendido |

## Requisitos

- Una cuenta de AWS activa, con MFA.
- Una terminal (Linux, macOS o Windows con WSL o PowerShell).
- Un editor de texto, como VS Code.
- AWS CLI v2. La guía paso a paso está en [`01-CONFIGURACION`](./01-CONFIGURACION/03-activity.md) y la documentación oficial de instalación aquí:

  https://docs.aws.amazon.com/es_es/cli/latest/userguide/getting-started-install.html

## Antes de cada práctica

Corre estos dos comandos y confirma que eres quien crees y que estás en la región correcta:

```bash
aws sts get-caller-identity
aws configure get region
```

## Glosario rápido

| Término | Significado |
|---|---|
| **CLI** | Command Line Interface: la herramienta para manejar AWS desde la terminal |
| **IAM** | Identity and Access Management: el servicio de identidades y permisos |
| **ARN** | Amazon Resource Name: el identificador único de cualquier recurso de AWS |
| **S3** | Simple Storage Service: el servicio de almacenamiento de archivos |
| **Bucket** | Contenedor de archivos en S3 |
| **Rol** | Identidad sin llaves permanentes que se asume de forma temporal |
| **EC2** | Elastic Compute Cloud: el servicio de servidores virtuales |
| **AMI** | Amazon Machine Image: la plantilla para crear una instancia |
| **VPC** | Virtual Private Cloud: tu red privada dentro de AWS |
| **Región** | Zona geográfica donde se crean los recursos, por ejemplo `us-east-2` |

## Si tu cuenta es nueva (plan gratuito con proyectos)

Las cuentas creadas con la experiencia nueva de AWS tienen algunas restricciones:

- **Créditos y plazo limitados.** Cuando se acaban, se cierra el acceso.
- **Una sola región.** Recursos como EC2 solo funcionan en la región de tu proyecto.
- **Sin grupos de IAM.** Las políticas se adjuntan directo al usuario.
- **Sin contraseñas de consola para usuarios IAM.**

No actives las "características avanzadas" para saltarte estas restricciones: exige pasar a un plan de pago, elimina el límite de gasto y no se puede revertir.

## Reglas de seguridad

- Nunca subas llaves de acceso, archivos `.csv` ni archivos `.pem` a GitHub.
- Nunca pegues una clave secreta en un chat, una captura o una evidencia.
- Da solo los permisos mínimos que la tarea necesita.
- Nunca abras el puerto 22 de una instancia a todo internet.
- Si una llave se expone, bórrala de inmediato en IAM y crea otra.

## Al terminar cada práctica

Borra lo que creaste. Los recursos encendidos consumen tus créditos aunque no los uses.

| Recurso | Qué hacer |
|---|---|
| Instancias EC2 | Terminarlas |
| Security groups y pares de llaves | Borrarlos |
| Buckets | Vaciarlos y borrarlos |
| Usuarios y llaves de prueba | Borrarlos |
| Roles y perfiles de instancia | Borrarlos al terminar la práctica de EC2 |

## Entregas

Cada `03-activity.md` indica su entregable. En general es un archivo `evidencia.md` con las salidas de los comandos y las respuestas a las preguntas de reflexión.

## Errores más comunes

| Error | Qué significa |
|---|---|
| `AccessDenied ... no identity-based policy allows` | A tu usuario le falta un permiso |
| `AccessDenied ... explicit deny in a service control policy` | Tu cuenta lo bloquea |
| `ParamValidation` | El comando está mal escrito |
| `NoRegion` | Falta configurar la región |
| `NoSuchEntity` | Lo que buscas no existe o no está adjunto |

El detalle de cada uno está en el `02-command.md` de cada carpeta.

## Recursos

- [Documentación de la AWS CLI](https://docs.aws.amazon.com/es_es/cli/latest/userguide/)
- [Guía de usuario de IAM](https://docs.aws.amazon.com/es_es/IAM/latest/UserGuide/)
- [Guía de usuario de S3](https://docs.aws.amazon.com/es_es/AmazonS3/latest/userguide/)
- [Guía de usuario de EC2](https://docs.aws.amazon.com/es_es/AWSEC2/latest/UserGuide/)