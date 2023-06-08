## Solución: Policy_S3_BucketBlockPublicAccessDisabled

La alerta "Policy_S3_BucketBlockPublicAccessDisabled" indica que el bloqueo de acceso público está desactivado en un bucket de Amazon S3. Para solucionar esta alerta, sigue estos pasos:

1. Accede a la consola de Amazon S3.

2. Navega hasta el bucket mencionado en la alerta.

3. Haz clic en la pestaña "Permissions" (Permisos) en la parte superior.

4. Desplázate hacia abajo hasta la sección "Block public access" (Bloqueo de acceso público).

5. Haz clic en el botón "Edit" (Editar).

6. Habilita las siguientes configuraciones de bloqueo de acceso público:
   - Block public access to buckets and objects granted through new access control lists (ACLs)
   - Block public access to buckets and objects granted through any access control lists (ACLs)
   - Block public access to buckets and objects granted through new public bucket or access point policies
   - Block public and cross-account access to buckets and objects through any public bucket or access point policies

7. Haz clic en "Save changes" (Guardar cambios).

Una vez que hayas realizado estos pasos, el bloqueo de acceso público estará habilitado en el bucket de Amazon S3 y la alerta "Policy_S3_BucketBlockPublicAccessDisabled" debería resolverse.

Recuerda revisar y aplicar las mejores prácticas de seguridad para tus buckets de Amazon S3 y asegurarte de que solo estén accesibles de acuerdo con tus requisitos y políticas de seguridad.
