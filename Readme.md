# admin_servers
# Comandos para crear llaves de ssh a git Hub
# Para comprobar si se tiene ssh en el equipo:
ssh -V
# Para comprobar la existencia de llaves hay que moverse al directoio de ssh, el ~ se obtiene con OPTION Ñ (MAC)
cd ~/.ssh
# Para generar la llave
ssh-keygen -t rsa -b 4096 -C arprieto@cisco.com
# Al aplicar este comando nos preguntara el nombre del archivo donde se almacenara la llave el default es id_rsa
# Preguntara la contraseña del repositorio donde nos queramos conectar, en este caso es GIT
# Al terminar va a crear 2 archivos:
# id_rsa y id_rsa.pub e indicara el figerprint 
# Vamos a revisae las llaves de ssh que tenemos en el directorio .ssh
eval "$(ssh-agent -s)"
# Ya que compruebe la existencia de llaves tenemos que agregarla y nos pedira la contraseña que dimos anteriormente
ssh-add ~/.ssh/id_rsa
# Ahora tenemos que agregar la llave en GIT HUB
# Tenemos que ir al menu (en la parte superior derecha de la pantalla)
# En la opcion SSH and GPR Keys
# Agregamos la nueva llave y esto se puede hacer con el comando
cat id_rsa.pub
# Desplegara la llave y a copiamos y la pegamos en GIT HUB
# La llave debe de aparece en color NEGRO ya que NO se ha usado
# Hay que crear un nuevo repositorio en GIT
# Vamos  repositorios y NUEVO
# Hay que poner el nombre del ropositorio, dejarlo publico, SIN marcar la opcion de crear README
# Creamos el archivo README.md con
touch README.md
# Editamos el archivo con NANO
nano README.md
# Inicializamos GIT
git init
# Agregamos los archivos a GIT
git add .
# Hacemos el commit a GIT
git commit -m "First Commit"
# Agregamos el remoto 
git remote add origin https://github.com/arturoprieto/admin_servers.git
# Hacemos el push
git push -u origin master

