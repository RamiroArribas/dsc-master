Te paso unas notas a modo de resumen:

exemple link a new Github account with Git:

steps:
1.create in Github an account.
2.In Ubunto to clone the report:
git config --global user.name "becomingdatasc"
git config --global user.email becomingdatasc@gmail.com
cat ~/.gitconfig  ##comprobar que user and name are correct!!
git clone https://github.com/becomingdatasc/master-data-science.git


Verify that exists the file README.md in the Master-data-science directory:
cd Repos
cd master-data-science

In the case that create a new change in GitHub, after that you have to do a pull in ubuntu
to syncronise with Git:
Git pull 

In the case that create a new change in Git, after that you have to do the nexts 3 steps in 
Ubuntu to syncronise with Github.
Nota: se tiene que estar dentro del directorio donde se quiere subir el report 
(p.ej: Report/ master-data-science). 
git add <file name.md>    ## cada vez que se realiza una modificación de un a linea
git commit -m 'hacer comentario si se considera preciso'
git commit ## para grabarlo en Ubuntu.
git push   ## para subirlo a Github.

