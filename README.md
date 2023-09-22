#  PRIMERA PARCIAL
## HEBER EMMANUEL FIGUEROA RODRIGUEZ
## 3°B   ICI
## APUNTES DE CLASE
### CLASE 1
``` python

# funcion pura = tiene argumentos, no producen efectos secundarios, retorna siempre el mismo valor con la misma entrada.
# ejemplo funcion pura = Math.sqrt(49)-> 7

## funcion impura = no tiene argumentos, puede retornar valores distintos, 
# ejemplo funcion impura= Math.random() -> 0.05
#                         Math.random() -> 3 

while True:
    print("\nMi Calculadora")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    print("5. Salir")

    opcion = input("Selecciona una opción: ")

    if opcion >= '5':
        print("¡Hasta luego!")
        break

    num1 = float(input("Ingresa el primer número: "))
    num2 = float(input("Ingresa el segundo número: "))

    if opcion == '1':
        print("Resultado:", num1 + num2)
    elif opcion == '2':
        print("Resultado:", num1 - num2)
    elif opcion == '3':
        print("Resultado:", num1 * num2)
    elif opcion == '4':        
        if num2 != 0:
            print("Resultado: ", num1 / num2)
        else:
            print("No se puede dividir entre cero")
    else:
        print("¡Gracias por usar Mi Calculadora!") 
 
class MiCalculadora:
    def _init_(self):
        pass

    def suma(self, a, b):
        return a + b

    def resta(self, a, b):
        return a - b

    def multiplicacion(self, a, b):
        return a * b

    def division(self, a, b):
        if b != 0:
            return a / b
        else:
            return "No se puede dividir entre cero"

calculadora = MiCalculadora()

while True:
    print("\nMi Calculadora")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    print("5. Salir")

    opcion = input("Selecciona una opción: ")

    if opcion == '5':
        print("¡Gracias por usar Mi Calculadora!")
        break
    elif opcion < '1' or opcion > '5':
        print("Opción no válida")
    else:
        num1 = float(input("Ingresa el primer número: "))
        num2 = float(input("Ingresa el segundo número: "))

    if opcion == '1':
        print("Resultado:", calculadora.suma(num1, num2))
    elif opcion == '2':
        print("Resultado:", calculadora.resta(num1, num2))
    elif opcion == '3':
        print("Resultado:", calculadora.multiplicacion(num1, num2))
    elif opcion == '4':        
        if num2 != 0:
            print("Resultado:", calculadora.division(num1, num2))
        else:
            print("No se puede dividir entre cero") 

def suma(a, b):
    return a + b

def resta(a, b):
    return a - b

def multiplicacion(a, b):
    return a * b

def division(a, b):
    return a / b

def mi_calculadora(opcion, num1, num2):
    if opcion == '1':
        return suma(num1, num2)
    elif opcion == '2':
        return resta(num1, num2)
    elif opcion == '3':
        return multiplicacion(num1, num2)
    elif opcion == '4' and num2 != 0:
        return division(num1, num2)
    else:
        return "Opción no válida"

while True:
    print("\nMi Calculadora")
    print("1. Suma")
    print("2. Resta")
    print("3. Multiplicación")
    print("4. División")
    print("5. Salir")

    opcion = input("Selecciona una opción: ")

    if opcion == '5':
        print("¡Gracias por usar Mi Calculadora!")
        break
    elif opcion < '1' or opcion > '5':
        print("Opción no válida")
    else:
        num1 = float(input("Ingresa el primer número: "))
        num2 = float(input("Ingresa el segundo número: "))
        resultado = mi_calculadora(opcion, num1, num2)
        print("Resultado:", resultado)
```

### LISTAS
```py

# Listas (se conocen como conecciones)
# datos mutables y inmutables

def suma(a,b):
    return a+b

def resta(a,b):
    return a-b

def multiplicacion(a,b):
    return a*b

def division(a,b):
    return a/b

operaciones=[suma,resta,multiplicacion,division]
print(operaciones[0](1,2))
print(operaciones[1](1,2))
print(operaciones[2](1,2))
print(operaciones[3](1,2))
for operacion in operaciones:
    print(operacion(1,2)) 
lista=[1,2,3,4,5,True,1.2,'hola',[1,2,3]]

# la lista es indexable (todos los elementos tienen un indice)
# la lista es mutable porque se puden modificar los valores
lista[8]
lista[8]='heber'
print(lista)

lista = [3,6,7,40,34,67,89]
max(lista)
min(lista)
sum(lista)
sorted(lista)
lista.sort(reverse=True)
lista
# metodo, hace las cosas pero no las regresa(no las imprime)

#slices
print(lista)
print(lista[:]) # es lo mismo. los dos puntos indican el inicio y el final

print(lista[0:]) # tambien es lo mismo
print(lista[-1:-3]) 
# si contamos los elementos de la lista alrevez se empiezan con-1
print(lista[-1:1])
# cuando una funcion no tiene un retorno, retorna None
def suma(a,b):
    pass

print(suma(3,4))

def funciones(a,b):
    return [a+b,a-b,a*b,a/b]
respuesta=funciones(3,4)
print(respuesta)
w,x,y,z = funciones(3,4)
print(w)
res_suma,_,_,_ = funciones(5,4)
res_suma
```

### TUPLE / TUPLA
```python

# tuple (se puede meter cualquieer tipo de dato), es inmutable(no se puede cambiar), pero si le pudes agregar valores

tupla_funciones=(suma,resta,multiplicacion,division)
print(tupla_funciones[1](5,4))
tupla=(1,2,3,4,5,True,1.2,'hola',[1,2,3])

# a la tupla se le puede agregar solamente de 2 elementos en adelante
tupla=(1,2,3,4,5,True,1.2,'hola',[1,2,3])
tupla.__add__((10,'holaaaa'))

print(tuple(numeros)) # tupla con parentesis
print(list(numeros)) # lista con corchetes
```

### RANGE
```python

numeros=range(5,10) # del 5 al 9
print(numeros)

for i in numeros:
    print(i,end="-") # ,end="" (es para imprimir de manera lineal)
    
 
numeros_pares=range(2,11,2)
for par in numeros_pares:
    print(par,end=" ")
 
for item in range(2,11,2):
    print(item,end=" ")
    
    
def suma(a: int, b:int) -> int: # salida 1 entero
    return a+b

def operacion(a:int, b:int) -> (int,int): # salida 2 enteros
    return(a+b,a-b)

(a,b)=operacion(5,6)
a,b=operacion(5,6)
print(a,b)
```

### SET
```python

# set conjuntos (lleva parentesis y se puede poner cualquier tipo de datos pero al momento de imprimir no acepta valores repetidos)
mi_set={1,2,3,3,3,2,2,1,1,1}
mi_set

data=[1,2,1,3,4,5,2,1,3,4,6,9,7,8]
list(set(data)) #  el set ordena los valores

data2= {1,56,57,58}
mi_set.union(data2)
```

### DICCIONARIO
```python

# diccionarios
mi_dict = {'llave': 'valor'}
mi_dict['llave']  # 'valor'
mi_dict.keys() # dict_keys(['llave'])
mi_dict.values()  # dict_values(['valor']) 
```

### OPERADORES LOGICOS 
```python

print(True and False)
print(True or False)
print(not False)
# SALIDA: FALSE, TRUE, TRUE

True
False
if 5 > 4:
    print(True)
print(5>7)
 
received: bool = False
not received
# SALIDA: TRUE, FALSE

nombre: str = 'hugo'
print(nombre)
print(type(nombre))
nombre.capitalize()
nombre.upper()

num: int = 10
pi: float = 3.14
es_alumno: bool = True
name: str = 'Hugo'
print(f'{num}--{pi}--{es_alumno}--{name.upper()}')

```

### OPERADORES ARITMETICOS
``` python

print(5+4)
print(5-4)
print(5*4)
print(5/4)
print(5//4) # division entera
print(5%4) # modulo o residuo
print(5**4) # x a la y
```

### CONDICIONALES
```python

n1: int = 30
n2: int = 20
if n1>n2:
    print(f'{n1} > {n2}')

n1=10
if n1>n2:
    print(f'{n1} > {n2}')
else:
    print(f'{n2} > {n1}')


edad: int = 18
if edad > 18:
    print('mayor de edad')
elif edad == 18:
    print('acabas de llegar a la mayoria de edad')
else:
    print('eres menor de edad perra')
```

### JUNTAR ARCHIVOS
```python

# main(entry point=punto de entrada)
# un lenguaje 
""" import libreria.suma as lib
import libreria.resta as lib
from libreria import suma,resta """
# import libreria as lib

if __name__ == "__main__":
    print(lib.suma(7,8))
    print(lib.resta(8,5))

def resta(a:int,b:int) ->int:
    return a-b
if __name__ == "__main__":
    print(resta(8,5))
    
# hins(pistas): se le conoce asi a a asignacion en este caso es el entero


def suma1(a: int ,b: int)->int: #salida entera
    return a + b

def suma2(a:float,b:float)->float:
    return a+b
def suma(a:int|float,b:int|float)->int|float:
    return a+b

if __name__ == "__main__": # equivalente de un entry point en python
    print(suma1(5,6))
    print(suma2(4.5,4.5))
    print(suma(5,5.5))

``` 

### CLASES
```python

# funcion decorador se utiliza para modificar el comportamiento de otra funcion

from dataclasses import dataclass

@dataclass #decorators
class User:
    id: str
    name: str
    age: int

    def show_data(self):
        return f"ID: {self.id}\nNOMBRE: {self.name}\nAÑO: {self.age}"

if __name__ == "__main__":
    usuario1 = User("1","EMMANUEL",25)
    usuario2 = User("2","HEBER",25)
    usuario3 = User("3","FIGUEROA",25)
    usuario4 = User("4","RODRIGUEZ",25)
    usuarios = [usuario1,usuario2,usuario3,usuario4]
    for usuario in usuarios:
        print(usuario.show_data())
```

### STREAMLIT

``` python

import streamlit as st
st.sidebar.title("CALCULADORA ICI")

def pedir_valores():
    name = st.text_input("NOMBRE: ")
    n1 = st.number_input("NUMERO 1")
    n2 = st.number_input("NUMERO 2")

    if st.button("SUMAR"):
        st.success(f"HOLA {name}")
        st.write(f"{n1} + {n2} = {n1+n2}")
    elif st.button("RESTAR"):
        st.success(f"HOLA {name}")
        st.write(f"{n1} - {n2} = {n1-n2}")
    

opcion = st.sidebar.selectbox("opciones:",[
    "SUMA","RESTA","MULTIPLICACION","DIVISION","ACERCA DE"
])

match opcion:
    case "SUMA":
        st.write("ESTA ES LA SUMA DE...")
        pedir_valores()
    case "RESTA":
        st.write("ESTA ES LA RESTA DE...")
        pedir_valores()
    case "MULTIPLICACION":
        st.write("ESTA ES LA MULTIPLICACION DE...")
    case "DIVISION":
        st.write("ESTA ES LA DIVISION DE...")
    case "ACERCA DE":
        st.write("DERECHOS RESERVADOS")
        st.write("UCOL-FIME-ICI")
```
