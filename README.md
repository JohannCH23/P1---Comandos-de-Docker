#PRÁCTICA 1 SRI Johan Jahir Erazo Bacareo

    Descargar e comprobar que unha imaxe está no teu equipo:

Para isto temos que usar o comando (docker pull ubuntu) para descargala. E para comprobar as imaxes facemos o comando (docker images).

    Crear un contedor sen nome, queda arrincado?

Para crear o contedor debemos lanzar o comando (docker run -d ubuntu).
Para saber se quedou arrincado facemos o comando (docker ps -a), con este mostraranos a lista de todos os contedores.

    Crea un contedor co nome 'U1', como accedes a el?

Aquí, para crealo co nome, engadimos unha variante no comando (docker run -dit --name u1 ubuntu). Para acceder a el, só temos que facelo co comando (docker exec -it u1 bash), así xa entraremos.

    Comproba a súa IP e fai ping a google.com

Neste paso, desde fóra do contedor, tiven que colocar os seguintes comandos antes de poder facer ping con Google: (apt-get update) e (apt-get install -y iputils-ping).

Agora, si, podemos ir ao contedor co comando (docker exec -it u1 bash) e, xa dentro, facemos o ping con Google co seguinte comando (ping google.com).

    Crea un contedor co nome 'bono', pódese facer ping entre os contedores?

Empezamos creándoo como sempre (docker run -dit --name bono ubuntu).
Seguido, desde fóra do contedor, tiven que buscar a IP co seguinte comando (docker inspect u1 | grep "IPAddress"). Con isto, xa entramos no contedor que fará ping ao outro, neste caso "u1", co comando (docker exec -it u1 bash). Xa dentro, facemos o ping coa IP que buscamos anteriormente, que sería así (ping 172.17.0.2). Deixoume facer ping sen ningún problema.

    Se pechas as terminais, que pasa co contedor?

Os contedores deberían seguir en funcionamento porque os lancei coas iniciais (-d), co que deben funcionar en segundo plano.

    Canta memoria no disco duro ocupaches? Usa docker para calculalo.

Para saber isto é tan sinxelo como executar o comando (docker system df), con isto debería saír canto se ocupa.

    Canta RAM ocupan os contedores? Crea varios para calculalo.

Co comando (docker stats) debe verse o espazo calculado.

    Como fixeches para clonar o repositorio?

Para clonalo utilicei o comando (git clone "Ligazón do repositorio") e con ese comando deberíase clonar.

    Como engades o ficheiro readme2.md?

Ubiqueime na carpeta que clonei co comando (cd "carpeta"). Seguido, lancei unha serie de comandos: (touch readme2.md) para crealo, (nano readme2.md) para editalo, (git add readme2.md) para engadilo, e (git commit -m "practica") para crealo.

    Os pasos a seguir para subir o ficheiro que estás editando e o ficheiro readme2.md

Para subilo executamos o comando (git push) para subilo. Para ver que a rama está actualizada executamos o comando (git commit -m "traballo").

    Como comprobarías que existen diferenzas entre o teu repositorio local e o remoto?

Pódese ver co comando (git diff), que nos amosará todas as diferenzas, se existen ou non.