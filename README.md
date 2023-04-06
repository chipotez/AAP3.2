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

Esto es necesario para que puedas trabajar con actualizaciones y colecciones de proyectos:

- Asegúrate de que los siguientes nombres de dominio formen parte de la lista de permitidos del firewall o del proxy para una conexión y descarga exitosa de colecciones desde el Automation Hub o el servidor Galaxy:

    - galaxy.ansible.com
    - cloud.redhat.com
    - console.redhat.com
    - sso.redhat.com

- La inspección SSL debe estar deshabilitada, ya sea cuando se usan certificados autofirmados o para los dominios de Red Hat.

:warning: Nota: Los requisitos para los sistemas administrados por Ansible Automation Platform son los mismos que para Ansible. Consulta el apartado "Introducción" de [Getting Started](https://docs.ansible.com/ansible/latest/user_guide/intro_getting_started.html).

Notas adicionales para los requisitos de Red Hat Ansible Automation Platform:

- Los requisitos para los sistemas administrados por Ansible Automation Platform son los mismos que para Ansible. Consulta el apartado "Introducción" de la Guía del usuario de Ansible.
- Aunque Red Hat Ansible Automation Platform depende de los Playbooks de Ansible y requiere la instalación de la última versión estable de Ansible antes de instalar el controlador de automatización, las instalaciones manuales de Ansible ya no son necesarias.
- Para las nuevas instalaciones, el controlador de automatización instala el paquete de la versión más reciente de Ansible 2.3.
- Si se realiza una instalación empaquetada de Ansible Automation Platform, el programa de instalación intenta instalar Ansible (y sus dependencias) desde el paquete por ti.
- Si decides instalar Ansible por tu cuenta, el programa de instalación de Ansible Automation Platform detecta que Ansible ha sido instalado y no intenta reinstalarlo.

:warning: Nota: Debes instalar Ansible utilizando un administrador de paquetes como yum, y la versión estable más reciente del administrador de paquetes debe estar instalada para que Red Hat Ansible Automation Platform funcione correctamente. La versión 2.9 de Ansible es requerida para las versiones 3.8 y posteriores.

## Requisitos del sistema del controlador de automatización

El controlador de automatización es un sistema distribuido, donde diferentes componentes de software pueden estar colocados o desplegados en varios nodos de cómputo. En el instalador, se proporcionan los tipos de nodo de control, híbrido, ejecución y salto como abstracciones para ayudarte a diseñar la topología adecuada para tu caso de uso.

Utiliza las siguientes recomendaciones para el tamaño de los nodos:

:warning: Nota: En todos los nodos excepto los nodos de salto, asigna un mínimo de 20 GB a /var/lib/awx para el almacenamiento del entorno de ejecución.

**Nodos de ejecución**

Ejecuta la automatización. Aumenta la memoria y la CPU para aumentar la capacidad de ejecución de más procesos.

| Requisito | Requerido |
| --- | --- |
| RAM | 16 GB |
| CPUs | 4 |

**Nodos de control**

Procesa eventos y ejecuta trabajos de clúster, incluyendo actualizaciones de proyectos y trabajos de limpieza. Aumentar la CPU y la memoria puede ayudar con el procesamiento de eventos de trabajo.

| Requisito | Requerido |
| --- | --- |
| RAM | 16 GB |
| CPUs | 4 |

**Nodos híbridos**

Ejecuta tanto automatización como trabajos de clúster. Los comentarios sobre la CPU y la memoria

| Requisito | Requerido |
| --- | --- |
| RAM | 16 GB |
| CPUs | 4 |


Chapter 5. Attaching your Red Hat Ansible Automation Platform subscription
You must have valid subscriptions attached on all nodes before installing Red Hat Ansible Automation Platform. Attaching your Ansible Automation Platform subscription allows you to access subcription-only resources necessary to proceed with the installation.

Note
Attaching a subscription is unnecessary if you have enabled Simple Content Access Mode on your Red Hat account. Once enabled, you will need to register your systems to either Red Hat Subscription Management (RHSM) or Satellite before installing the Ansible Automation Platform. See Simple Content Access Mode for more information.

Procedure

Obtain the pool_id for your Red Hat Ansible Automation Platform subscription:

<pre>[root@app ~]# subscription-manager list --available --all | grep &quot;Ansible Automation Platform&quot; -B 3 -A 6
Ends:                10/11/2023
Entitlement Type:    Physical

Subscription Name:   Red Hat <span style="color:#C01C28"><b>Ansible Automation Platform</b></span>, Self-Support (100 Managed Nodes, NFR, Partner Only)
Provides:            Red Hat <span style="color:#C01C28"><b>Ansible Automation Platform</b></span>
                     Red Hat Single Sign-On
                     JBoss Enterprise Application Platform
SKU:                 SER0496
Contract:            16686769
Pool ID:             2c94a0538636e30001863bc3c1663c04
Provides Management: No</pre>

Note
Do not use MCT4022 as a pool_id for your subscription because it can cause Ansible Automation Platform subscription attachment to fail.

Example

An example output of the subsciption-manager list command. Obtain the pool_id as seen in the Pool ID: section:

<pre>Subscription Name: Red Hat Ansible Automation, Premium (5000 Managed Nodes)
  Provides: Red Hat Ansible Engine
  Red Hat Ansible Automation Platform
  SKU: MCT3695
  Contract: ````
  Pool ID: &lt;pool_id&gt;
  Provides Management: No
  Available: 4999
  Suggested: 1</pre>
  
  Attach the subscription:
<pre>[root@app ~]# subscription-manager attach --pool=2c94a0538636e30001863bc3c1663c04
Successfully attached a subscription for: Red Hat Ansible Automation Platform, Self-Support (100 Managed Nodes, NFR, Partner Only)
</pre>

You have now attached your Red Hat Ansible Automation Platform subscriptions to all nodes.

Verification

Verify the subscription was successfully attached:

<pre>[root@app ~]# subscription-manager list --consumed
+-------------------------------------------+
   Consumed Subscriptions
+-------------------------------------------+
Subscription Name:   Red Hat Ansible Automation Platform, Self-Support (100 Managed Nodes, NFR, Partner Only)
Provides:            Red Hat Ansible Automation Platform
                     JBoss Enterprise Application Platform
                     Red Hat Single Sign-On
SKU:                 SER0496
Contract:            16686769
Account:             6696234
Serial:              8212813249902247294
Pool ID:             2c94a0538636e30001863bc3c1663c04
Provides Management: No
Active:              True
Quantity Used:       1
Service Type:        L1-L3
Roles:               
Service Level:       Self-Support
Usage:               
Add-ons:             
Status Details:      Subscription is current
Subscription Type:   Standard
Starts:              02/09/2023
Ends:                02/09/2024
Entitlement Type:    Physical
</pre>

Troubleshooting

If you are unable to locate certain packages that came bundled with the Ansible Automation Platform installer, or if you are seeing a Repositories disabled by configuration message, try enabling the repository using the command:

Red Hat Ansible Automation Platform 2.3 for RHEL 8
subscription-manager repos --enable ansible-automation-platform-2.3-for-rhel-8-x86_64-rpms

Red Hat Ansible Automation Platform 2.3 for RHEL 9
subscription-manager repos --enable ansible-automation-platform-2.3-for-rhel-9-x86_64-rpms

Chapter 6. Choosing and obtaining a Red Hat Ansible Automation Platform installer
Choose the Red Hat Ansible Automation Platform installer you need based on your Red Hat Enterprise Linux environment internet connectivity. Review the scenarios below and determine which Red Hat Ansible Automation Platform installer meets your needs.

6.1. Installing with internet access
Choose the Red Hat Ansible Automation Platform (AAP) installer if your Red Hat Enterprise Linux environment is connected to the internet. Installing with internet access retrieves the latest required repositories, packages, and dependencies. Choose one of the following ways to set up your AAP installer.

Tarball install

Navigate to https://access.redhat.com/downloads/content/480
Click Download Now for the Ansible Automation Platform <latest-version> Setup.

Extract the files:
`$ tar xvzf ansible-automation-platform-setup-<latest-version>.tar.gz`

Click Download Now for the Ansible Automation Platform <latest-version> Setup.

Extract the files:

`tar xvzf ansible-automation-platform-setup-<latest-version>.tar.gz`

RPM install

Install Ansible Automation Platform Installer Package

v.2.3 for RHEL 8 for x86_64

$ sudo dnf install --enablerepo=ansible-automation-platform-2.3-for-rhel-8-x86_64-rpms ansible-automation-platform-installer
v.2.3 for RHEL 9 for x86-64

$ sudo dnf install --enablerepo=ansible-automation-platform-2.3-for-rhel-9-x86_64-rpms ansible-automation-platform-installer
Note
dnf install enables the repo as the repo is disabled by default.

When you use the RPM installer, the files are placed under the /opt/ansible-automation-platform/installer directory.

6.2. Installing without internet access
Use the Red Hat Ansible Automation Platform (AAP) Bundle installer if you are unable to access the internet, or would prefer not to install separate components and dependencies from online repositories. Access to Red Hat Enterprise Linux repositories is still needed. All other dependencies are included in the tar archive.

Procedure

Navigate to https://access.redhat.com/downloads/content/480
Click Download Now for the Ansible Automation Platform <latest-version> Setup Bundle.
Extract the files:

$ tar xvzf ansible-automation-platform-setup-bundle-<latest-version>.tar.gz
