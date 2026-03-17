**Integrantes:**

-Andrea Melissa Torres Batres

-Alejandra María Baires Campos

**Sistema de Gestión Veterinaria (MagicPet)🐾**

**Situación problemática**

En muchas clínicas veterinarias pequeñas, especialmente en el entorno local, la gestión de atención de mascotas se realiza de forma manual, utilizando cuadernos o registros físicos. Esta situación genera problemas como la pérdida de información de las mascotas, dificultad para registrar citas, errores en los datos ingresados y desorganización en la atención diaria. Por ejemplo, una veterinaria de barrio atiende varias mascotas al día, pero al no contar con un sistema digital, no registra de forma ordenada el nombre de la mascota, su dueño, el tipo de servicio y el estado de atención, lo que provoca retrasos y confusión.

**Solución mediante la página web**

Se propone el desarrollo de una aplicación web utilizando Vue.js que permita registrar y gestionar la información de las mascotas de forma digital.

**El sistema permitirá:**

-Registrar mascotas con nombre, dueño y tipo de servicio

-Validar que los campos no estén vacíos

-Mostrar una lista de mascotas registradas

-Cambiar el estado de atención (Pendiente / Atendido)

-Eliminar registros

Con estas funciones, el sistema resuelve el problema al mejorar la organización, reducir errores y agilizar la atención dentro de la veterinaria.

**Sector al que va dirigido**

**La solución está dirigida a:**

-Clínicas veterinarias pequeñas y medianas

-Veterinarias independientes

-Negocios de atención animal

**Respuestas de preguntas:**

**-Explique con sus propias palabras qué es Vue.js y cuál es su función dentro de la
página web desarrollada:**

Vue.js es un framework de JavaScript que permite crear páginas web interactivas de forma más sencilla.
En mi proyecto, lo utilicé para manejar toda la lógica del sistema veterinario, como registrar mascotas, mostrar la lista en tiempo real y actualizar la información sin necesidad de recargar la página gracias a Vue, la aplicación responde automáticamente a las acciones del usuario, lo que la hace más dinámica y fácil de usar.

**-Describa qué variables reactivas utilizó en su aplicación y cuál es la función de
cada una dentro del sistema.**

En mi aplicación utilicé las siguientes variables reactivas:

-nombreMascota: guarda el nombre de la mascota ingresada en el formulario

-cliente: almacena el nombre del dueño de la mascota

-servicio: guarda el tipo de servicio seleccionado (consulta, vacuna o cirugía)

-error: indica si hay un error en el formulario (por ejemplo, campos vacíos)

-mensajeError: muestra el mensaje de error al usuario

-mascotas: es un arreglo donde se guardan todas las mascotas registradas junto con sus datos

Estas variables son importantes porque permiten que la información se actualice automáticamente en la pantalla cada vez que el usuario realiza una acción

**-Explique la diferencia entre las siguientes directivas utilizadas en su proyecto: v-bind y v-model**

La diferencia es que:

**v-model** lo utilicé en los inputs y el select para capturar lo que el usuario escribe o selecciona, por ejemplo en el nombre de la mascota, cliente y servicio.

**v-bind** lo utilicé de forma abreviada con : para asignar clases dinámicas, como en el estado de la mascota (:class), donde cambia el color dependiendo si está "Atendido" o "Pendiente".

**-Mencione al menos un ejemplo de evento utilizado dentro de su aplicación.**

En mi aplicación utilicé varios eventos, por ejemplo:

**@submit.prevent="agregarMascota":** se ejecuta cuando se envía el formulario y evita que la página se recargue

**@click="cambiarEstado(index)":** cambia el estado de la mascota entre pendiente y atendido

**@click="eliminarMascota(index)":** elimina una mascota de la lista

Estos eventos permiten que el usuario interactúe con el sistema de forma sencilla.

**-Explique para qué utilizó la directiva v-for dentro de su aplicación.**

Utilicé v-for para recorrer el arreglo mascotas y mostrar cada registro dentro de la tabla.
Debido a esto, cada vez que agrego una mascota se muestra automáticamente en la lista sin tener que escribir código adicional.

**-Describa en qué situación utilizó v-if y qué problema resuelve dentro de su
interfaz.**

Utilicé v-if para mostrar el mensaje de error cuando los campos están vacíos.
Por ejemplo, si el usuario intenta agregar una mascota sin completar los datos, aparece el mensaje **"Todos los campos son obligatorios".**
Esto ayuda a evitar confusión y le indica al usuario qué debe corregir antes de continuar.

**-Explique cómo se realiza la validación de datos en su aplicación y por qué es
importante validar la información ingresada por el usuario.**

La validación la realicé dentro del método agregarMascota(), donde verifico que los campos no estén vacíos usando .trim().
Si algún campo está vacío, activo la variable error y muestro un mensaje al usuario.

**Esto es importante porque:**

-Evita que se guarden datos incompletos

-Mejora la calidad de la información

-Hace que el sistema sea más confiable

-Mejora la experiencia del usuario











