# 📓 C++ Cheatsheet

## Índice
1. [Sintaxis Básica](#sintaxis-básica)
2. [Tipos de Datos](#tipos-de-datos)
3. [Operadores](#operadores)
4. [Estructuras de Control](#estructuras-de-control)
5. [Funciones](#funciones)
6. [Clases y Objetos](#clases-y-objetos)
7. [Manejo de Memoria](#manejo-de-memoria)
8. [STL (Standard Template Library)](#stl-standard-template-library)
9. [Ejemplos Comunes](#ejemplos-comunes)

## Sintaxis Básica

```cpp
#include <iostream> // Incluye la biblioteca estándar de entrada/salida
using namespace std; // Uso del espacio de nombres estándar

int main() {
    cout << "¡Hola, mundo!" << endl; // Imprime en consola
    return 0; // Indica que el programa terminó correctamente
}
```

## Tipos de Datos

### Tipos de Datos Básicos

```cpp
int entero = 5;          // Entero
float flotante = 5.5f;   // Flotante
double doble = 5.5;      // Doble precisión
char caracter = 'A';     // Caracter
bool booleano = true;    // Booleano
```

### Tipos de Datos Derivados

```cpp
int arreglo[5] = {1, 2, 3, 4, 5};  // Arreglo
string cadena = "Hola";            // Cadena de caracteres
```

## Operadores

### Operadores Aritméticos

```cpp
int suma = 5 + 3;
int resta = 5 - 3;
int multiplicacion = 5 * 3;
int division = 5 / 3;
int modulo = 5 % 3;
```

### Operadores Relacionales

```cpp
bool esIgual = (5 == 3);      // Igual a
bool esDiferente = (5 != 3);  // Diferente de
bool esMayor = (5 > 3);       // Mayor que
bool esMenor = (5 < 3);       // Menor que
bool esMayorIgual = (5 >= 3); // Mayor o igual que
bool esMenorIgual = (5 <= 3); // Menor o igual que
```

### Operadores Lógicos

```cpp
bool y = (true && false); // AND lógico
bool o = (true || false); // OR lógico
bool no = !true;          // NOT lógico
```

## Estructuras de Control

### If-Else

```cpp
int a = 5;
if (a > 3) {
    cout << "a es mayor que 3" << endl;
} else {
    cout << "a no es mayor que 3" << endl;
}
```

### Switch

```cpp
int x = 2;
switch (x) {
    case 1:
        cout << "x es 1" << endl;
        break;
    case 2:
        cout << "x es 2" << endl;
        break;
    default:
        cout << "x no es 1 ni 2" << endl;
}
```

### For Loop

```cpp
for (int i = 0; i < 5; i++) {
    cout << i << endl;
}
```

### While Loop

```cpp
int i = 0;
while (i < 5) {
    cout << i << endl;
    i++;
}
```

### Do-While Loop

```cpp
int i = 0;
do {
    cout << i << endl;
    i++;
} while (i < 5);
```

## Funciones

### Declaración y Definición

```cpp
int suma(int a, int b) {
    return a + b;
}

int main() {
    int resultado = suma(3, 4);
    cout << "Resultado: " << resultado << endl;
    return 0;
}
```

### Funciones con Referencias

```cpp
void incrementar(int &num) {
    num++;
}

int main() {
    int a = 5;
    incrementar(a);
    cout << "a incrementado: " << a << endl;
    return 0;
}
```

### Funciones Comunes

```cpp
#include <cmath>

double raizCuadrada = sqrt(16);  // Raíz cuadrada
double potencia = pow(2, 3);     // Potencia
double seno = sin(3.14 / 2);     // Seno
double coseno = cos(3.14 / 2);   // Coseno
double logaritmo = log(10);      // Logaritmo natural
```

## Clases y Objetos

### Definición de Clase

```cpp
class Persona {
public:
    string nombre;
    int edad;

    void mostrarInformacion() {
        cout << "Nombre: " << nombre << ", Edad: " << edad << endl;
    }
};

int main() {
    Persona p;
    p.nombre = "Juan";
    p.edad = 30;
    p.mostrarInformacion();
    return 0;
}
```

### Constructores y Destructores

```cpp
class Persona {
public:
    string nombre;
    int edad;

    Persona(string n, int e) {
        nombre = n;
        edad = e;
    }

    ~Persona() {
        cout << "Destructor llamado para " << nombre << endl;
    }
};

int main() {
    Persona p("Ana", 25);
    p.mostrarInformacion();
    return 0;
}
```

## Manejo de Memoria

### Punteros

```cpp
int main() {
    int a = 10;
    int *p = &a;
    cout << "Valor de a: " << *p << endl;
    return 0;
}
```

### Memoria Dinámica

```cpp
int main() {
    int *p = new int;
    *p = 10;
    cout << "Valor de p: " << *p << endl;
    delete p;
    return 0;
}
```

## STL (Standard Template Library)

### Vectores

```cpp
#include <vector>

int main() {
    vector<int> vec = {1, 2, 3, 4, 5};
    for (int i : vec) {
        cout << i << " ";
    }
    return 0;
}
```

### Mapas

```cpp
#include <map>

int main() {
    map<string, int> edad;
    edad["Juan"] = 30;
    edad["Ana"] = 25;

    for (auto const &par : edad) {
        cout << par.first << ": " << par.second << endl;
    }
    return 0;
}
```

## Ejemplos Comunes

### FizzBuzz

```cpp
int main() {
    for (int i = 1; i <= 100; i++) {
        if (i % 3 == 0 && i % 5 == 0) {
            cout << "FizzBuzz" << endl;
        } else if (i % 3 == 0) {
            cout << "Fizz" << endl;
        } else if (i % 5 == 0) {
            cout << "Buzz" << endl;
        } else {
            cout << i << endl;
        }
    }
    return 0;
}
```

### Número Primo

```cpp
bool esPrimo(int n) {
    if (n <= 1) return false;
    for (int i = 2; i < n; i++) {
        if (n % i == 0) return false;
    }
    return true;
}

int main() {
    int num = 29;
    if (esPrimo(num)) {
        cout << num << " es un número primo" << endl;
    } else {
        cout << num << " no es un número primo" << endl;
    }
    return 0;
}
```
