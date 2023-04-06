# RED HAT ANSIBLE AUTOMATION PLATFORM 2.3

Red Hat Ansible Automation Platform simplifica el desarrollo y la operación de cargas de trabajo de automatización para administrar los ciclos de vida de la infraestructura de aplicaciones empresariales. Funciona en múltiples dominios de TI, incluidas operaciones, redes, seguridad y desarrollo, así como en diversos entornos híbridos. Descargue el paquete "setup" a continuación para instalar los componentes autohospedados de Ansible Automation Platform en Red Hat Enterprise Linux. Si está instalando en un entorno sin conexión, descargue en su lugar el paquete "setup bundle".

1.1. Requisitos 
* Ha elegido y obtenido un instalador de plataforma del Software [ Red Hat Ansible Automation Platform Product Software.](https://access.redhat.com/downloads/content/480/ver=2.3/rhel---9/2.3/x86_64/product-software)
* Está instalando en una máquina que cumple con los requisitos del sistema base.
* Ha creado una cuenta de servicio de registro de Red Hat, siguiendo las instrucciones de la guía [Creating Registry Service Accounts guide.](https://access.redhat.com/RegistryAuthentication#creating-registry-service-accounts-6)

RECURSOS ADICIONALES

Para obtener más información sobre cómo obtener un instalador de plataforma o los requisitos del sistema, consulte los requisitos del sistema de [Red Hat Ansible Automation Platform system requirements](https://access.redhat.com/documentation/en-us/red_hat_ansible_automation_platform/2.3/html/red_hat_ansible_automation_platform_planning_guide/platform-system-requirements) dentro de Red Hat Ansible Automation Platform Planning Guide

## Creación de cuentas de servicio de registro
Diríjase a la Aplicación de Gestión de Cuentas de Servicio de Registro e inicie sesión si es necesario.

1. En la página de Cuentas de Servicio de Registro, haga clic en el botón Nueva Cuenta de Servicio.
2. Proporcione un nombre para la cuenta de servicio. Se le antepone una cadena fija y aleatoria.
    - Ingrese una descripción.
    - Haga clic en crear.
    
3. Vuelva a sus Cuentas de Servicio.
4. Haga clic en la cuenta de servicio que creó.
    - Tome nota del nombre de usuario, que incluye la cadena antepuesta (es decir, XXXXXXX|nombredeusuario). Este es el nombre de usuario que debe usarse para iniciar sesión en registry.redhat.io.
    - Tome nota de la contraseña. Esta es la contraseña que debe usarse para iniciar sesión en registry.redhat.io.
Hay pestañas disponibles dentro de la página de Información de Token que ofrecen orientación sobre cómo utilizar el token de autenticación para diversos escenarios. Por ejemplo, la pestaña Inicio de Sesión de Docker demuestra cómo se puede utilizar el token con la CLI de Docker.
