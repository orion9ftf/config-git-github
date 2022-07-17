### Git y Github

1.- Instalar git (en Linux)

```shell
$ sudo apt install git
```

1.1.- Primero configuramos nuestro nombre de usuari@ también el email:

```shell
$ git config --global user.name "Tu Nombre"
$ git config --global user.email tucorreo@mail.com
```

2.- Preguntamos si efectivamente se configuró:

```shell
$ git config --list
```

3.- Nos debería devolver las configuraciones:

```shell
> user.name=Nombre
> user.email=micorreo@mail.com
```

4.- Llaves ssh:

```shell
$ ssh-keygen -t rsa -b 4096 -C tucorreo@email.com
$ enter
$ enter
```

5.- Debiera crease dos archivos:

```shell
id_rsa.pub
id_rsa
```

6.- 

```shell
$ eval "$(ssh-agent -s)"
```

Si todo funciona bien obtendremos una respuesta como esta: Agent pid número

7.- Añadir la llave al archivo:

```shell
$ ssh-add ~/.ssh/id_rsa
$ enter
```

8.- Copiar la llave en Linux:

```shell
$ sudo apt install xclip
$ xclip -sel clip < ~/.ssh/id_rsa.pub
```

9.- Copiar la llave en Mac:

```shell
$ pbcopy < ~/.ssh/id_rsa.pub
```

10.- Copiar la llave en Windows:
```shell
$ clip < ~/.ssh/id_rsa.pub
```

11.- Esto listará las llaves:

```shell
$ ls -la ~/.ssh.
```

Llevamos la llave a nuestro Repositorio de Github y la pegamos.


12.- Esto es para ver si funciona nuestra llave:

```shell
$ ssh -T git@github.com
```

Debiera devolver: `Hi username! Your’ve …`

13.- Verificar si se creó la llave:

```shell
$ ssh -v
$ ls .ssh
```

