# compumundo-employee-records-IAC

Este repositorio contiene una plantilla de AWS CloudFormation para automatizar el almacenamiento de registros de empleados en S3 mediante el uso de servicios como AWS Lambda y AWS KMS.

## Descripción

La plantilla de CloudFormation crea una pila de recursos en AWS que incluye los siguientes componentes:

- Un bucket de Amazon S3 llamado `active-employee-files-{companyName}`: Este bucket se utiliza para almacenar los archivos de los empleados activos. Cada vez que se crea un objeto en este bucket, se invoca una función de AWS Lambda para procesarlo.
- Un bucket de Amazon S3 llamado `inactive-employee-files-{companyName}`: Este bucket se utiliza para almacenar los archivos de los empleados inactivos. Los archivos almacenados en este bucket se mueven automáticamente al almacenamiento de Glacier después de 5 días.
- Una función de AWS Lambda llamada `clean-files`: Esta función se invoca cuando se crea un objeto en el bucket de empleados activos. Su objetivo es procesar el archivo y realizar acciones como limpiar datos o desencadenar otros eventos. En este ejemplo, la función simplemente imprime los eventos y el contexto recibidos y devuelve un saludo.

## Uso del archivo CloudFormation.yaml

Para utilizar este archivo de plantilla de AWS CloudFormation, sigue estos pasos:

1. Asegúrate de tener una cuenta de AWS activa.
2. Clona este repositorio en tu máquina local.
3. Abre la consola de AWS y navega a la sección de AWS CloudFormation.
4. Selecciona "Crear pila" y luego elige "Subir un archivo de plantilla" para cargar el archivo `CloudFormation.yaml`.
5. Proporciona el nombre de la empresa en el campo correspondiente.
6. Revisa y confirma las opciones de configuración.
7. Haz clic en "Crear pila" para iniciar la implementación.
8. Espera a que la implementación se complete (puede tomar unos minutos).
9. Una vez que la pila se haya creado correctamente, tendrás acceso a los nuevos recursos creados (buckets de S3 y función Lambda) a través de la consola de AWS.

## Notas adicionales

- Asegúrate de revisar los comentarios dentro del archivo `CloudFormation.yaml` para entender mejor la configuración de los recursos y ajustarla según tus necesidades.
- Este proyecto es solo un ejemplo de automatización del almacenamiento de registros de empleados. Puedes personalizarlo y agregar más funcionalidad si es necesario.
- Recuerda eliminar los recursos creados (la pila de CloudFormation) cuando ya no los necesites para evitar costos innecesarios.

## Contribución

Si deseas contribuir a este proyecto, puedes seguir estos pasos:

1. Realiza un fork de este repositorio.
2. Crea una nueva rama en tu repositorio fork para hacer tus cambios.
3. Haz los cambios que desees realizar.
4. Realiza una solicitud de extracción (pull request) con una descripción clara de tus cambios y los motivos detrás de ellos.

## Problemas

Si encuentras algún problema o tienes alguna sugerencia, por favor abre un problema en este repositorio o contacta al propietario del repositorio.

## Licencia

Este proyecto está bajo la [Licencia MIT](LICENSE).