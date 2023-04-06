# Configuracion de Hostname

Para configurar el hostname en Red Hat Enterprise Linux (RHEL) 8, puedes utilizar el comando hostnamectl. A continuación, se muestran algunos ejemplos de cómo utilizar este comando con diferentes opciones y argumentos:

1. Para establecer el hostname del sistema:

`sudo hostnamectl set-hostname NOMBRE_DE_HOST`

Donde NOMBRE_DE_HOST es el nombre que deseas asignar al sistema. Este comando establece el hostname de forma temporal. Si deseas establecer el hostname de forma permanente, también debes editar el archivo /etc/hostname con el nombre del hostname.

2. Para establecer el hostname del sistema y asignar un nombre de dominio:

`sudo hostnamectl set-hostname NOMBRE_DE_HOST.NOMBRE_DE_DOMINIO`

Donde NOMBRE_DE_HOST es el nombre que deseas asignar al sistema y NOMBRE_DE_DOMINIO es el nombre de dominio que deseas asociar al sistema. Este comando establece el hostname de forma temporal y modifica el archivo /etc/hostname con el nuevo hostname.

3. Para establecer el hostname del sistema y modificar el archivo /etc/hosts para que coincida con el hostname:

`sudo hostnamectl set-hostname --static NOMBRE_DE_HOST`

Donde NOMBRE_DE_HOST es el nombre que deseas asignar al sistema. Este comando establece el hostname de forma temporal y modifica el archivo /etc/hostname y /etc/hosts para que coincidan con el nuevo hostname.

4. Para establecer el hostname del sistema y modificar el archivo /etc/machine-info con información adicional:

`sudo hostnamectl set-hostname --pretty "NOMBRE PRESENTABLE" --icon-name ICONO --chassis TIPO_CHASIS`

Donde NOMBRE PRESENTABLE es un nombre que describes el sistema, ICONO es el nombre del icono asociado con el sistema y TIPO_CHASIS es el tipo de chasis del sistema (por ejemplo, laptop o desktop). Este comando establece el hostname de forma temporal y modifica el archivo /etc/hostname y /etc/machine-info con la información adicional.

5. Para mostrar la información actual del hostname:

`hostnamectl`

Este comando muestra la información actual del hostname, incluyendo el hostname actual, el nombre de dominio, la información presentable, el icono asociado y el tipo de chasis.

Estos son solo algunos ejemplos de cómo configurar el hostname en RHEL 8 utilizando hostnamectl. Es importante tener en cuenta que, para realizar cambios permanentes en el hostname, también debes editar los archivos correspondientes (por ejemplo, /etc/hostname, /etc/hosts o /etc/machine-info).





# Para crear un snapshot en KVM, sigue estos pasos:

1. Abre el hipervisor KVM y accede a la máquina virtual (VM) que deseas tomar el snapshot.

2. Detén la VM utilizando el siguiente comando de KVM:

`virsh shutdown nombre_de_la_vm`

3. Una vez que la VM esté detenida, toma el snapshot utilizando el siguiente comando de KVM:

`virsh snapshot-create-as nombre_de_la_vm nombre_del_snapshot`

Donde:
- nombre_de_la_vm es el nombre de la VM que deseas tomar el snapshot.
- nombre_del_snapshot es el nombre que deseas asignar al snapshot.
4. Inicia la VM nuevamente utilizando el siguiente comando de KVM:


`virsh start nombre_de_la_vm`

O, si deseas utilizar la interfaz gráfica de usuario, puedes hacer clic derecho en la VM en la lista de VMs y seleccionar "Arrancar".

Con estos pasos, deberías poder crear un snapshot de una VM de KVM de manera sencilla. Es importante tener en cuenta que los comandos pueden variar ligeramente según la distribución de Linux que estés utilizando y la versión de KVM que tengas instalada.

Recuerda que los snapshots se utilizan para capturar el estado actual de una VM y permiten volver a ese estado en cualquier momento en el futuro. Es importante tener en cuenta que los snapshots pueden ocupar una cantidad significativa de espacio en disco y pueden afectar el rendimiento de la VM, por lo que es recomendable utilizarlos con moderación y borrarlos cuando ya no sean necesarios.


# Clonar una VM en KVM

Para clonar una VM en KVM utilizando el comando virsh, sigue estos pasos:

1. Abre el hipervisor KVM y accede a la VM que deseas clonar.

2. Detén la VM utilizando el siguiente comando de KVM:


`virsh shutdown nombre_de_la_vm`

3. Una vez que la VM esté detenida, clónala utilizando el siguiente comando de KVM:

`virt-clone --original nombre_de_la_vm --name nombre_de_la_nueva_vm --auto-clone`

Donde:

- nombre_de_la_vm es el nombre de la VM que deseas clonar.
- nombre_de_la_nueva_vm es el nombre que deseas asignar a la nueva VM.

4. Inicia la nueva VM utilizando el siguiente comando de KVM:

`virsh start nombre_de_la_nueva_vm`

O, si deseas utilizar la interfaz gráfica de usuario, puedes hacer clic derecho en la nueva VM en la lista de VMs y seleccionar "Arrancar".

Con estos pasos, deberías poder clonar una VM de KVM de manera sencilla utilizando el comando virsh. Es importante tener en cuenta que los comandos pueden variar ligeramente según la distribución de Linux que estés utilizando y la versión de KVM que tengas instalada. Además, ten en cuenta que la nueva VM será una copia exacta de la original, por lo que necesitarás cambiar su configuración y/o nombre si deseas utilizarla con una finalidad distinta a la original.
