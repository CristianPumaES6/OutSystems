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

---------------------------------------------------
-------- Ejercicio 3 ------------------------------
---------------------------------------------------

creating the data model.

Tomar en cuenta cuando una funcion o entidad se usa desde otro lado, es recomendable agregar de tipo publica.

// la relaciones se haces desde Data Type

-------------------------------
---------- 4.1 Screen ---------
-------------------------------
Screen Templates
Screens can be Empty or based on a Template

Screen Content
OutSystems Screens are built based on widgets (UI elements)

Screen Variables
What is displayed to the end-user can depend on data
● Some data can come be passed to the Screen
    Input Parameters
● These variables only exist in the scope of the
Screen

Fetching Data to Display on Screen
Database or Local Storage Entities
    Data Action for advanced cases
        - Server Action
        -Output Data Type by default is Text, but can be changed



Client-side Logic
    Client Actions
        - Visually modeled logic and data
        - Easy to call server-side logic

-------------------------------------------
---------- 4.2 Aggregates Overview --------
-------------------------------------------

Aggregates allow us to define
database queries in a visual way
● Add Sources
● Create filters
● Define sorting


Aggregates are easy to create
and maintain
● Excel-like display of real data
● SQL knowledge is NOT required

-------------------------------------------
---------- 4.3 Movile Widgets --------
-------------------------------------------

Existes muchos componentes basico la proxima que lean esto, les recomiendo leer el doc.

----------------------------------------------
---------------- Exercice --------------------
----------------------------------------------

First, we will add a reference to the Entities from the ToDo module.

le agregamos al if

un if tiene un container. Condition .GetToDoesByUserId.HasFetchError

condicionales: 

GetToDoesByUserId.HasFetchError

not GetToDoesByUserId.IsDataFetched

GetToDoesByUserId.List.Empty

El List necesita un source , asi que arrastramos un atributo del aggregates 
List => 

LISTAR - Crear y editar.


----------------------------------------------------------------
---------------- 5.1 Advanced Data QUerties --------------------
----------------------------------------------------------------

Advanced Queries
● Aggregates
○ Multiple Sources
○ Joins
    ● Only With
    ● With or Without
    ● With

○ Calculated Attributes
    
○ Aggregating Records

----------------------------------------------------------------
----------------------- 5.3 Themes Style -----------------------
----------------------------------------------------------------

Customizing CSS

----------------------------------------------------------------
----------------------- 5.5 Mobile Screen ----------------------
----------------------------------------------------------------
Server is only needed for querying the database or executing server-side code

Events during the transition can be used in the application logic

App Events
○ On Application Ready
     Executed when the application is loading
○ On Application Resume
    ecuted when the application is
    returning from background to
    foreground



Screen Lifecycle Events
○ OnInitialize
○ OnReady
○ OnRender
○ OnDestroy

Lifecycle Event Handlers

-------On Initialize--------------
Occurs after checking the permission of the user to access the Screen, but before
navigating to the Screen and fetching data. You can use it to initialize the Screen,
by setting its default data.

-------On Ready --------------
Occurs after the Screen DOM is ready. You can use it to manipulate the DOM.

-------On Render --------------
Occurs right after the Screen On Ready Event handler and every time the data of a
Screen changes. You can use it to update some third-party component.

-------On Destroy ---------------------
Occurs before destroying a Screen and removing it from the DOM. You can use it
to implement logic when the component is disposed.

------- On After Fetch---------------------
Occurs after an Aggregate or Data Action has finished fetching data, but before
the data is rendered on the Screen.You can use it to act upon the retrieved data
