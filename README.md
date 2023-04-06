# RED HAT ANSIBLE AUTOMATION PLATFORM 2.3

Red Hat Ansible Automation Platform simplifica el desarrollo y la operación de cargas de trabajo de automatización para administrar los ciclos de vida de la infraestructura de aplicaciones empresariales. Funciona en múltiples dominios de TI, incluidas operaciones, redes, seguridad y desarrollo, así como en diversos entornos híbridos. Descargue el paquete "setup" a continuación para instalar los componentes autohospedados de Ansible Automation Platform en Red Hat Enterprise Linux. Si está instalando en un entorno sin conexión, descargue en su lugar el paquete "setup bundle".

## Requisitos 
* Ha elegido y obtenido un instalador de plataforma del Software [ Red Hat Ansible Automation Platform Product Software.](https://access.redhat.com/downloads/content/480/ver=2.3/rhel---9/2.3/x86_64/product-software)
* Está instalando en una máquina que cumple con los requisitos del sistema base.
* Ha creado una cuenta de servicio de registro de Red Hat, siguiendo las instrucciones de la guía [Creating Registry Service Accounts guide.](https://access.redhat.com/RegistryAuthentication#creating-registry-service-accounts-6)

RECURSOS ADICIONALES

Para obtener más información sobre cómo obtener un instalador de plataforma o los requisitos del sistema, consulte los requisitos del sistema de [Red Hat Ansible Automation Platform system requirements](https://access.redhat.com/documentation/en-us/red_hat_ansible_automation_platform/2.3/html/red_hat_ansible_automation_platform_planning_guide/platform-system-requirements) dentro de Red Hat Ansible Automation Platform Planning Guide

## Creación de cuentas de servicio de registro
Diríjase a [Registry Service Account Management Application](https://access.redhat.com/terms-based-registry/) e inicie sesión si es necesario.

1. En la página de Cuentas de Servicio de Registro, haga clic en el botón Nueva Cuenta de Servicio.
2. Proporcione un nombre para la cuenta de servicio. Se le antepone una cadena fija y aleatoria.
    - Ingrese una descripción.
    - Haga clic en crear.
    
3. Vuelva a sus Cuentas de Servicio.
4. Haga clic en la cuenta de servicio que creó.
    - Tome nota del nombre de usuario, que incluye la cadena antepuesta (es decir, XXXXXXX|nombredeusuario). Este es el nombre de usuario que debe usarse para iniciar sesión en registry.redhat.io.
    - Tome nota de la contraseña. Esta es la contraseña que debe usarse para iniciar sesión en registry.redhat.io.
Hay pestañas disponibles dentro de la página de Información de Token que ofrecen orientación sobre cómo utilizar el token de autenticación para diversos escenarios. Por ejemplo, la pestaña Inicio de Sesión de Docker demuestra cómo se puede utilizar el token con la CLI de Docker.

<!--
https://access.redhat.com/terms-based-registry/
Token Information
themike.aap.test

eyJhbGciOiJSUzUxMiJ9.eyJzdWIiOiIzNmQ0OGNhOGRlYmI0NGVlOTdjZjViOWIxN2U0Mjg1NCJ9.tQgr3i6Tg_j8osBhdHJzaiDctDVFHTVPWG5-_jl1AyCaTh1_Ea_VmlBPNYZjgAf763QsEIJpMSHFwbHM9VJedLbKIn1mrzX7bXapymS79Yl3SbNXO4h0PbRxDlvJjg5Cf9zK_7UYDjSLtFkEvrAXTZjAm3dt7QfeQRbM8CkNyOJ4twM_5xfDlpphVdDG-6o1cDAlXwv5b3XWpdlbwLIFAemtB3TVmy6faAWVVgRhct6BKmrHQ6ZJgyM4yOz81LtT91jlfVNzf1Ync1wr5PF9CtGv53cr5ZeiWRK-3WIIk6p9gOjZav-0UMcdlxSgLX1iGUyU5U2ozCUaVpm3P0CcBmk4qE0dw4lDQgKSrLnLiFp9YYYs5UO8PxjAMgvMJg6TY-GsUsYWwer-9SWrhq-KV28JkCkyEeGPxyv5f9d4lni-6En3qnVdI0VTku-MPmyjbQlb2DP0ZECzdp0mYIW1NAJyhIEGnuuLWknDi6j_PeO3RxAxBcFgJ3nKn8LJ2GPod0JOIb1Hd67Ki93GcALrQOkV9eMdOBMxgsW8vegPtrP5WZfVAF4UqIhGM2MRuayuifLFtwpFMTtQ5mqeo5S51k2_UuXr_fG40-Upe6-1tbFJEImiJi6rALY0f9npTPFrt97MlVZx6zOkc8Blr9gc_8sYtVp8IHTs6eDfT8_M5is
-->

Tabla Sistema Base

|  | Required |	Notes |
| --- | --- | --- |
| Subscription | Valid Red Hat Ansible Automation Platform|  |
| OS | Red Hat Enterprise Linux 8.4 or later 64-bit (x86)|Red Hat Ansible Automation Platform is also supported on OpenShift, see Deploying the Red Hat Ansible Automation Platform operator on OpenShift Container Platform for more information.|
| Ansible | version 2.3 required |If Ansible is not already present on the system, the setup playbook will install ansible-core 2.14.|
| Python | 3.8 or later||
| Browser | A currently supported version of Mozilla FireFox or Google Chrome|
| Database | PostgreSQL version 13|

 
