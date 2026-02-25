# Apuntes_T.A.P

# Proyecto – Interfaz Gráfica de Usuario

## Unidad I 

Alumno: Luis Angel  Rodriguez Flores

Materia: TOPICOS AVANZADOS DE PROGRAMACION


---

# Introducción

En este repositorio se presenta el desarrollo de los temas correspondientes a la **Unidad I: Interfaz Gráfica de Usuario**, junto con un ejemplo práctico desarrollado en Python.

El proyecto fue realizado utilizando **Visual Studio Code**, donde se desarrolló y ejecutó el código del programa.

Además de la investigación teórica, se desarrolló una pequeña aplicación tipo chat utilizando la biblioteca Flet, con el objetivo de comprender cómo funcionan las interfaces gráficas y el manejo de eventos dentro de un programa.

---

# Objetivo

El objetivo de este trabajo es comprender los conceptos básicos relacionados con:

* Interfaces gráficas de usuario
* Eventos dentro de una aplicación
* Manejo de componentes gráficos
* Programación dirigida por eventos

También se busca aplicar estos conocimientos mediante el desarrollo de un programa sencillo.

---

# Herramientas utilizadas

Para el desarrollo de este proyecto se utilizaron las siguientes herramientas:

Python – Lenguaje de programación

Flet – Biblioteca para crear interfaces gráficas

Visual Studio Code – Editor de código

GitHub – Plataforma para almacenar el proyecto

---

# Desarrollo del programa

Como parte práctica del trabajo se desarrolló un pequeño programa de chat que permite escribir mensajes y mostrarlos en pantalla.

Durante el desarrollo se siguieron varios pasos.

Primero se creó la estructura del programa y se importaron las librerías necesarias.

Después se diseñó la interfaz gráfica utilizando componentes como cuadros de texto, botones y listas de mensajes.

Finalmente se implementó el manejo de eventos para que el programa pudiera responder cuando el usuario enviara un mensaje.

---

# Ejemplo de interfaz

Las interfaces gráficas permiten interactuar con el sistema de manera visual.

---

# Ejecución del programa

Instalar Flet:

pip install flet

Ejecutar el programa:

python chat_flet.py

El programa abrirá automáticamente en el navegador.

---

# Conclusión

El estudio de las interfaces gráficas de usuario es fundamental dentro del desarrollo de software. Gracias a estas interfaces, los usuarios pueden interactuar con los sistemas de una forma más sencilla.

Mediante este proyecto se pudieron comprender los conceptos básicos de la creación de interfaces gráficas, el manejo de eventos y la utilización de componentes visuales dentro de una aplicación.

Además, el uso de herramientas como Visual Studio Code facilitó el desarrollo y prueba del programa.

---
# Unidad I – Interfaz Gráfica de Usuario

## Introducción

Una interfaz gráfica de usuario, conocida como GUI, es un medio que permite a las personas interactuar con un sistema informático mediante elementos visuales como botones, ventanas, menús e iconos.

Las interfaces gráficas surgieron para facilitar el uso de las computadoras, ya que anteriormente era necesario escribir comandos para poder utilizar un programa.

Actualmente casi todos los sistemas utilizan interfaces gráficas porque son más fáciles de comprender.

---

# 1.1 Creación de interfaz gráfica para usuarios

La creación de una interfaz gráfica consiste en diseñar la forma en que el usuario interactuará con el sistema.

Esto incluye la organización de los elementos visuales y la forma en que el usuario introduce o recibe información.

Para que una interfaz sea eficiente debe cumplir con algunas características:

* Ser fácil de utilizar
* Tener una estructura clara
* Mostrar la información de forma organizada
* Permitir realizar acciones de manera rápida

Entre los elementos más comunes dentro de una interfaz se encuentran:

Ventanas
Botones
Campos de texto
Listas desplegables
Etiquetas informativas

Estos elementos ayudan a que el usuario pueda interactuar con el sistema de forma sencilla.

---

# 1.2 Tipos de eventos

Un evento es cualquier acción que ocurre dentro de una aplicación cuando el usuario interactúa con ella.

Por ejemplo:

Clic del mouse
Presionar una tecla
Seleccionar una opción
Abrir una ventana

Los eventos son detectados por el programa, el cual responde mediante instrucciones previamente programadas.

---

# 1.3 Manejo de eventos

El manejo de eventos consiste en definir qué debe hacer el sistema cuando ocurre una acción específica.

Por ejemplo, cuando el usuario presiona un botón, el programa puede ejecutar una función que procese información o muestre un mensaje.

Este tipo de programación se conoce como **programación dirigida por eventos**, ya que el flujo del programa depende de las acciones realizadas por el usuario.

---

# 1.4 Manejo de componentes gráficos de control

Los componentes gráficos de control son los elementos que permiten la interacción entre el usuario y el sistema.

Entre los más utilizados se encuentran:

Botones – Ejecutan acciones
Campos de texto – Permiten escribir información
Casillas de verificación – Activan opciones
Listas desplegables – Permiten seleccionar opciones
Botones de opción – Permiten elegir una alternativa

Estos componentes pueden ser configurados mediante programación para cambiar su comportamiento o apariencia.

---

# Conclusión

Las interfaces gráficas son una parte fundamental de los sistemas informáticos actuales. Gracias a ellas, las personas pueden utilizar programas de manera más sencilla.

Comprender el funcionamiento de los eventos y de los componentes gráficos permite desarrollar aplicaciones más completas y fáciles de utilizar.

# Explicación del código del chat

A continuación se explica el funcionamiento del programa desarrollado en Python utilizando la biblioteca **Flet**. El objetivo de este programa es crear una interfaz gráfica sencilla que permita enviar y mostrar mensajes dentro de un chat.

Para entender mejor el funcionamiento del código, se explica por secciones.

---

# 1. Importación de librerías

Primero se importan las librerías necesarias para el funcionamiento del programa.

```python
from dataclasses import dataclass
import flet as ft
```

La librería **dataclasses** permite crear clases de forma sencilla para almacenar información.
En este caso se utiliza para representar los mensajes del chat.

Por otro lado, **Flet** es una biblioteca que permite crear interfaces gráficas modernas utilizando Python.

---

# 2. Creación de la estructura del mensaje

Después se define una clase que representa cada mensaje dentro del chat.

```python
@dataclass
class Message:
    user_name: str
    text: str
    message_type: str
```

Esta clase permite guardar tres datos importantes:

• El nombre del usuario
• El texto del mensaje
• El tipo de mensaje

El uso de una estructura de datos ayuda a organizar mejor la información dentro del programa.

---

# 3. Diseño del componente del mensaje

En esta parte del código se define cómo se mostrará cada mensaje dentro de la interfaz.

```python
class ChatMessage(ft.Row):
    def __init__(self, message: Message):
        super().__init__()
```

Aquí se crea un componente gráfico basado en una fila. Esto permite organizar los elementos del mensaje de manera horizontal.

Después se agregan los controles visuales.

```python
self.controls = [
    ft.CircleAvatar(
        content=ft.Text(message.user_name[:1].upper()),
        color=ft.Colors.WHITE,
        bgcolor=ft.Colors.BLUE,
    ),
```

Este elemento crea un círculo que muestra la inicial del usuario.

Posteriormente se agregan los textos.

```python
ft.Column(
    controls=[
        ft.Text(message.user_name, weight="bold"),
        ft.Text(message.text),
    ]
)
```

En esta sección se muestra el nombre del usuario y el contenido del mensaje.

---

# 4. Creación de la función principal

Después se define la función principal del programa.

```python
def main(page: ft.Page):
```

Esta función se encarga de crear y organizar todos los elementos que aparecerán en la interfaz.

Dentro de ella se configuran diferentes propiedades de la página.

```python
page.title = "Chat con Flet"
```

Esto define el título de la aplicación.

---

# 5. Área donde se muestran los mensajes

En esta parte se crea una lista que almacenará todos los mensajes enviados.

```python
chat = ft.ListView(expand=True)
```

Cada vez que el usuario envía un mensaje, este se agrega a la lista para mostrarse en la pantalla.

---

# 6. Campo para escribir mensajes

Luego se crea el campo de texto donde el usuario puede escribir.

```python
message_box = ft.TextField(
    hint_text="Escribe un mensaje",
    expand=True
)
```

Este componente permite introducir el mensaje que será enviado al chat.

---

# 7. Evento para enviar mensajes

Una de las partes más importantes del programa es el manejo de eventos.

```python
def send_message(e):
```

Esta función se ejecuta cuando el usuario presiona el botón de enviar.

Primero se verifica que el campo no esté vacío.

```python
if message_box.value != "":
```

Después el mensaje se agrega a la lista del chat.

```python
chat.controls.append(
    ChatMessage(
        Message("Usuario", message_box.value, "chat")
    )
)
```

Finalmente se limpia el campo de texto y se actualiza la interfaz.

```python
message_box.value = ""
page.update()
```

Esto permite que el nuevo mensaje aparezca inmediatamente en pantalla.

---

# 8. Construcción de la interfaz

Posteriormente se agregan todos los componentes a la página.

```python
page.add(
    chat,
    ft.Row(
        [
            message_box,
            ft.IconButton(
                icon=ft.Icons.SEND,
                on_click=send_message
            ),
        ]
    )
)
```

En esta sección se colocan:

• La lista de mensajes
• El campo de texto
• El botón para enviar

Esto forma la estructura principal de la interfaz del chat.

<img width="960" height="557" alt="image" src="https://github.com/user-attachments/assets/ef834387-213d-463c-a424-3bb8ab17927b" />


---

# 9. Ejecución de la aplicación

Finalmente se ejecuta el programa.

```python
ft.app(target=main, view=ft.AppView.WEB_BROWSER)
```

Esta línea inicia la aplicación y hace que se abra automáticamente en el navegador.

<img width="957" height="564" alt="image" src="https://github.com/user-attachments/assets/090fcf0a-2b0a-43ab-b273-5a9d303fd6c9" />


---

# Conclusión sobre el código

El desarrollo de este programa permite comprender cómo funcionan las interfaces gráficas en Python y cómo los eventos permiten que el sistema responda a las acciones del usuario.

Además, demuestra que con herramientas como **Flet** es posible crear aplicaciones visuales de manera sencilla y rápida.

Este tipo de programación es muy utilizado actualmente en el desarrollo de aplicaciones modernas.
