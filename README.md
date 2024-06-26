
# 📓 C++ Cheatsheet

## Índice
1. [Sintaxis Básica](#sintaxis-básica)
2. [Estructuras de Control](#estructuras-de-control)
3. [Funciones](#funciones)
4. [Clases y Objetos](#clases-y-objetos)
5. [Manejo de Memoria](#manejo-de-memoria)
6. [STL (Standard Template Library)](#stl-standard-template-library)
7. [Ejemplos Comunes](#ejemplos-comunes)

## Sintaxis Básica

```cpp
#include <iostream> // Incluye la biblioteca estándar de entrada/salida
using namespace std; // Uso del espacio de nombres estándar

int main() {
    cout << "¡Hola, mundo!" << endl; // Imprime en consola
    return 0; // Indica que el programa terminó correctamente
}
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
