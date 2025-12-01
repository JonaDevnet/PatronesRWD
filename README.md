# 🚀 Introducción a C# Backend

Este repositorio contiene ejemplos y prácticas sobre conceptos fundamentales y avanzados para el desarrollo backend con C# y .NET. A continuación, se detalla una breve introducción teórica de los temas abordados.

## 📚 Conceptos Clave

### 1. 📦 Genéricos (Generics)
Los genéricos nos permiten escribir clases y métodos flexibles que pueden trabajar con cualquier tipo de dato, manteniendo la seguridad de tipos (*type safety*) y evitando el "boxing/unboxing". Es como crear una plantilla que se adapta al tipo de dato que le indiquemos.

```csharp
// Ejemplo: Una caja que puede guardar cualquier tipo de dato T
public class Caja<T>
{
    private T contenido;
    public void Guardar(T item) => contenido = item;
}

var cajaEnteros = new Caja<int>();
var cajaTextos = new Caja<string>();
```

### 2. 🔌 Interfaces
Una interfaz define un "contrato". Especifica **qué** debe hacer una clase (sus métodos y propiedades), pero no **cómo** debe hacerlo. Son fundamentales para la inyección de dependencias y el desacoplamiento del código.

```csharp
public interface IRepositorio
{
    void Guardar();
}

public class UsuarioRepo : IRepositorio
{
    public void Guardar() { /* Lógica para guardar usuario */ }
}
```

### 3. 📄 JSON (JavaScript Object Notation)
Es el formato estándar ligero para el intercambio de datos. En C#, utilizamos bibliotecas como `System.Text.Json` para serializar (convertir objetos de C# a texto JSON) y deserializar (convertir texto JSON a objetos C#).

```JSON
{
  "id": 1,
  "nombre": "Juan",
  "esProgramador": true
}
```

### 4. 🧩 Programación Funcional en C#
Aunque C# es orientado a objetos, soporta características del paradigma funcional. Esto implica tratar a las funciones como ciudadanos de primera clase (podemos pasar funciones como parámetros), favorecer la inmutabilidad y evitar efectos secundarios para hacer el código más predecible.

### 5. λ Expresiones Lambda
Son funciones anónimas (sin nombre) que se usan para crear delegados o árboles de expresión de forma concisa. Se definen con el operador `=>` (se lee "tiende a" o "va hacia").

"
```csharp
(input) => expresión
Func<int, int> cuadrado = x => x * x;
Console.WriteLine(cuadrado(5)); // Imprime 25
```

### 6. 🔍 LINQ (Language Integrated Query)
Es un conjunto de tecnologías que permiten realizar consultas directamente sobre colecciones de datos (arrays, listas, XML, bases de datos) usando una sintaxis uniforme similar a SQL, pero integrada en C#.

```csharp
int[] numeros = { 1, 2, 3, 4, 5, 6 };

// Filtrar números pares y ordenarlos
var pares = numeros.Where(n => n % 2 == 0).OrderByDescending(n => n);
// Resultado: 6, 4, 2
```

---
*✨ Repositorio creado con fines educativos.*
