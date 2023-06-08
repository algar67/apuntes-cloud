## Solución para la alerta de AWS GuardDuty: UnauthorizedAcces: IAMUser/MaliciousIPCaller.Custom

1. **Identificar el IAM User**
   No se requiere acción de código en este paso, solo anota el nombre del IAM User mencionado en la alerta.

2. **Evaluar la situación**
   No se requiere acción de código en este paso, solo investiga los detalles de la alerta en el panel de GuardDuty o a través de la CLI.

3. **Aislar la cuenta comprometida**
   Revocar las credenciales del IAM User afectado
```shell
aws iam delete-access-key --user-name <IAMUser> --access-key-id <AccessKeyID>
```

4. **Investigar la fuente del ataque**
Puedes utilizar herramientas de terceros o servicios de reputación de IP para obtener información adicional sobre la IP maliciosa.

5. **Fortalecer la seguridad**
Implementar las siguientes acciones de seguridad:
- Habilitar la autenticación multifactor (MFA) para los usuarios de IAM
- Ajustar los permisos y políticas de IAM según sea necesario
- Implementar el acceso basado en roles (IAM Roles) en lugar de usar claves de acceso y secretas directamente en instancias EC2 u otros servicios

6. **Monitorear y revisar**
Continuar monitoreando con GuardDuty y revisar regularmente los registros y alertas




Recuerda reemplazar <IAMUser> con el nombre del usuario IAM mencionado en la alerta y <AccessKeyID> con el ID de clave de acceso específica del usuario.

Este es solo un ejemplo de cómo podrías solucionar la alerta utilizando la AWS CLI. Dependiendo de tus necesidades y configuración específica, es posible que debas realizar ajustes adicionales.

Ten en cuenta que es importante comprender completamente el impacto y las implicaciones de cada acción antes de ejecutar cualquier código en tu entorno de producción. Siempre se recomienda realizar pruebas en un entorno de prueba antes de implementar cambios en un entorno de producción.
