# Teclado remoto del Apple Watch: el texto pegado llega vacío (watchOS 27)

[Read in English](README.md)

> **Estado: abierto.** Reproducido en watchOS 27.2. Última actualización: 2026-10-01.

Cuando un campo de texto del Apple Watch se llena con el teclado remoto del iPhone, el texto que **pegas** en el iPhone se ve bien en el iPhone, pero llega **vacío** al reloj. Escribir el mismo texto letra por letra funciona.

Pasa en campos seguros (contraseñas) y en campos de texto normales, así que no parece una restricción de los campos de contraseña.

## Cómo reproducirlo

1. En el reloj, abre un campo de texto (probado con uno de contraseña y uno normal).
2. Abre el teclado en el iPhone cuando te lo pida.
3. Copia un texto de prueba corto (por ejemplo `test12345`) desde otra app.
4. Pégalo en el campo del iPhone. El iPhone muestra el texto.
5. Confirma en el reloj.

**Esperado:** el reloj recibe el texto pegado.
**Real:** el campo del reloj recibe la entrada vacía.

## Qué probé

| Prueba | Resultado |
|---|---|
| Escribir el texto a mano en el iPhone | llega al reloj |
| Pegar en un campo seguro (contraseña) | llega vacío |
| Pegar en un campo de texto normal | llega vacío |

El canal de datos funciona, porque lo escrito a mano llega. La falla es solo del texto pegado.

## Entorno

| | |
|---|---|
| iPhone | iPhone 15 Pro Max (`iPhone16,2`), iOS 27.0 |
| Reloj | Apple Watch Ultra 2 (`Watch7,5`), watchOS 27.2 (`24S5091f`) |
| Mac | MacBook Pro (`MacBookPro17,1`, Apple M1), macOS 27.2 |

## Solución provisional

Escribe el texto a mano en lugar de pegarlo.

## Relacionado

- [watchos27-pairing-bug](https://github.com/kisnner26/watchos27-pairing-bug): otro problema en el mismo reloj, que nunca se reconecta después de emparejarse bien.

## Notas

Es un reporte independiente desde una sola configuración de dispositivos. Si lo puedes reproducir (o no), abre un issue con tus versiones de dispositivo y sistema.

Licencia MIT. Ver [LICENSE](LICENSE).
