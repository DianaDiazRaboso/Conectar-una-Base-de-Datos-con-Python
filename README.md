# Conectar-una-Base-de-Datos-con-Python
Código Python para acceder a una base de datos. Y así poder hacer una consulta en lenguaje SQL. En primer lugar, debemos instalar el conector mysql-connector-python, un driver para comunicarse con servidores MySQL.

pip install mysql-connector-python

Seguidamente, realizamos el mismo proceso con PyMySQL, otro paquete para la interacción con bases de datos MySQL. Y, una vez instalado, lo importamos.

import mysql.connector pip install pymysql

Teniendo ya los paquetes necesarios, nos conectamos a la base de datos. Para ello, creamos una variable llamada “myConnetion” y mediante PyMySQL, almacenamos la ruta de la base de datos, el usuario, la contraseña y el nombre de la base de datos. En definitiva la información necesaria para establecer la conexión con la base de datos.

import pymysql myConnection = pymysql.connect( host='route', user= 'user', passwd='password', db='db' )
cur = myConnection.cursor() 
cur.execute( "SELECT* FROM TTable" ) for first_name in cur.fetchall()
print (first_name) 
myConnection.close()
