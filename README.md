# Resoluci-n-M-quina-Reverse

Iniciamos nuestra máquina vulnerable

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 175648" src="https://github.com/user-attachments/assets/9ee37446-ca75-4501-925a-6803990ec6d1" />

# Reconocimiento

Una vez nuestra máquina se encuentra iniciada procederemos hacer un escaneo de puertos utilizando la herramienta nmap, para saber los puertos que se encuentren ejecutando al igual que los servicios

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 175803" src="https://github.com/user-attachments/assets/c47d409a-3c3a-4cff-8ab7-7da39dfd3721" />

Abrimos un buscador con el numero de la maáquina a ver qe podiamos encontrar

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 181137" src="https://github.com/user-attachments/assets/f578a337-985e-481b-8f27-c84b4e85d2b6" />

Reviamos un poco y nos encontramos un login asi que procedimos a intentar ingresar haciendo inyección sql

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 181217" src="https://github.com/user-attachments/assets/488c1ef3-7713-4808-899a-3b7f9519428e" />

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 181649" src="https://github.com/user-attachments/assets/2f282e4c-cb49-4060-aeea-42ff76c6e4ea" />

Una vez hicimos varios intentos pero no logramos ingresar asi que procedimos a hacer un fuzzing utilizando a herramienta feroxbuster, pero fue poco lo que pudimos encontrar

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 181701" src="https://github.com/user-attachments/assets/0ad8b4a3-4507-4021-aac3-404fcdaaf564" />

Procedimos nuevamente a tratar de ingresar al sitio y usamos las credenciales **admin** y de password utilizamos **admin123** y obtuvimos acceso

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 183828" src="https://github.com/user-attachments/assets/9e587755-c752-47a6-936b-ee052d9b9c7e" />

Luego fuimos al apartado diagnostico de red y nos dimos cuenta que podiamos ejecutar comandos, asi que empezamos a prbar

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 183923" src="https://github.com/user-attachments/assets/0303d240-a306-496d-aa06-90d29a602e37" />

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 184408" src="https://github.com/user-attachments/assets/f6918345-7564-4545-8a98-f45b72325560" />

# Explotación

Al ver esto quisimos tratar de ingresar un comando en bash a ver si podiamos lograr que la maquina nos diera una reverse shell, asi que pusimos nuestro kali en modo escucha

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 193938" src="https://github.com/user-attachments/assets/b1fba3c3-664f-4dba-a5d7-fef614226879" />

y Procedimos a ingresar un comando que ya habiamos usado anteriormente en otras maquinas

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 190058" src="https://github.com/user-attachments/assets/c5ef6d23-7ecc-4d74-8167-8e1884e91854" />

Y obtuvimos acceso a la maquina como el usuario www-data

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 190105" src="https://github.com/user-attachments/assets/ec8637eb-d929-4585-a93e-f576efcb84d3" />

# Escalada de privilegios

Luego listamos los binarios y utilizamos el comando sudo -l el cual nos permitio ver que podiamos ingresar como root utilizando un archivo, asi que procedimos a verificsrlo

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 190252" src="https://github.com/user-attachments/assets/b1c1e7ad-ef4b-4190-94ed-7b7c63b54e8b" />

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 190626" src="https://github.com/user-attachments/assets/87ab77c7-35cf-4890-bf9e-8aef98443a9b" />

Ya dentro de la maquina procedimos a verificar si ya eramos root y efectivamente

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 192006" src="https://github.com/user-attachments/assets/ef2a4c92-dfcb-41f4-bdab-52fa8e17c77c" />


# Resultados

Procedimos a listar los archivos y luego a pasar a la carpeta **root** y encontramos la flag.txt

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 192028" src="https://github.com/user-attachments/assets/01bb8466-2738-49bc-bdf4-d859ad1e9414" />

Encontramos la flag

<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 192038" src="https://github.com/user-attachments/assets/ee9344a1-02f5-4923-9dbf-d8cca3235400" />

y de esta manera explotamos esta maquina
<img width="1920" height="1140" alt="Captura de pantalla 2026-03-28 192102" src="https://github.com/user-attachments/assets/6b403d5b-bd09-489a-9bde-c9d45c9c7b18" />

