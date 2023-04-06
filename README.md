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

    
    Chapter 7. About the installer inventory file
Red Hat Ansible Automation Platform works against a list of managed nodes or hosts in your infrastructure that are logically organized, using an inventory file. You can use the Red Hat Ansible Automation Platform installer inventory file to specify your installation scenario and describe host deployments to Ansible. By using an inventory file, Ansible can manage a large number of hosts with a single command. Inventories also help you use Ansible more efficiently by reducing the number of command line options you have to specify.

The inventory file can be in one of many formats, depending on the inventory plugins that you have. The most common formats are INI and YAML. Inventory files listed in this document are shown in INI format.

The location of the inventory file depends on the installer you used. The following table shows possible locations:

Installer	Location
Bundle tar

/ansible-automation-platform-setup-bundle-<latest-version>

Non-bundle tar

/ansible-automation-platform-setup-<latest-version>

RPM

/opt/ansible-automation-platform/installer

You can verify the hosts in your inventory using the command:

ansible all -i <path-to-inventory-file. --list-hosts
Example inventory file

[automationcontroller]
host1.example.com
host2.example.com
Host4.example.com

[automationhub]
host3.example.com

[database]
Host5.example.com

[all:vars]
admin_password='<password>'

pg_host=''
pg_port=''

pg_database='awx'
pg_username='awx'
pg_password='<password>'

registry_url='registry.redhat.io'
registry_username='<registry username>'
registry_password='<registry password>'
The first part of the inventory file specifies the hosts or groups that Ansible can work with.

7.1. Guidelines for hosts and groups
Databases

When using an external database, ensure the [database] sections of your inventory file are properly set up.
To improve performance, do not colocate the database and the automation controller on the same server.
Automation hub

If there is an [automationhub] group, you must include the variables automationhub_pg_host and automationhub_pg_port.
Add Ansible automation hub information in the [automationhub] group
Do not install Ansible automation hub and automation controller on the same node.
Provide a reachable IP address or fully qualified domain name (FDQN) for the [automationhub] and [automationcontroller] hosts to ensure that users can synchronize and install content from Ansible automation hub and automation controller from a different node. Do not use localhost.
Private automation hub

Do not install private automation hub and automation controller on the same node.
You can use the same Postgresql (database) instance, but they must use a different (database) name.
If you install private automation hub from an internal address, and have a certificate which only encompasses the external address, it can result in an installation you cannot use as a container registry without certificate issues.
Important
You must separate the installation of automation controller and Ansible automation hub because the [database] group does not distinguish between the two if both are installed at the same time.

If you use one value in [database] and both automation controller and Ansible automation hub define it, they would use the same database.

Automation controller

Automation controller does not configure replication or failover for the database that it uses. automation controller works with any replication that you have.
Clustered installations

When upgrading an existing cluster, you can also reconfigure your cluster to omit existing instances or instance groups. Omitting the instance or the instance group from the inventory file is not enough to remove them from the cluster. In addition to omitting instances or instance groups from the inventory file, you must also deprovision instances or instance groups before starting the upgrade. See Deprovisioning nodes or groups. Otherwise, omitted instances or instance groups continue to communicate with the cluster, which can cause issues with automation controller services during the upgrade.
If you are creating a clustered installation setup, you must replace [localhost] with the hostname or IP address of all instances. Installers for automation controller, automation hub, and automation services catalog do not accept [localhost] All nodes and instances must be able to reach any others using this hostname or address. In other words, you cannot use the localhost ansible_connection=local on one of the nodes. Use the same format for the host names of all the nodes.

Therefore, this does not work:

[automationhub]
localhost ansible_connection=local
hostA
hostB.example.com
172.27.0.4
Instead, use these formats:

[automationhub]
hostA
hostB
hostC
or

[automationhub]
hostA.example.com
hostB.example.com
hostC.example.com
7.2. Deprovisioning nodes or groups
You can deprovision nodes and instance groups using the Ansible Automation Platform installer. Running the installer will remove all configuration files and logs attached to the nodes in the group.

Note
You can deprovision any hosts in your inventory except for the first host specified in the [automationcontroller] group.

To deprovision nodes, append node_state=deprovision to the node or group within the inventory file.

For example:

To remove a single node from a deployment:

[automationcontroller]
host1.example.com
host2.example.com
host4.example.com   node_state=deprovision
or

To remove an entire instance group from a deployment:

[instance_group_restrictedzone]
host4.example.com
host5.example.com

[instance_group_restrictedzone:vars]
node_state=deprovision
7.3. Inventory variables
The second part of the example inventory file, following [all:vars], is a list of variables used by the installer. Using all means the variables apply to all hosts.

To apply variables to a particular host, use [hostname:vars]. For example, [automationhub:vars].

7.4. Rules for declaring variables in inventory files
The values of string variables are declared in quotes. For example:

pg_database='awx'
pg_username='awx'
pg_password='<password>'
When declared in a :vars section, INI values are interpreted as strings. For example, var=FALSE creates a string equal to FALSE. Unlike host lines, :vars sections accept only a single entry per line, so everything after the = must be the value for the entry. Host lines accept multiple key=value parameters per line. Therefore they need a way to indicate that a space is part of a value rather than a separator. Values that contain whitespace can be quoted (single or double). See the Python shlex parsing rules for details.

If a variable value set in an INI inventory must be a certain type (for example, a string or a boolean value), always specify the type with a filter in your task. Do not rely on types set in INI inventories when consuming variables.

Note
Consider using YAML format for inventory sources to avoid confusion on the actual type of a variable. The YAML inventory plugin processes variable values consistently and correctly.

If a parameter value in the Ansible inventory file contains special characters, such as #, { or }, you must double-escape the value (that is enclose the value in both single and double quotation marks).

For example, to use mypasswordwith#hashsigns as a value for the variable pg_password, declare it as pg_password='"mypasswordwith#hashsigns"' in the Ansible host inventory file.

7.5. Securing secrets in the inventory file
You can encrypt sensitive or secret variables with Ansible Vault. However, encrypting the variable names as well as the variable values makes it hard to find the source of the values. To circumvent this, you can encrypt the variables individually using ansible-vault encrypt_string, or encrypt a file containing the variables.

Procedure

Create a file labeled credentials.yml to store the encrypted credentials.

$ cat credentials.yml

admin_password: my_long_admin_pw
pg_password: my_long_pg_pw
registry_password: my_long_registry_pw
Encrypt the credentials.yml file using ansible-vault.

$ ansible-vault encrypt credentials.yml
New Vault password:
Confirm New Vault password:
Encryption successful
Important
Store your encrypted vault password in a safe place.

Verify that the credentials.yml file is encrypted.

$ cat credentials.yml
$ANSIBLE_VAULT;1.1;
AES256363836396535623865343163333339613833363064653364656138313534353135303764646165393765393063303065323466663330646232363065316666310a373062303133376339633831303033343135343839626136323037616366326239326530623438396136396536356433656162333133653636616639313864300a353239373433313339613465326339313035633565353464356538653631633464343835346432376638623533613666326136343332313163343639393964613265616433363430633534303935646264633034383966336232303365383763
Run setup.sh for installation of Ansible Automation Platform 2.3 and pass both credentials.yml and the --ask-vault-pass option.

$ ANSIBLE_BECOME_METHOD='sudo' ANSIBLE_BECOME=True ANSIBLE_HOST_KEY_CHECKING=False ./setup.sh -e @credentials.yml -- --ask-vault-pass
7.6. Additional inventory file variables
You can further configure your Red Hat Ansible Automation Platform installation by including additional variables in the inventory file. These configurations add optional features for managing your Red Hat Ansible Automation Platform. Add these variables by editing the inventory file using a text editor.

A table of predefined values for inventory file variables can be found in Inventory File Variables in the Red Hat Ansible Automation Platform Installation Guide.
