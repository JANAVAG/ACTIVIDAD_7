# CÓDIGO ACTIVIDAD 7
#!/bin/bash
COMPARA=$(gsutil ls | grep "bkt07")
EQUIPO="LOS MIXTOS"
validacion(){
if [ "$COMPARA" = "gs://sit-devops-training-bkt07/" ]; then

        echo "El bucket ya existe"
        eliminacion_bucket

else
        creacion_bucket


fi

}

creacion_bucket(){

gsutil mb -p sit-devops-training -c standard -l us-east4 -b on gs://sit-devops-training-bkt07

}

impresion(){

echo $EQUIPO
date
}
eliminacion_bucket(){
gsutil rm -r gs://sit-devops-training-bkt07
}
validacion
impresion
