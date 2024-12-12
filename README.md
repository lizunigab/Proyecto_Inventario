# Proyecto_Inventario
Proyecto final del curso de RESTful Web APIs con .NET Core
Consideraciones Importantes
* El proyecto está desarrollado en visual Studio Versión 2022
* Es una API REST FULL BACK END
* El enfoque que se está utilizando es CODE-FIRST (Se crea todo el código y luego se crea la base de datos a través de las migraciones)

* Conexión de Base de datos se realiza en el archivo “appsettings.json”. Se debe crear el usuario en SQL server con autentificación SQL para poder acceder a la base de datos.

* Configurar Conexión SQL, lo cual se realiza en el archivo “Program.cs”

// Add services to the container.
builder.Services.AddDbContext<ApplicatioDbContext>(opciones => opciones.UseSqlServer(builder.Configuration.GetConnectionString("ConexionSQL")));


* Migración y base de datos: Mediante la migración se crean las entidades y los campos definidos en los modelos, para lo cual se va al menú de Herramientas/ Administrador de paquetes NuGet / Consola del administraor de paquetes
Digita los siguientes comandos: 
-	Clear 
-	Add-migration  MigracionInicial (Cada vez que se requiera realizar una migración se coloca “Add-migration” + el nombre de lo que se va a migrar)
-	Posterior a ejecutar el comando se verifica que todo quedara bien y se procede a crear la base de datos mediante:
o	Update-database (esto hace el push de la base de datos) se debe hacer después de las verificaciones del resultado de la migración del paso anterior 
