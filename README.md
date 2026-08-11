#Primer paso:
*Revisar si està instalado "Git" y "docker" de lo contrario descargarlo
#Segundo paso:
*Clonar el repositorio de github y abrir una terminal en la computadora y ejecutar:
git clone [https://github.com/mrodriguezzz/Elrealfinal.git](https://github.com/mrodriguezzz/Elrealfinal.git)
cd Elrealfinal
#Tercer paso:
*Dar permisos a Docker ejecutando:
xhost +local:root
#Cuarto paso:
*Descargar la imagen del contenedor ejecutando:
sudo docker pull maurozzz/elfinal:latest
#Quinto paso:
*Ejecutando el contenedor montando la carpeta actual del proyecto:
sudo docker run -it --rm \
  -v $(pwd):/geant4lab/proyecto \
  -e DISPLAY=$DISPLAY \
  -v /tmp/.X11-unix:/tmp/.X11-unix \
  maurozzz/elfinal:latest
#Sexto paso:
Entrar al directorio del proyecto montado:
cd /geant4lab/las_lluvias 
#Sèptimo paso:
*Crear la carpeta y ejecutar:
mkdir build
cd build
#Octavo paso:
*Compilar el còdigo:
cmake ..
make -j4
#Noveno paso:
*Ejecutar la simulaciòn
./sim
Si no sale, probarlo con:
./sim vis.mac

