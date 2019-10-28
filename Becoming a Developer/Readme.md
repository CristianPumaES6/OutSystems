● Create an application
● Create the Core module of the application
● Create the User Interface module of the application
● Create a Client Action that works as a function
● Use that function in another module
● Create an end-user of the application


Crearemos una aplicacion con 2 modulos : el core y la interface.
Creamos una action, y la convertimos a function.
luego desde nuesta interface hacemos que dependa del core y usamos esa accion dentro de las expresiones regulares.

------------------------------------------------
---------------- ENTIDADES ---------------------
------------------------------------------------

Existen 2 core y UI

Entity Actions : CRUD data operations
Create: CreateCustomer
● Retrieve: GetCustomer
● Update: UpdateCustomer
● Delete: DeleteCustomer

Static Entities:
Static Entity Records

y usos


----------------------------------------------------
----------- Modeling Data --------------------------

data relationships 

One-to-one,
one-to-many,
and many to many

Aprendemos a crear dependencias del modulo.

La interface consume del core.

-----------------------------------------------------
------------ Variables ------------------------------
-----------------------------------------------------
Variables
○ Input Parameter
○ Output Parameter
○ Local Variable

Data Types
○ Structures
○ Lists

Variables are defined and exist in a particular scope 


- Input Parameter
Passes a value into its parent’s scope
from the outside scope
    
    Can be set as Mandatory

- Output Parameter
Returns a value from inside its
parent’s scope to the outside scope


- Local Variable
Can be assigned and used “locally”
inside that scope

parent’s scope to the outside scope

--- OutSystems Data Types
OutSystems language is Strongly Typed
● Every variable must declare its data type
● That data type can not change


Structures 

Structures are custom compound data types
-The Structure itself does not hold any value
-Structures are not variables 