################################################################################
# Solución para la alerta de GuardDuty: Acceso no autorizado: IAMUser/MaliciousIPCaller.Custom
################################################################################

# 1. Identificar el IAM User
# No se requiere acción de código en este paso, solo anota el nombre del IAM User mencionado en la alerta.

# 2. Evaluar la situación
# No se requiere acción de código en este paso, solo investiga los detalles de la alerta en el panel de GuardDuty o a través de la CLI.

# 3. Aislar la cuenta comprometida
# Revocar las credenciales del IAM User afectado
aws iam delete-access-key --user-name <IAMUser> --access-key-id <AccessKeyID>

# 4. Investigar la fuente del ataque
# Puedes utilizar herramientas de terceros o servicios de reputación de IP para obtener información adicional sobre la IP maliciosa.

# 5. Fortalecer la seguridad
# Implementar las siguientes acciones de seguridad:

# Habilitar la autenticación multifactor (MFA) para los usuarios de IAM
# Ajustar los permisos y políticas de IAM según sea necesario
# Implementar el acceso basado en roles (IAM Roles) en lugar de usar claves de acceso y secretas directamente en instancias EC2 u otros servicios

# 6. Monitorear y revisar
# Continuar monitoreando con GuardDuty y revisar regularmente los registros y alertas

