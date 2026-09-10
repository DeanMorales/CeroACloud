# mi primera app de IA con Party Rock sin codigo.

## buen y mal prompt

> hace referencia a cuando damos un resultado no optimo, sera generico y no tendras exactitud.
>> un buen prompt siempre debe terer un resultado especifico, en un personaje, justificado y personalizado.

¿ Cambio le modelo?

debemos cambiar nuestro prompt

## Prompt Engineering

diseñar instrucciones clara para conseguir el resultado especifico que buscamos en un modelo generativo.

1. vamos a partyRock.

link: 

[partyrock]("https://partyrock.aws/home")

las apps de party rock estan hechas de widgets, por lo que tendremos que ir construyendo de forma facil. 

- en primera instancia, debemos capturar nuestras variables de User Input.

- nombre 

### construyendo la app

#### El prompt 
```
Elige el pokemon que mejor represente a esta persona.

```

**El Contexto:**


**Prompt por capas**

1. Rol "eres un mistico adivino pokemon"
2. Contxto "
3. task "elije cual es el pokemon que represente mejor a esta persona."

#### Constraints

reglas estrictas para limitar la generacion
"mantenlo en menos de 200 palabras.
"usa u ntono divertido y jugeton."
"hazlo en idioma español latinoamericano"

#### Chaining en la interfaz

en partyrock encadenar widgets es tan facil como escribir un arroba @ esto despliega un meno con todos los widgets. 


#### Auditoria 

**Generado =/ Correcto**

checklist sistematico:

1. relevancia
2. constraints
3. 

#### Grounding (anclar a una fuente externa)
anclar las respuestas generadas a una fuente de verdad externa para que tener 
