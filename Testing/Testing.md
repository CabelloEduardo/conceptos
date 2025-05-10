# Testing de Software: Fundamentos

## 🧠 ¿Qué es el testing de software?

El *testing* es el proceso de **verificar que tu programa hace lo que debería hacer**. Es una forma sistemática de comprobar que el código:

* funciona correctamente,
* maneja errores,
* y se mantiene estable a pesar de cambios.

---

## 🔍 ¿Por qué es tan importante?

Sin testing puedes tener:

* Bugs ocultos (que aparecen sólo en ciertos casos).
* Cambios que rompen funcionalidades sin que te des cuenta.
* Programas difíciles de mantener y escalar.

Con testing tienes:

✅ Confianza en tu código
✅ Documentación viviente (los tests explican el comportamiento esperado)
✅ Mayor velocidad al hacer cambios sin miedo

---

## 🧩 Tipos fundamentales de testing

1. ### 🔹 **Test unitario** (*Unit Test*)

   Prueba una **unidad pequeña** del código, como una función o método individual.

   > Ejemplo: probar que `sumar(2, 3)` devuelve `5`.

2. ### 🔹 **Test de integración**

   Prueba cómo **varias partes del sistema interactúan entre sí**.

   > Ejemplo: probar que una función que llama a una API y guarda datos en base de datos lo hace correctamente.

3. ### 🔹 **Test de sistema o end-to-end**

   Prueba el sistema **como lo usaría un usuario real**, de punta a punta.

   > Ejemplo: simular un usuario que llena un formulario web y verifica si se muestra un mensaje de éxito.

4. ### 🔹 **Test manual vs. automatizado**

   * *Manual*: tú haces clics o ingresas datos.
   * *Automatizado*: el código prueba al código (con librerías como `pytest`, `unittest`, `Jest`, `JUnit`, etc.)

---

## 🛠️ ¿Cómo luce un test unitario en la práctica?

Supón que tienes esta función en cualquier lenguaje:

```python
def sumar(a, b):
    return a + b
```

Un test unitario verifica su comportamiento esperado:

```python
def test_sumar():
    assert sumar(2, 3) == 5
```

> “Assert” significa: **esto debería ser cierto**. Si no lo es, el test falla.

---

## 🧪 ¿Qué se debe testear?

1. **Comportamiento esperado**

   * ¿Devuelve lo correcto?
   * ¿Maneja bien entradas inválidas?

2. **Límites y casos extremos**

   * ¿Qué pasa si divides entre cero?
   * ¿Qué pasa si ingresas un string en vez de un número?

3. **Errores esperados**

   * ¿Lanza la excepción correcta cuando algo va mal?

---

## 🧠 Buenas prácticas generales (independientes del lenguaje)

* 🔄 **Automatiza todo lo que puedas**
  Evita tener que testear manualmente cada cambio.

* 🧱 **Una prueba = un caso específico**
  Pequeñas, claras, y con un solo propósito.

* 🧹 **Aísla tus pruebas**
  No deben depender de pruebas anteriores ni de un orden de ejecución.

* 📎 **Nómbralas bien**
  Que el nombre explique qué están probando: `test_usuario_sin_nombre_no_es_valido`.

* 💥 **Haz fallar las pruebas primero (TDD)**
  Esto asegura que tu prueba es válida.

---

## 📘 Ejemplo simple multi-lenguaje: probar suma

### Python (pytest):

```python
def test_sumar():
    assert sumar(1, 2) == 3
```

### JavaScript (Jest):

```javascript
test('sumar 1 + 2 es igual a 3', () => {
  expect(sumar(1, 2)).toBe(3);
});
```

### Java (JUnit):

```java
@Test
void testSumar() {
    assertEquals(3, MiClase.sumar(1, 2));
}
```

---

## ✅ Qué ganas entendiendo testing como concepto

* Puedes leer código de pruebas en cualquier lenguaje.
* Puedes decidir si necesitas tests unitarios, de integración o de sistema.
* Puedes mejorar la calidad del software sin depender de herramientas específicas.
* Puedes construir software más confiable, profesional y sostenible.

