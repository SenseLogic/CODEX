![](LOGO/codex.png)

# Codex

Language-agnostic coding standard.

## Goals

Efficiently develop code and applications in a disciplined manner which ensures the following qualities :

*   **Adequate** : perfectly matches the user needs.
*   **Efficient** : minimizes processing and waiting times to avoid frustration and maximize productivity.
*   **Attractive** : allows interaction through a nice looking interface.
*   **Ergonomic** : can be used in an intuitive and productive manner.
*   **Robust** : runs without crash even under bad connectivity conditions.
*   **Secure** : protects the data from being lost, corrupted, stolen or hacked.
*   **Maintainable** : is easy to fix and enhance by any programmer in the team.
*   **Extensible** : is easy to extend with new features by reusing existing components.
*   **Consistent** : looks like it has been designed and implemented by a single developer.

## Specificity

This coding standard targets self-documenting code, and favors readability over compactness by :

*   forbidding the use of cryptic acronyms, abbreviations, prefixes and suffixes;
*   including the class name in attributes and variable names.

## Principles

*   **Design before you code** by quickly writing :

    *   a short text or UI flow showing how to use the application, to optimize the **user interface** before implementing it;
    *   a short text or database design showing how the information will be stored, to optimize the **data architecture** before implementing it;
    *   a short text or component design showing how the application will be structured, to optimize the **component architecture** before implementing it;
    *   a short text or test code showing how to use the application components, to optimize the **component interface** before implementing it.

*   Develop programs **gradually**, starting with the data components, then implementing one external feature at a time.

*   Don't overgineer your code, choose **simple modular designs** which can easily be extended.

*   Don't repeat yourself, create **reusable components** that you can use several times across one or several projects.

*   Develop the application and its components with **simple** **efficient** **maintainable** code that :
    *   is **stable** and **robust**;
    *   is **easy to understand** just by itself, without comments or surrounding context;
    *   can be easily **extended** and debugged by any programmer in the team;
    *   minimizes **software entropy**, by maintaining an **orderly structure** over time and **fully** complying with the coding standard.

*   Instead of adding comments to explain the code intent, **refactor the code itself** to make this intent obvious by :

    *   using **clear consistent unambiguous names** for all classes, attributes, functions, parameters and variables;
    *   using local variables to store **intermediate results**;
    *   splitting long functions into several **smaller functions** called in sequence;
    *   keeping your functions small enough so that they **just do what their name says**, and nothing more;
    *   implement **English-like code** that reads so naturally that even a child could understand what it does.

*   Even if you are on a hurry :
    *   immediately fix any **design or implementation flaw** you see, or else technical debt will accumulate, and thus drastically slow you down in the future.
    *   continue to develop **clean maintainable code** to limit sofware entropy, as this will help you **ship faster** by keeping a high level of productivity even if the project size and complexity grow over time.

*   Be a source of **order** instead of chaos, so always leave the code in a better state than you found it.

*   Make the application **resilient** to external conditions (network failures, missing or corrupted files, etc).

*   Check invalid method parameters with **assertions** in the debug build.

*   For performance reasons, preferably use :

    *   public attributes without getters and setters.
    *   public non-virtual methods.
    *   virtual methods instead of delegates.
    *   state classes instead of coroutines.

*   Use private attributes and methods only where you need to.

*   Create automated **unit tests**.

*   Only push **stable tested code** to the ´develop´ branch, and only after **testing your changes** extensively.
*   Test those changes again and even more thoroughly when merging them into ´release´, and then ´master`, making sure this won't cause any downtime or loss of data.

*   Use the concise functions provided by the project high level libraries instead of calling directly the low level functions they wrap.

## Main rules

*   Write **simple and efficient self-documenting code**, where the intent of each line of code is perfectly obvious without any comment or context
*   Write **short** functions and methods which use **clear non-ambiguous** names for all type, function, variable and constant identifiers
*   Split your styling code using section comments : IMPORTS, CONSTANTS, ELEMENTS, CLASSES
*   Split your imperative code using section comments : IMPORTS, CONSTANTS, VARIABLES, TYPES, ATTRIBUTES, CONSTRUCTORS, INQUIRIES, OPERATIONS, FUNCTIONS, STATEMENTS
*   Use **Unix line endings**
*   Use **four spaces** per indentation level and no tabulations
*   Put braces on their **own line** and **align** them vertically
*   Put JavaScript multiline return arguments in parentheses
*   Indent the content of braces, brackets and parentheses by four spaces
*   Indent closing brackets and parentheses by four spaces
*   Add exactly a space after { [ ( if while for
*   Add exactly a space before } ] )
*   No space between {} [] ()
*   Add an empty line before if while for return
*   Split multiline arrow functions after the => operator
*   No empty line after { [ ( and before } ] )
*   No consecutive empty lines
*   Don't use single letter variable names like a, b, i, j, n (except for x, y, z, w vector components)
*   Use explicit identifiers without any abbreviated word (except for Id, Uuid, Tuid suffixes) made of singular words : productCount, productArray
*   Use the singular form in identifiers (messageArray), except for functions (GetMessages) and booleans (HasMessages)
*   Use the class name in the variable names : addedProductId, productArray
*   Use the key name in the map names : messageByDateMap
*   Use standard variable prefixes : first, last, post, prior, next, old, new, initial, final, minimum, maximum
*   Use standard variable suffixes : Index, Count, Array, Map, Id, Uuid, Tuid, Code, Name, Text, Time, Path
*   Use standard path suffixes : FolderPath, FilePath, FileName, FileLabel, FileExtension
*   Use standard function prefixes : get, find, is, has, clear, set, add, remove, start, stop, begin, end, enter, exit, open, close, read, write, enable, disable
*   Declare most JavaScript local variables with **let**, using **var** only where it is needed
*   Write all type identifiers in PascalCase : Product, ProductImage
*   Write all function, variable and constant identifiers in camelCase : product, productImage, productIndex, productCount, productArray, productByIdMap
*   Write each function parameter on its own line
*   Don't add an ending comma to array literals
*   Declare standard functions and methods instead of arrow functions
*   Use arrow functions only as call arguments
*   Declare HTML attributes in this order : id, class, style, data-, tag-specific, on:
*   Order classes from low to high level : class="icon green-search-icon product-filter-button"
*   Don't use quotes for evaluated HTML attributes : placeholder={ ... }
*   Use double quotes for HTML attributes : id="..." class="..." style="..." data-name="..." src="..." on:click={ ... }
*   Use single quotes for string literals
*   Use pre-incrementations and pre-decrementations : ++productIndex
*   Use strict equality operators : ===, !==
*   Test variables against a constant instead of using a falsy test : !== undefined, !== null, !== 0, !== ''
*   Use script/style/HTML ordering in Svelte components
*   Write null safe code
*   Use null values only where absolutely required (Dart optional arguments, etc)
*   Always use `let` to declare variables, using `const` only for true constants and `var` for hoisted function variables.
*   Fix all warnings and errors, both during compilation and at runtime.

## Sample Svelte component

```
<script>
    // -- IMPORTS

    import { fade } from 'svelte/transition';

    // -- VARIABLES

    export let value = undefined;
    export let valueArray = [ value ];
    export onChange = () => {};

    let valueCount = valueArray.length;
    let

    // -- TYPES

    class Being
    {
        // -- CONSTRUCTORS

        constructor(
            name,
            age
            )
        {
            this.name = name;
            this.age = age;
        }
    }

    // ~~

    class Person
        extends Being
    {
        // -- CONSTRUCTORS

        constructor(
            name,
            age,
            weight
            )
        {
            super( name, age );

            this.weight = weight;
        }

        // -- INQUIRIES

        getAge(
            )
        {
            return age;
        }

        // ~~

        getHelloMessage(
            )
        {
            return `Hello, my name is ${ this.name }, I'm ${ this.age } years old and I weight ${ this.weight } kilograms.`;
        }

        // -- OPERATIONS

        setAge(
            age
            )
        {
            this.age = age;
        }

        // ~~

        setFakeAge(
            age
            )
        {
            if ( age > 0
                 && age < 50
                 && ( age < 20
                      || age > 40 ) )
            {
                this.age = age * 2;
            }
            else if ( age > 20
                      && age < 40
                      && ( age < 25
                           || age > 35 ) )
            {
                this.age = age * 0.5;
            }
            else
            {
                this.age = age + 10;
            }
        }
    }

    // -- FUNCTIONS

    function getFruitText(
        fruitArray
        )
    {
        let fruitText = '';

        for ( let fruitName of fruitNameArray )
        {
            if ( fruitText !== '' )
            {
                fruitText += ', ';
            }

            fruitText += fruitName;
        }

        return fruitText;
    }

    // ~~

    function getAgeInterval(
        sortedPersonArray
        )
    {
        if ( sortedPersonArray.length === 0 )
        {
            return null;
        }
        else
        {
            return (
                {
                    firstAge: sortedPersonArray[ 0 ].age,
                    lastAge: sortedPersonArray[ sortedPersonArray.length - 1 ].age
                }
                );
        }
    }

    // -- STATEMENTS

    let fruitNameArray =
        [
            'apple',
            'banana',
            'cherry'
        ];

    let book =
        {
            title: 'SvelteKit for Beginners',
            author: 'John Doe',
            year: 2023
        };

    let numberArray = [ 1, 2, 3, 4, 5 ];
    let doubledNumberArray = numberArray.map( n => n * 2 );

    let bookText = '';
    let messageCount = 5;

    for ( let messageIndex = 0;
          messageIndex < messageCount;
          ++messageIndex )
    {
        bookText += messageIndex + ': ' + book.title + '<br/>';

        if ( book.year >= 2022 )
        {
            bookText += 'The book is recent!<br/>';
        }
    }

    let passIndex = 0;

    while ( passIndex < 5 )
    {
        ++passIndex;
    }

    do
    {
        ++passIndex;
    }
    while ( passIndex < 10 );

    let fruitText = getFruitText( fruitNameArray );

    let personArray =
        [
            new Person( 'Mike', 49, 85 ),
            new Person( 'Luke', 30, 77 ),
            new Person( 'John', 30, 72 )
        ];

    personArray.sort(
        ( firstPerson, secondPerson ) =>
        {
            try
            {
                if ( firstPerson.age !== secondPerson.age )
                {
                    return firstPerson.age - secondPerson.age;
                }
                else
                {
                    return firstPerson.weight - secondPerson.weight;
                }
            }
            catch ( error )
            {
                console.error( error.message );
            }
        }
        );

    let ageInterval = getAgeInterval( personArray );
</script>

<style lang="stylus">
    // -- ELEMENTS

    h1
    {
        font-size: 2rem;
        color: #34628B;
    }

    h1:hover
    {
        font-size: 2.5rem;
    }

    p
    {
        color: #B24871;
    }

    // -- CLASSES

    .author
    {
        color: #A80BC9;
    }

    .book-text,
    .fruit-list
    {
        color: #2C28B8;
    }

    .person
    {
        font-size: 1.5rem;
        font-weight: 700;
        color: #2929BD;
    }
</style>

<svelte:head>
    <title>SvelteKit Sample</title>
</svelte:head>

<main>
    <h1>
        { book.title }
    </h1>
    <p class="author">
        Author: { book.author }
    </p>
    <div>
        <input placeholder={ `Named ${ book.title }` } bind:value={ book.title }/>
    </div>
    <div>
        <input placeholder={ `Written by ${ book.author }` } bind:value={ book.author }/>
    </div>
    <p class="book-text">
        {@html bookText }
    </p>
    { #each numberArray as number }
        <p class="number" in:fade>
            Number : { number }
        </p>
    { /each }
    <p>
        Doubled numbers: { doubledNumberArray.join( ', ' ) }
    </p>
    <p id="fruit-list" class="fruit-list">
        Fruits: { fruitText }
    </p>
    { #each personArray as person }
        <p class="person">
            { person.getHelloMessage() }
        </p>
    { /each }
    <p>
        { ageInterval.firstAge } - { ageInterval.lastAge }
    </p>
</main>
```

## Sample Dart entity class

```dart
// -- TYPES

class Property
{
    // -- ATTRIBUTES

    final String
        id;
    final double
        number;
    final String
        city,
        country,
        title,
        description;
    final double
        price;
    final String
        imagePath;
    final List<String>
        imagePathArray;
    final Map<String, String>
        propertyByNameMap;

    // -- CONSTRUCTORS

    Property(
        {
            required this.id,
            required this.number,
            required this.city,
            required this.country,
            required this.title,
            required this.description,
            required this.price,
            required this.imagePath,
            required this.imagePathArray,
            required this.propertyByNameMap
        }
        );

    // -- OPERATORS

    @override
    bool operator==(
        Object other
        )
    {
        if ( identical( this, other ) )
        {
            return true;
        }
        else
        {
            return
                other is Property
                && other.id == id;
        }
    }

    // -- INQUIRIES

    Property copyWith(
        {
            String? id,
            double? number,
            String? city,
            String? country,
            String? title,
            String? description,
            double? price,
            String? imagePath,
            List<String>? imagePathArray,
            Map<String, String>? propertyByNameMap
        }
        )
    {
        return Property(
            id: id ?? this.id,
            number: number ?? this.number,
            city: city ?? this.city,
            country: country ?? this.country,
            title: title ?? this.title,
            description: description ?? this.description,
            price: price ?? this.price,
            imagePath: imagePath ?? this.imagePath,
            imagePathArray: imagePathArray ?? this.imagePathArray,
            propertyByNameMap: propertyByNameMap ?? this.propertyByNameMap
            );
    }

    // ~~

    factory Property.fromMap(
        Map<String, dynamic> map
        )
    {
        return Property(
            id: map[ 'id' ],
            number: map[ 'number' ],
            city: map[ 'city' ],
            country: map[ 'country' ],
            title: map[ 'title' ],
            description: map[ 'description' ],
            price: map[ 'price' ],
            imagePath: map[ 'imagePath' ],
            imagePathArray: List<String>.from( map[ 'imagePathArray' ] ),
            propertyByNameMap: Map<String, String>.from( map[ 'propertyByNameMap' ] )
            );
    }

    // ~~

    Map<String, dynamic> toMap(
        )
    {
        return
            {
                'id': id,
                'number': number,
                'city': city,
                'country': country,
                'title': title,
                'description': description,
                'price': price,
                'imagePath': imagePath,
                'imagePathArray': imagePathArray,
                'propertyByNameMap': propertyByNameMap
            };
    }

    // ~~

    @override
    String toString(
        )
    {
        return 'Property { id: $id, number: $number, city: $city, country: $country, title: $title, description: $description, price: $price, imagePath: $imagePath, imagePathArray: $imagePathArray, propertyByNameMap: $propertyByNameMap }';
    }

    // ~~

    @override
    int get hashCode
    {
        return id.hashCode;
    }
}
```

## Sample Flutter component

```dart
// -- IMPORTS

import 'package:cached_network_image/cached_network_image.dart';
import 'package:flutter/material.dart';
import 'package:flutter_bloc/flutter_bloc.dart';
import 'package:go_router/go_router.dart';
import 'package:senselogic_gist/senselogic_gist.dart';
import '../state/view_properties_state.dart';
import '../storage/storage.dart';
import '../store/view_properties_store.dart';

// -- TYPES

class ViewPropertiesPageState
    extends State<ViewPropertiesPage>
{
    // -- ATTRIBUTES

    late final ViewPropertiesStore
        propertyListStore;

    // -- OPERATIONS

    @override
    void initState(
        )
    {
        super.initState();

        propertyListStore = ViewPropertiesStore();
        propertyListStore.fetch();
    }

    // ~~

    @override
    Widget build(
        BuildContext context
        )
    {
        return Scaffold(
            appBar: AppBar(
                title: const Text( 'Property Details' ),
                actions: [
                    IconButton(
                        icon: const Icon( Icons.home ),
                        onPressed: ()
                        {
                            context.go( '/' );
                        },
                        ),
                    IconButton(
                        icon: const Icon( Icons.login ),
                        onPressed: ()
                        {
                            context.go( '/signin' );
                        },
                        ),
                    IconButton(
                        icon: const Icon( Icons.person_add ),
                        onPressed: ()
                        {
                            context.go( '/signup' );
                        }
                        )
                    ]
                ),
            body: BlocConsumer<ViewPropertiesStore, ViewPropertiesState>(
                bloc: propertyListStore,
                listener:
                    ( context, state )
                    {
                    },
                builder:
                    ( context, state )
                    {
                        if ( state is ViewPropertiesInitialState )
                        {
                            return const Text( 'Initial' );
                        }
                        else if ( state is ViewPropertiesLoadingState )
                        {
                            return const Center( child: CircularProgressIndicator() );
                        }
                        if ( state is ViewPropertiesErrorState )
                        {
                            return Center( child: Text( state.error ) );
                        }
                        else if ( state is ViewPropertiesLoadedState )
                        {
                            return
                                ListView.builder(
                                    physics: const ScrollPhysics(),
                                    shrinkWrap: true,
                                    itemCount: state.propertyList.length,
                                    itemBuilder:
                                        ( context, index )
                                        {
                                            final
                                                property = state.propertyList[ index ];

                                            return ListTile(
                                                title: Text( getLocalizedText( property.title ) ),
                                                leading: CachedNetworkImage(
                                                    imageUrl: getStorageImagePath( property.imagePath, 640 ),
                                                    placeholder: ( context, url ) => const CircularProgressIndicator(),
                                                    errorWidget: ( context, url, error ) => const Icon( Icons.error )
                                                    ),
                                                onTap: () => context.go( '/property/${ property.id }' ),
                                                );
                                        }
                                    );
                        }
                        else
                        {
                            return const Icon( Icons.error );
                        }
                    }
                )
            );
    }
}

// ~~

class ViewPropertiesPage
    extends StatefulWidget
{
    // -- CONSTRUCTORS

    const ViewPropertiesPage(
        {
            super.key
        }
        );

    // -- OPERATIONS

    @override
    ViewPropertiesPageState createState(
        )
    {
        return ViewPropertiesPageState();
    }
}
```
## Common rules

*   Use **American English** everywhere.

    ```cs
    initializeColor();
    moveForward();
    ```

*   Use the **English language order** in compound identifiers.

    ```cs
    enemyListByCategoryDictionary = getEnemyListByCategoryDictionary();
    ```

*   Use the **meter** as the default distance unit.

*   Use the **second** as the default time unit.

*   Use **four spaces** instead of tabulations, to make the code independent of the editor settings.

*   Use **Unix line endings**.

*   Trim **trailing whitespace** on save.

*   Choose **short meaningful identifiers** for class, attribute, method, constant and variable names, to prevent ambiguity and cognitive load.

*   Use **standard prefixes** :

    *   first, last, post
    *   prior, next
    *   sub, super, base
    *   initial, final
    *   old, new
    *   backward, forward
    *   left, right
    *   back, front
    *   bottom, top
    *   minimum, maximum
    *   lower, higher, upper
    *   horizontal, vertical
    *   local, global

*   Use **standard suffixes** :

    *   Index, Count
    *   Array (in JavaScript), List (in Dart), Map
    *   Code, Name, Text, Time, Path
    *   Id, Uuid, Tuid

*   Use **standard verbs** :

    *   initialize, update, finalize
    *   create, release, destroy
    *   build, apply
    *   clear, fill
    *   reset, set, get, find
    *   is, has
    *   add, remove
    *   addFirst, removeFirst
    *   addLast, removeLast
    *   start, stop
    *   begin, end
    *   enter, exit
    *   open, close
    *   read, write
    *   load, save
    *   pause, resume
    *   lock, unlock
    *   attach, detach
    *   enable, disable
    *   select, deselect
    *   activate, deactivate
    *   increment, decrement
    *   increase, decrease
    *   compress, decompress
    *   connect, disconnect
    *   send, receive
    *   grant, revoke

*   Name your **types** (classes, structures, enumerations, etc) in **PascalCase** without articles, and declare the base class on the next line.

    ```cs
    class TankShell
        extends Bullet
    {
        Vector3
            positionVector;
        Quaternion
            rotationQuaternion;

        ...
    }
    ```

*   Name your **type members** (methods, attributes, constants, etc) in **camelCase**, without articles.

    ```cs
    shootShell(
        muzzle.positionVector,
        muzzle.rotationQuaternion
        );
    ```

*   Name your **local variables** and **method parameters** in **camelCase**, without articles.

    ```cs
    void shootShell(
        Vector3 shellPositionVector,
        Quaternion shellRotationQuaternion
        )
    {
        TankShell
            shotTankShell;

        ...

        shotTankShell
            = new TankShell(
                  shellPositionVector,
                  shellRotationQuaternion
                  );

        ...
    }
    ```

*   Don't use abbreviations or single-letter variables.

    ```cs
    Tank findTank(
        int tankIdentifier,
        int firstTankIndex,
        int postTankIndex
        )
    {
        int
            tankIndex;

        for ( tankIndex = firstTankIndex;
              tankIndex < postTankIndex;    // no i, j, n, etc
              ++tankIndex )
        {
            if ( tankArray[ tankIndex ].identifier == tankIdentifier )
            {
                return tankArray[ tankIndex ];
            }
        }

        return null;
    }
    ```

*   Avoid acronyms, and capitalize them in member names.

    ```cs
    DatabaseUrl
        databaseUrl;
    ```

*   If a variable name collides with a predefined identifier, simply add a trailing underscore.

    ```cs
    Class
        class_;

    class_ = new Class();
    ```

*   Use a noun or noun phrase for classes, constants, attributes and variable names.

*   Include the meaningful part of the class name in attribute and variable names.

    ```cs
    Dictionary<string, Player>
        activePlayerDictionary;
    List<Enemy>
        closeEnemyList;
    Tank[]
        enemyTankArray;
    Vector3
        initialShellPositionVector,
        tankVelocityVector;

    void shootShell(
        )
    {
        Shell
            lastShotShell,
            shotShell;

        ...
    }
    ```

*   Start method names with a verb in the imperative mood (Set, Get, Find, ...).

*   Start boolean inquiry names with a verb in the indicative mood (Is, Has, Can, ...).

*   Declare the method parameters in the same order as in the method name.

    ```cs
    bool findPlayerIndexByName(
        ref int playerIndex,
        string playerName
        )
    {
        ...
    }
    ```

*   Use a positive affirmation for boolean variable and attribute names.

    ```cs
    if ( gameIsPaused )
    {
        ...
    }
    ```

*   If an attribute name starts like its owner class name, omit the common prefix.

    ```cs
    class Tank
    {
        TankShell[]
            shellArray;
        bool
            isDamaged;

        void shootShell(
            TankShell tankShell
            )
        {
            ...
        }
    }
    ```

*   Align matching braces.

    ```cs
    bool canShoot(
        )
    {
        return shotShellCount < maximumShellCount;
    }

    // ~~

    void shootShell(
        Vector3 initialVelocityVector
        )
    {
        ...
    }
    ```

*   Use braces for single statement blocks.

    ```cs
    if ( loadedAmmunitionCount > 0 )
    {
        shootBullet();
    }
    else if ( carriedAmmunitionCount > 0 )
    {
        reloadWeapon();
    }
    else
    {
        noAmmunitionSound.play();
    }
    ```

*   Declare each attribute, variable and method parameter name on a separate line.

    ```cs
    int
        tankCount,
        tankIndex;
    ```

*   Group local variables of the same type, and sort the declarations by ascending types (lowercase, then PascalCase, then SCREAMING_CASE) and variable names, so that the declaration of a variable can be located at a glance.

    ```cs
    int
        shellCount,
        shellIndex,
        tankCount,
        tankIndex;
    string
        playerName,
        targetName;
    CharacterController
        characterController;
    NavMeshAgent
        navigationMeshAgent;
    Tank
        enemyTank;
    Tank[]
        enemyTankArray;
    ```

*   Split complex statements and expressions on several lines if they contain boolean operators or if they become too wide.

*   When splitting an expression on several lines, start the next lines with an operator and align it with the start of its left operand (or else indent it by 4 spaces).

    ```cs
    if ( ( tower.getDistance(
               towerTarget,
               weaponType
               )
           > tower.maximumShootingDistance )
         || ( tankDistance > maximum distance
              && tankHealth > 0.5 ) )
    {
        ...
    }

    let shellHitsTower
        = ( ( tower.getDistance(
                  towerTarget,
                  weaponType
                  )
              > tower.maximumShootingDistance )
            || ( tankDistance > maximum distance
                 && tankHealth > 0.5 ) );
    ```

*   In multiline assignments, the operator can also be put at the end of the first line, to ease code indentation :

    ```html
    <div
        on:handleShot=
            {
                ( shot ) =>
                {
                    let shellHitsTower =
                        ( ( tower.getDistance(
                                towerTarget,
                                weaponType
                                )
                            > tower.maximumShootingDistance )
                          || ( tankDistance > maximum distance
                               && tankHealth > 0.5 ) );
                }
            }
    >
    </div>
    ```

*   Favor indexed iterations over foreach iterations, and foreach iterations over functional iterations.

    ```cs
    for ( enemyIndex = 0;
          enemyIndex < enemyList.count;
          ++enemyIndex )
    {
        ...
    }

    foreach ( Enemy enemy in enemyList )
    {
        ...
    }
    ```

*   Put the scalar or constant multiplier after the multiplicand expression.

    ```cs
    averageValue = ( firstValue + secondValue ) * 0.5f;
    ```

*   Add exactly one space :

    *   after `(` `[` `,`
    *   before `)` `]`
    *   after `if` `switch` `while` `for` `foreach` `return` ...
    *   around operators.

*   Add exactly one empty line :

    *   around standard comments;
    *   after the local variable declarations;
    *   after the method preconditions;
    *   between `if` `switch` `while` `for` `foreach` `do` `try` `return` and the prior statement;
    *   between `}` and the next statement.

*   Use standard file extensions.

    *   C# : cs
    *   C : c, h
    *   C++ : cpp, hpp
    *   Javascript : js
    *   HTML : html
    *   CSS : css

*   Declare one class per source code file.

*   Use the class name in lowercase as file name.

    ```cs
    tank_shell.cpp
    tank_shell.hpp
    ```

*   Group the class elements by category, and declare them in this order :

    *   Imports.
    *   Types.
    *   Constants.
    *   Attributes.
    *   Constructors.
    *   Destructor.
    *   Operators.
    *   Inquiries : methods which don't change the class attributes.
    *   Operations : methods which may change the class attributes.

*   Within a category, declare :

    *    the called methods before the calling methods, preferably in the order they will be called, so that the class code can be immediately understood by a single sequential read.
    *    the static members after the non-static members.

*   Import exactly what each file needs to be compiled independently, and nothing more.

*   Sort the imports by ascending names.

*   Declare code sections in this order :
    *   imports
    *   constants
    *   types
    *   variables
    *   functions
    *   statements

*   Delimitate code sections with standard comments.

    ```cs
    // -- IMPORTS

    ...

    // -- CONSTANTS

    ...

    // -- TYPES

    class Name
    {
        // -- CONSTANTS

        ...

        // -- ATTRIBUTES

        ...

        // -- CONSTRUCTORS

        ...

        // -- DESTRUCTOR

        ...

        // -- OPERATORS

        ...

        // -- INQUIRIES

        ...

        // -- OPERATIONS

        ...
    }

    // -- VARIABLES

    ...

    // -- FUNCTIONS

    ...

    // -- STATEMENTS

    ...
    ```

*   Don't use standard comments for empty sections.

*   Align multiple lines comments with the surrounding statements, start them with an uppercase character and end them with a period.

    ```cs
    /*
        A long explanation which must be written
        on several lines.
    */

    ...
    ```

*   Align single line comments with the surrounding statements, start them with an uppercase character and end them with a period.

    ```cs
    // A short explanation which can be written on a single line.

    ...
    ```

*   Put end of line comments exactly four spaces after the statement, and start them with lowercase character.

    ```cs
    doSomethingWeird();    // a short explanation
    ```

*   Name the unit test class by simply adding a `_TEST` suffix to the class name.

## CSS rules

*   Use double quotes for string literals.

*   Name your **ids** and **classes** in **kebab-case**, without articles.

*   Use :
    *   **unitless** values for line heights.
    *   **rem** values for font sizes and all other static sizes.
    *   **px** values only for tiny static sizes, like 1 or 2 pixels.
    *   **%**, **vh**, **vw**, **vmin** and **vmax** values for dynamic sizes.
    *   zero or one decimal in your sizes (0.9rem, 1.2vh), unless you absolutely need more precision (0.75rem, 1.25rem).

*   Group **rules** by category, and declare them in this order :

    *   Imports
    *   Constants
    *   Variables
    *   Functions
    *   Mixins
    *   Fonts
    *   Elements
    *   Classes

*   Delimitate rule sections with standard comments.

    ```cs
    // -- IMPORTS

    ...

    // -- CONSTANTS

    ...

    // -- VARIABLES

    ...

    // -- FUNCTIONS

    ...

    // -- MIXINS

    ...

    // -- FONTS

    ...

    // -- ELEMENTS

    ...

    // -- CLASSES

    ...
    ```

*   Order **rules** by increasing interiority, appearance order, and specificity.

*   For a same base selector class, declare rules in this order :

    *   @keyframe class-animation
    *   .class
    *   .class:not()
    *   .class:first-child
    *   .class:nth-child()
    *   .class:last-child
    *   .class:hover
    *   .class:focus
    *   .class:active
    *   .class:invalid
    *   .class:before
    *   .class:after
    *   .class:placeholder-shown
    *   .class::placeholder
    *   .class ~ .other-class
    *   .class + .other-class
    *   .class > .other-class
    *   .class .other-class
    *   .class#id
    *   .class.other-class

*   Declare concatenated **specifiers** in this order :

    *   element
    *   #id
    *   .class
    *   :not()
    *   :first-child
    *   :nth-child()
    *   :last-child
    *   :hover
    *   :focus
    *   :active
    *   :invalid
    *   :before
    *   :after
    *   :placeholder-shown
    *   ::placeholder

*   Declare **media queries** inside the rule using the "+Media" mixin, right after the declarations, and order them by increasing breakpoint.

    ```css
    .class
    {
        ...

        @media ( min-width: 40em )
        {
            ...
        }

        @media ( min-width: 60em )
        {
            ...
        }
    }
    ```

*   Group **declarations** by category :

    *   Inheritance
    *   Position
    *   Container
    *   Layout
    *   Content
    *   Typography
    *   Behavior

*   Delimitate declaration sections with a blank line.

    ```css
    .header-menu
    {
        z-index: 100;
        position: fixed;
        top: 0;
        left: 0;
        right: 0;

        padding: 1rem;

        display: flex;
        justify-content: center;
        align-items: center;

        background-color: transparent;

        transition: background-color 0.3s ease;

        +Media( min-width-40em )
        {
            padding: 2rem;
        }

        +Media( min-width-60em )
        {
            padding: 3rem;
        }
    }
    ```

*   Declare **properties** in this order :

    *   Inheritance
        *   @extend
    *   Position
        *   z-index
        *   position
        *   top
        *   bottom
        *   left
        *   right
        *   transform-origin
        *   transform
        *   scale
        *   rotate
        *   translate
    *   Container
        *   container-type
        *   overflow
        *   overflow-y
        *   overflow-x
        *   box-sizing
        *   scrollbar-width
        *   inset
        *   margin
        *   margin-block
        *   margin-block-start
        *   margin-block-end
        *   margin-inline
        *   margin-inline-start
        *   margin-inline-end
        *   margin-top
        *   margin-bottom
        *   margin-left
        *   margin-right
        *   outline
        *   height
        *   min-height
        *   max-height
        *   width
        *   min-width
        *   max-width
        *   aspect-ratio
        *   border
        *   border-top
        *   border-bottom
        *   border-left
        *   border-right
        *   border-width
        *   border-style
        *   border-color
        *   border-image
        *   border-radius
        *   border-top-radius
        *   border-top-left-radius
        *   border-top-right-radius
        *   border-bottom-radius
        *   border-bottom-left-radius
        *   border-bottom-right-radius
        *   border-collapse
        *   padding
        *   padding-top
        *   padding-bottom
        *   padding-left
        *   padding-right
    *   Layout
        *   display
        *   flex
        *   flex-direction
        *   flex-wrap
        *   flex-grow
        *   flex-shrink
        *   flex-basis
        *   flex-flow
        *   grid-template
        *   grid-template-rows
        *   grid-template-columns
        *   grid-template-areas
        *   grid-auto-rows
        *   grid-gap
        *   gap
        *   row-gap
        *   column-gap
        *   grid-area
        *   grid-row
        *   grid-column
        *   justify-content
        *   justify-items
        *   justify-self
        *   align-content
        *   align-items
        *   align-self
        *   order
        *   float
        *   clear
        *   columns
        *   column-count
        *   column-width
        *   column-span
        *   column-fill
        *   column-gap
        *   column-rule
        *   column-rule-width
        *   column-rule-style
        *   column-rule-color
        *   shape-outside
        *   clip-path
        *   object-fit
    *   Content
        *   content
        *   visibility
        *   opacity
        *   background
        *   background-clip
        *   background-color
        *   background-image
        *   background-origin
        *   background-position
        *   background-repeat
        *   background-size
        *   background-attachment
        *   mask
        *   mask-clip
        *   mask-composite
        *   mask-image
        *   mask-mode
        *   mask-origin
        *   mask-position
        *   mask-repeat
        *   mask-size
        *   box-shadow
        *   filter
        *   backdrop-filter
    *   Typography
        *   list-style-type
        *   direction
        *   writing-mode
        *   text-orientation
        *   line-height
        *   font
        *   font-family
        *   font-size
        *   font-weight
        *   font-style
        *   font-stretch
        *   font-variant
        *   white-space
        *   overflow-wrap
        *   word-wrap
        *   word-break
        *   word-spacing
        *   letter-spacing
        *   caption-side
        *   vertical-align
        *   text-align
        *   text-align-last
        *   text-indent
        *   text-justify
        *   text-overflow
        *   text-decoration
        *   text-decoration-line
        *   text-decoration-style
        *   text-decoration-color
        *   text-transform
        *   text-shadow
        *   color
    *   Behavior
        *   resize
        *   scroll-behavior
        *   scroll-snap-type
        *   scroll-snap-points-y
        *   scroll-snap-points-x
        *   user-select
        *   pointer-events
        *   cursor
        *   transition
        *   transition-property
        *   transition-delay
        *   transition-duration
        *   transition-timing-function
        *   animation
        *   animation-name
        *   animation-delay
        *   animation-duration
        *   animation-timing-function
        *   animation-iteration-count
        *   animation-direction
        *   animation-fill-mode
        *   animation-play-state
    *   Media queries (of increasing breakpoint size)

*   Write color literals in **UPPERCASE**.

    ```css
    background-color: #C8C8C8;
    ```

*   Declare Stylus constants in **camelCase**.

    ```css
    redColor = #F87272;
    redColor100 = darken( redColor, 80% );
    ```

*   Declare SCSS constants in **kebab-case**.

    ```css
    $red-color: #F87272;
    $red-color-100: mix( $red-color, #000000, 80% );
    ```

## HTML rules

*   Use double quotes for string literals.

*   Use single quotes inside double-quoted string literals.

*   Declare tag **attributes** in this order :

    *   id
    *   class sorted by increasing specificity
    *   style sorted as explained above
    *   data-* in alphabetical order
    *   tag-specific attributes (src, href, etc) in alphabetical order
    *   on* in alphabetical order

    ```html
    <div id="header-menu-home-button"
         class="button scaled-button header-menu-button header-menu-home-button"
         style="margin-left: auto; background-image: url( '/static/image/header_menu/home_button.svg' )"
         data-view-name="home"
         onclick="ShowView( 'home' )">
        ...
    </div>
    ```

## Svelte rules

*   Use the following order in Svelte components :
    *   script section
    *   style section
    *   HTML section

## Route rules

*   Routes are written in **kebab-case**.
*   User files routes start by **/upload/**.
*   API routes start by **/api/**.
*   Administration routes start by **/admin/**.
*   Page data routes use the **POST** verb.

## Version

1.0

## Author

Eric Pelzer (ecstatic.coder@gmail.com).

## License

This project is licensed under the GNU Lesser General Public License version 3.

See the [LICENSE.md](LICENSE.md) file for details.
