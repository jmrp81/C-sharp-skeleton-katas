# C-sharp-skeleton-katas

## Proyecto de consola en .Net Core para realizar diferentes katas.


# Pasos ha realizar para crear la estructura del proyecto

* Podéis seguir los siguientes o pasos o a través de la guia:

<https://docs.microsoft.com/es-es/dotnet/core/tutorials/with-visual-studio-code>

## Pasos previos

* **A:** Usando VSCode, se recomienda la instalación de la extensión de C# (Se puede usar cualquier editor o IDE) (Ver último  apartado con más extensiones recomendables): 

<https://marketplace.visualstudio.com/items?itemName=ms-dotnettools.csharp>


* **B:** Instalación del SDK de .Net Core:

<https://dotnet.microsoft.com/download/dotnet-core/thank-you/sdk-3.1.402-windows-x64-installer>

## Creando la aplicación

* **A:** Creamos una carpeta donde albergaremos el proyecto (el nombre de la carpeta sera el usado para el proyecto también)

* **B:** Desde la terminal nos situamos en el raiz de la carpeta y ejecutamos la siguiente orden:

```C
dotnet new console
```

* **C:** Crear archivo de solución para el proyecto

```C
dotnet new sln
```

* **D:** Realizado el paso anterior tendremos una aplicación de consola que mostrara en pantalla "Hello World!" para ejecutarla usamos la siguiente orden:

```C
dotnet run
```

## Input Output Console

* Leer Información desde la terminal
```C
 Console.ReadLine();
```

* Mostrar Información en la terminal
```C
 Console.WriteLine("Hello World!");
 Console.Write("Hello World!");
```

* Esperar a cerrar la consola hasta que se inserte un caracter por la terminal
```C
Console.ReadKey(true);
```

## Compilación

```C
dotnet build
```

## Depuración

* Revisar que tengamos el archivo "launch.json" en VSCode deberia estar dentro de la carpeta ".vscode" (sino si ejecutamos la depuración con F5 la suele crear):

```C
// reemplazar:
"console": "internalConsole",
// por:
"console": "integratedTerminal",
// Este cambio es para poder depurar cuando se usa  'Console'
```

* Colocamos un punto de ruptura en la linea que queramos y pulsamos F5 para iniciar la depuración.

## Creación proyecto para albergar la logica

* **A:** Creamos el proyecto con el siguiente comando desde la terminal:

```C
// -o comando para indicar la ubicación de salida
dotnet new classlib -o BaseBusinessLibrary
```

* **B:** Agregamos el anterior proyecto a la solucción con el siguiente comando:

```C
dotnet sln add BaseBusinessLibrary/BaseBusinessLibrary.csproj
```

## Pruebas Unitarias

# Descripción 
En el código se ha usado **MStest** también se puede usar con **xUnit** y **nUnit**.

* Acceso al repo de MSTest => <https://github.com/Microsoft/testfx-docs>

# Pasos

* **A:** Crear proyecto de Test:

```C
dotnet new mstest -o LibraryTest
```


* **B:** Añadir proyecto a la solución:

```C
dotnet sln add LibraryTest/LibraryTest.csproj
```

* **C:** Para poder usar los test añadimos una referencia en el proyecto de BaseBusinessLibrary

```C
dotnet add LibraryTest/LibraryTest.csproj reference BaseBusinessLibrary/BaseBusinessLibrary.csproj
```

* **D:** Para ejecutar las pruebas usamos el siguiente comando

```C
dotnet test LibraryTest/LibraryTest.csproj

// con fichero log
dotnet test LibraryTest/LibraryTest.csproj -d my.log
```

# Algunos métodos de aserción

```C
Assert.AreEqual	-> Comprueba que dos valores u objetos son iguales. 
Assert.AreSame -> Comprueba que dos variables de objeto hacen referencia al mismo objeto. 
Assert.IsFalse -> Comprueba si una condición es false. 
Assert.IsNotNull -> Comprueba que un objeto no es null. 
```

## Comandos cli .Net Core (dotnet)

<https://docs.microsoft.com/es-es/dotnet/core/tools/>


## Otras extensiones para VSCode recomendables:

* **A:** .NET Install Tool for Extension Authors --> ms-dotnettools.vscode-dotnet-runtime
* **B:** C# Extensions --> jchannon.csharpextensions