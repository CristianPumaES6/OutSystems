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


v

Layout Block
● Screens use this Block by default

Defines the Screen structure with Placeholders
■ Title
■ Content
■ Bottom

Events
○ OnSync
○ OnPullToRefresh
○ Event Handlers

Common UI Flow
● Exceptions
● Screens
● Blocks
● Redirect

Menu Block
BottomBar Block


On Exception Action
● SecurityException - User not authenticated or authorized
● CommunicationException - No (or weak) connection; timeouts
● AllExceptions - All other exceptions



Common Screens
Splash Screen
    Displayed when app is loading

Login Screen
    Asks for username and password

InvalidPermissions Screen
    OnException Action Destination for Security Exception

Common Screens Actions
 Splash Screen
    ○ OnLoadComplete
    ○ OnUpgradeProgress
    Login Screen
 Login Action
    ■ Server Action
    ■ Must be online to login
        ○ SyncOnLogin
    ■ Performs the sync, if configured


----------------------------------------------------------------------------------
----------------------- 5.7 exercise Layouts and common UI -----------------------
----------------------------------------------------------------------------------
In summary, in this specific exercise lab, we will:
● Tweak the look and feel of the Splash Screen
● Add links to the existing Screens to the Menu
● Add links to the existing Screens to the Bottom Bar


En el bloke menu, se deben enlazar los link de las paginas. esto se hace se pude hacer arrastrando los screem de las plantallas.

Para el bloke de BottomBar, no es tan facil como arrastrar la pantalla, para esto nostros tenemos que usar el bottom Bar item, .

----------------------------------------------------------------------------------
----------------------- 6.1 Logic and Exception Handling -----------------------
----------------------------------------------------------------------------------

Action Flows
- It can only have one Start node
- Every Action flow can end with multiple:
    End nodes
    Raise Exception
    Destination nodes

- Pueden tener muchos Exception Handlers


Code Reusability
Screen Actions
    -Executed client-side
Server / Client Actions - can be called in multiple flows
■ Client Actions .- can call Server and Client Actions
■ Server Actions .- can only call Server Actions


Flow Nodes
    ○ Assign
        Allows setting values to variables
    ○ If
        Creates a conditional branching on an Action flow
    ○ Switch
        Creates conditional branching with multiple branches
    ○ For Each
        Allows iterating through a Record List
    ○ Ad-hoc loops
        Use the If to evaluate a loop condition
    ○ JavaScript


Exception Handling
    ○ Handler Flows
        An Exception is thrown when an operation fails unexpectedly at runtime
    ○ Raising Exceptions
        An Exception can be raised
    ○ Global Exception Handler

------------------------------------------------------
----------------------- 6.2 exercicios -----------------------
---------------------------------------------------------------------

Se creo 2 server action publicas y se puso solo lectura a la entindad ToDo.



------------------------------------------------------
----------------------- 6.3 Validations -----------------------
---------------------------------------------------------------------

------------------------------------------------------
----------------------- 6.4 Roles -----------------------
---------------------------------------------------------------------


------------------------------------------------------
----------------------- 6.5 Debuging -----------------------
---------------------------------------------------------------------

-------------------------------------------------------
------------------------- 6.6 Exercice -------------------------
----------------------------------------------------

se valida los input 
Length(GetToDoById.List.Current.ToDo.Title)<3

y en el server validamos los roles.

CheckRegisteredRole(UserId:)


---------------------------------------------------
------------------------- 6.6 Generar APP ---------
---------------------------------------------------

generar la app es tan facil como dar 2 click.


----------------------------------------------------
--------- 7.2 Exercice Generar APP -----------------
----------------------------------------------------


----------------------------------------------------
---------      8.1 Local Storage     ---------------
----------------------------------------------------

Local Storage Entity
○ Stored on device
○ Available Online or Offline

-- Local Storage Scenarios

    Various local storage use cases
    Stand alone apps
    Caching
    Offline
        ■ Store data locally
        ■ Read only, or can data be changed?
        ■ All data, or subsets of data?

-- Creating Local Storage Entities
        
    Created just like a Database Entity
        Special “All” Actions (for sync process)
        ■ CreateOrUpdateAll and DeleteAll Actions


    No Static Entities in Local Storage


-- Initializing Local Storage Entities
    Download data from the server
    Create / enter data on device (user)
    No data preview


-- Fetching Data from Local Storage
    Data from Local Storage can only be fetched via Aggregates

-- Securing Local Storage
    Avoid storing sensitive data on the device
    Store small amounts of sensitive data
        - Use Javascript encryption framework to encrypt data before storing it


----------------------------------------------------
---------   8.2 Ejercicio Local Storage   ----------
----------------------------------------------------




----------------------------------------------------
---------   8.3 Data Synchonization   ----------
----------------------------------------------------
Configures automatic start and retry
of the synchronization process
    ○ When the app gets online
    ○ When the user logs in
    ○ When the user resumes the app


OfflineDataSync Action

Can be used for creating logic executed on the client

Client Action that calls the server to synchronize data
    Input parameter: SyncUnit
    Calls ServerDataSync
        ■ Needs SyncUnit as Input

SyncUnit
    ○ Defines set of data to sync


Synchronization patterns

    Read-Only Data
        Use this synchronization pattern when your users only need to read data while the app is offline and the amount of data to synchronize is small.

    Read-Only Data Optimized
        Use this synchronization pattern when your users only need to read data while the app is offline and there are large amounts of data to synchronize.

    Read/Write Data Last Write Wins
        Use this synchronization pattern when it is not likely for more than one user to change the same data while the app is offline.

    Read/Write Data with Conflict Detection
        This data synchronization pattern is recommended for advanced scenarios where multiple end-users will change the same data while the apps are offline.

    Read/Write Data One-to-Many
        This data synchronization pattern is recommended for mobile apps with entities that follow a one-to-many relationship and where it is not likely for multiple end-users to change the same data while the apps are offline.

----------
OfflineDataSync Events Block

Handles Sync Events
    ○ OnSyncComplete
    ○ OnSyncError
    ○ OnSyncStart