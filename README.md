# Laboratorio 2 - Haskell

## 📌 Descripción  
Este laboratorio tiene como objetivo que los estudiantes fortalezcan sus conocimientos relacionados con **Haskell** y la programación funcional.

---

## 🛠️ Instrucciones Generales  

1. **Fork del repositorio**  
   - Realice un **fork** de este repositorio en su cuenta personal de GitHub.  
   - No realice cambios directamente sobre el repositorio original.  

2. **Estructura de carpetas**  
   - Dentro de su fork, cree una carpeta llamada **`lab02/`**.  
   - Cada ejercicio debe resolverse en un archivo **independiente** con el siguiente formato:  
     ```
     lab02/ejercicio01.hs
     lab02/ejercicio02.hs
     ...
     ```  

3. **Resolución de ejercicios**  
   - Desarrolle los programas en el entorno de programacion indicado en clase.  
   - Una vez finalizados, copie el código a los archivos `.hs` correspondientes en su repositorio.  
   - Cada archivo debe contener:
     - La implementación de su solución.  

4. **Buenas prácticas**  
   - Use **nombres de predicados claros y significativos**.
---

## 🚀 Entrega  

- **Plazo**: La entrega debe realizarse a mas tardar el proximo lunes, se habilitara una tarea en Moodle para adjuntar el link del repositorio.

---

## ✅ Criterios de Evaluación  

1. **Correctitud de las soluciones** (funcionalidad de los predicados).  
2. **Cumplimiento de la estructura solicitada** (archivos independientes en `lab01/`).  
3. **Claridad en la codificación** (nombres, comentarios y legibilidad).  
4. **Uso adecuado de variables** (incluyendo variables anónimas donde corresponda).  

---

## 💡 Recomendaciones  

- Revise la documentación oficial de Haskell: [Haskell Documentation](https://www.haskell.org/documentation/).  
- Antes de subir sus archivos, **ejecute y verifique** cada consulta en el compilador en linea.  
- Mantenga su repositorio organizado y actualizado.

---

## Ejercicio 1 - Manejo de listas

1. Definir las siguientes funciones usando recursión.

```  
Retorna la longitud de una lista
miLength :: [a] -> Int

Retorna el último elemento de una lista
miLast :: [a] -> a

Duplica cada elemento de una lista de números
duplicar :: [Int] -> [Int]

Eliminar los elementos pares de una lista
eliminarPares :: [Int] -> [Int]
 ```

2. Define estas mismas funciones pero ahora usando funciones de orden superior como map y filter


---

## Ejercicio 2 - Listas por comprensión

1. Usa comprensión de listas para:

 ```
a. Obtener los cuadrados de los primeros 10 números.

b. Filtrar los divisibles por 3 entre 1 y 30.

c. Generar una lista de pares (x, y) donde x < y y ambos estén en [1..5].

 ```

2. Define una función que devuelva los divisores de un número (usando lista por comprensión):
    ```
     divisores :: Int -> [Int]
     ```

3. Define la función divisoresPropios, crea una función que determine si un número es perfecto (suma de sus divisores propios = número):

  ```
  esPerfecto :: Int -> Bool
  ```

---

## Ejercicio 3 - Funciones de orden superior


1. Reescribe las siguientes funciones sin recursión explícita, usando funciones de orden superior:
   
    ```
    a. Suma de todos los elementos
    sumaLista :: [Int] -> Int
    
    b. Contar cuántos elementos son mayores que 10
    mayoresQue10 :: [Int] -> Int
    
    c. Calcular el producto de una lista de números
    productoLista :: [Int] -> Int

    d. Convierte una lista de grados Celsius a Fahrenheit
    celsiusAFahrenheit :: [Double] -> [Double]

    e. Suma 5 a cada número impar de una lista y deja igual los pares.
    ajustarImpares :: [Int] -> [Int]
    ```
    
2. Define las siguientes funciones usando filter
   ```
   a. Devuelve solo los nombres con más de 5 letras.
   nombresLargos :: [String] -> [String]

   b. Filtra los números negativos de una lista.
   soloNegativos :: [Int] -> [Int]

   c. De una lista de edades, obtiene las que estén entre 18 y 25 años.
   edadesUniversitarios :: [Int] -> [Int]
   ```

3. Define las siguientes funciones usando filter y map
   ```
   a. Dada una lista de precios, sumar IVA (19%) solo a los valores mayores o iguales a 1000.
   agregarIVA :: [Double] -> [Double]

   b. De una lista de palabras, obtener solo las que comienzan con vocal y devolver su longitud.
   longitudesVocales :: [String] -> [Int]

   c. Dada una lista de números, devuelve los cuadrados de los pares.
   cuadradosPares :: [Int] -> [Int]
   ```

4. Define las siguientes funciones usando any o all
   ```
   a. Verifica si algún número en la lista es negativo.
   hayNegativo :: [Int] -> Bool

   b. Verifica si todos los números son pares.
   todosPares :: [Int] -> Bool

   c. Comprueba si todos los nombres empiezan con mayúscula.
   import Data.Char (isUpper)
   nombresCorrectos :: [String] -> Bool
   ```

5. Define las siguientes funciones usando takeWhile o dropWhile
   ```
   a.De una lista ordenada, toma los elementos menores que 100.
   menoresQue100 :: [Int] -> [Int]

   b. Quita los ceros iniciales de una lista.
   sinCerosIniciales :: [Int] -> [Int]
   ```
---

## Ejercicio 4 - Funciones que reciben y retornan funciones

1. Define una funcion que recibe una función que transforma una lectura (por ejemplo, conversión de grados Celsius a Fahrenheit, o aplicar calibración),
y una lista de lecturas de sensores.

   ```
   procesarLecturas :: (Double -> Double) -> [Double] -> [Double]
   procesarLecturas f lecturas = map f lecturas
   ```

2. Define una función que retorne un filtro personalizado:
    ```
   crearFiltro :: (a -> Bool) -> ([a] -> [a])

   Ejemplo:
   
   soloPares = crearFiltro even
   soloPares [1..10] == [2,4,6,8,10]
    ```

3. Crea una función que genera “verificadores” de rangos.
    ```
    enRango :: Int -> Int -> (Int -> Bool)
    enRango min max = (\x -> x >= min && x <= max)

    Ejemplo:
    
    entre5y10 = enRango 5 10
    entre5y10 7   -- True
    ```

4. Genera una función que eleva a una potencia dada.

   ```
   potenciador :: Int -> (Int -> Int)
   potenciador n = (\x -> x ^ n)
   ```

## Retrospectiva
1. ¿Cuál fue el tiempo total invertido en el laboratorio por cada uno de ustedes? (Horas/Hombre)
2. ¿Cuál es el estado actual del laboratorio? ¿Por qué?
3. ¿Cuál consideran fue el mayor logro? ¿Por qué?
4. ¿Cuál consideran que fue el mayor problema técnico? ¿Qué hicieron para resolverlo?
5. ¿Qué hicieron bien como equipo? ¿Qué se comprometen a hacer para mejorar los resultados?
6. ¿Qué referencias usaron? ¿Cuál fue la más útil? Incluyan citas con estándares adecuados.
