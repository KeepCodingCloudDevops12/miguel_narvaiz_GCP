# miguel_narvaiz_GCP
Practicas Keep coding DevOps 12 GCP 

Aqui estan los archivos solicitados para la practica Esta el archivo draw.io y se dio acceso al profesor para que lo pueda ver en directo con la app si no se puede ver el draw.io esta el archivo pdf con el diagrama los accesos a los dos proyectos se enviarion por mail al profesor directo desde la plataforma GCP el proyecto de la primera practica tiene el nombre de "KC DevOps 12 GCP" para el segundo proyecto "KCGCP-Terraform" tambien se asigno acceso como "Owner" al profesor.

Para revisar la practica 1 los servcios e instancias estan apagadas entonces para lograr que funcionen se necesitan encender tanto la VM que esta en el apartado de instancias como el grupo de instancias que esta en el apartado de grupos y por ultimo la instancia de SQL que esta en el apartado de SQL

Solo se realizaron los paso 1,2,3 y el bonus 

Para la practica bonus se agregaron al repositorio el archivo "credentials.json" y "main.tf" estos dos archivos funcionan en conjunto para desplegar una arquitectura en GCP usando Terraform. Los pasos a seguir son los siguientes: 

1.- conectarnos al cloudshell del proyecto usando "gcloud config set project KCGCP-Terraform " 

2.- usando nano o algun editor de archivos, creamos los archivos "credentials.json" y "main.tf" copiamos y pegamos el contenido respectivamente ambos en el mismo path 

3.- utlizar "terraform init" para inicializar terreform 

4.- usar "terraform plan" para vizualizar los cambios y las instancias que se aplicaran 

5.- usar "terraform apply" para que los cambios tomen efecto y confirmar con "yes" 

6.- Validar que todo se haya instalado correctamente desde la consola 

7.- para destruir todo "terraform detroy" y confirmar con "yes"
