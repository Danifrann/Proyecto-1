# Proyecto1

Este es un proyecto que realiza cálculos para una tienda online.

## Descripción

El proyecto incluye una función `calcularDescuento` para calcular descuentos y un algoritmo para gestionar la compra de productos en una tienda.

## Código PSeInt

El algoritmo muestra un menú que permite al usuario ingresar los datos requeridos en el enunciado y ejecuta
las operaciones hasta que el usuario seleccione la opción "Salir" (bucle)

Escribí todo el algoritmo sin funciones, pero luego agregué la función `calcularDescuento` ya que era requerido por la pauta.

```plaintext
Funcion descuento <- calcularDescuento ( precioOriginal, tieneCodigoDescuento )
    descuento = 0;
    si (tieneCodigoDescuento == "SI") Entonces
        descuento = precioOriginal * 0.10;
    FinSi
Fin Funcion

Algoritmo Proyecto1
    
    Dimension productos[3]
    Dimension precios[3]
    Dimension pesos[3]
    
    Definir indiceProductoSeleccionado Como Entero
    Definir tieneCodigoDescuento Como Caracter;
    Definir precioOriginal Como Real;
    Definir precioActual Como Real;
    Definir descuento Como Real;
    Definir impuestos Como Real;
    Definir descuentoCantidad Como Real;
    Definir pesoProducto Como Real;
    Definir porcentajeDeDescuentoPorCantidad Como Real;
    porcentajeDeDescuentoPorCantidad = 0.05;
    Definir porcentajeDeImpuesto Como Real
    porcentajeDeImpuesto = 0.12;
    Definir porcentajeDecuento Como Real;
    porcentajeDecuento = 0.1;
    Definir costofinalProducto Como Real;
    Definir costoFijo Como Real;
    costoFijo = 10;
    
    // Definiendo los productos
    productos[1] = "Zapato modelo A";
    productos[2] = "Zapato modelo B";
    productos[3] = "Zapato modelo c";
    
    // representan los precios de los productos
    precios[1] = 100;
    precios[2] = 200;
    precios[3] = 300;
    
    // representan los kilos de peso de los productos
    pesos[1] = 1.5;
    pesos[2] = 3;
    pesos[3] = 4;
    
    Escribir "Ingrese el indice del producto que quiere comprar"
    Escribir "1. ",productos[1]
    Escribir "2. ",productos[2]
    Escribir "3. ",productos[3]
    Escribir "4. Salir"
    Leer indiceProductoSeleccionado
    Mientras indiceProductoSeleccionado <> 4 Hacer
        // Obtener el producto seleccionado
        precioOriginal = precios[indiceProductoSeleccionado]
        
        // Preguntando al usuario si tiene un descuento
        Escribir "Tiene un cupón de descuento?"
        Escribir "1. SI";
        Escribir "2. NO";
        Leer tieneCodigoDescuento
        
        // Evaluando descuento
        descuento = calcularDescuento(precioOriginal, tieneCodigoDescuento);
        precioActual = precioOriginal - descuento;
        
        // Evaluando impuestos
        impuestos = precioActual * porcentajeDeImpuesto;
        precioActual = precioActual + impuestos;
        
        // Evaluando descuento por cantidad
        Escribir "Ingrese la cantidad de productos"
        Leer cantidadProductos;
        si (cantidadProductos >= 2) Entonces
            descuentoCantidad = precioActual * porcentajeDeDescuentoPorCantidad;
        FinSi
        precioActual = precioActual - descuentoCantidad
        
        // evaluando costo envio
        pesoProducto = pesos[indiceProductoSeleccionado] * cantidadProductos;
        costoEnvio = costoFijo + (2 * pesoProducto);
        
        // Mostrando resultado final
        costofinalProducto = (precioActual * cantidadProductos) + costoEnvio;
        Escribir "El costo total del producto es: ", costofinalProducto;
        Escribir "Descuento: ", descuento
        Escribir "Impuestos: ", impuestos
        Escribir "Descuento por cantidad: ", descuentoCantidad
        Escribir "Valor envio: ", costoEnvio
        
        Escribir "-----------------------------"
        Escribir "Ingrese el indice del producto que quiere comprar"
        Escribir "1. ",productos[1]
        Escribir "2. ",productos[2]
        Escribir "3. ",productos[3]
        Escribir "4. Salir"
        Leer indiceProductoSeleccionado
    Fin Mientras
    
    Escribir "Gracias por comprar en DanielaShop"
    
FinAlgoritmo
