# miguel_narvaiz_GCP
Practicas Keep coding DevOps 12 GCP 

Aqui estan los archivos solicitados para la practica Esta el archivo draw.io y se dio acceso al profesor para que lo pueda ver en directo con la app si no se puede ver el draw.io esta el archivo pdf con el diagrama. 

Los accesos a los dos proyectos se enviarion por mail al profesor directo desde la plataforma GCP, el proyecto de la primera practica tiene el nombre de "KC DevOps 12 GCP" para el segundo proyecto "KCGCP-Terraform" tambien se asigno acceso como "Owner" al profesor.

Para revisar la practica 1 los servcios e instancias estan apagadas entonces para lograr que funcionen se necesitan encender tanto la VM que esta en el apartado de instancias como el grupo de instancias que esta en el apartado de grupos y por ultimo la instancia de SQL que esta en el apartado de SQL

Solo se realizaron los paso 1,2,3 y el bonus 

Para el punto 3 necesitamos conectarnos al testserver-v2 en la ruta /home/naesman1devops buscar y editar el script stress_ab.sh y reemplazar la IP publica en el campo TARGET_URL  del servidor del MIG que este activo

Este es el script :

```
#!/bin/bash

# IP o dominio del Load Balancer
TARGET_URL="http://34.8.221.243/"

# Total de rondas de prueba
ROUNDS=10

# Parámetros de AB
TOTAL_REQUESTS=13000
CONCURRENCY=50

# Carpeta para resultados
RESULTS_DIR="ab_results"
mkdir -p $RESULTS_DIR

echo "Iniciando stress test con Apache Benchmark"
echo "URL objetivo: $TARGET_URL"
echo "Guardando resultados en ./$RESULTS_DIR"

for i in $(seq 1 $ROUNDS); do
  echo "----> Ronda $i"
  TIMESTAMP=$(date +%Y%m%d-%H%M%S)
  ab -n $TOTAL_REQUESTS -c $CONCURRENCY $TARGET_URL > $RESULTS_DIR/ab_result_$TIMESTAMP.txt
  echo "Esperando 5 segundos antes de la siguiente ronda..."
  sleep 5
done

echo "Stress test finalizado."
```
una vez que que el script haya terminado el MIG empeza a eliminar las instancias en un tiempo aproximado de 20 min


Para la practica bonus se agregaron al repositorio el archivo "credentials.txt" y "main.tf" estos dos archivos funcionan en conjunto para desplegar una arquitectura en GCP usando Terraform. El archivo "credentials.txt" esta en un rar por politicas de seguridad de GCP asi que es necesario extraerlo antes. 

Los pasos a seguir son los siguientes: 

1.- conectarnos al cloudshell del proyecto usando "gcloud config set project KCGCP-Terraform " 

2.- usando nano o algun editor de archivos, creamos los archivos "credentials.json" y "main.tf" copiamos y pegamos el contenido respectivamente ambos en el mismo path 

3.- utlizar "terraform init" para inicializar terreform 

4.- usar "terraform plan" para vizualizar los cambios y las instancias que se aplicaran 

5.- usar "terraform apply" para que los cambios tomen efecto y confirmar con "yes" 

6.- Validar que todo se haya instalado correctamente desde la consola 

7.- para destruir todo "terraform detroy" y confirmar con "yes"
