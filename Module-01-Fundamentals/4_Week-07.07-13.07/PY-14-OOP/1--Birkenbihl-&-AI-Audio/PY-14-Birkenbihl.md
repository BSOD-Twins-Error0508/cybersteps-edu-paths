Welcome! Before our live session on Object-Oriented Programming, OOP, please go through this material. Understanding these concepts will help you get the most out of our class. Willkommen! Vor unserer Live-Sitzung über Objektorientierte Programmierung, OOP, gehe bitte dieses Material durch. Das Verständnis dieser Konzepte wird dir helfen, das Beste aus unserem Unterricht herauszuholen.

What is Object-Oriented Programming? Was ist Objektorientierte Programmierung?

Here's an example: class Dog, colon, def underscore underscore init underscore underscore(self, name), colon, self.name equals name. def bark(self), colon, print(f"{self.name} says woof!"). dog1 equals Dog("Buddy"). dog1.bark(). Hier ist ein Beispiel: class Dog, Doppelpunkt, def Unterstrich Unterstrich init Unterstrich Unterstrich(self, name), Doppelpunkt, self.name gleich name. def bark(self), Doppelpunkt, print(f"{self.name} says woof!"). dog1 gleich Dog("Buddy"). dog1.bark().

Up until now, you've likely been writing Python code in a procedural way. You write sequences of instructions, perhaps organizing reusable pieces into functions. This works well for many tasks, but as programs become larger and more complex, managing them can become difficult. Bis jetzt hast du wahrscheinlich Python-Code auf prozedurale Weise geschrieben. Du schreibst Sequenzen von Anweisungen, organisierst vielleicht wiederverwendbare Teile in Funktionen. Das funktioniert gut für viele Aufgaben, aber wenn Programme größer und komplexer werden, kann ihre Verwaltung schwierig werden.

Object-Oriented Programming, OOP, is a different way of thinking about and structuring your code. Instead of focusing primarily on procedures, functions, OOP focuses on objects. Objektorientierte Programmierung, OOP, ist eine andere Art, über deinen Code nachzudenken und ihn zu strukturieren. Anstatt sich hauptsächlich auf Prozeduren, Funktionen, zu konzentrieren, konzentriert sich OOP auf Objekte.

Think about the real world. It's full of objects: cars, dogs, computers, network packets, log entries, user accounts. Each of these objects has: Denke an die reale Welt. Sie ist voller Objekte: Autos, Hunde, Computer, Netzwerkpakete, Logeinträge, Benutzerkonten. Jedes dieser Objekte hat:

State: Characteristics or data associated with the object, for example a car has a color, make, and model; a log entry has a timestamp, source IP, and message. Zustand: Eigenschaften oder Daten, die mit dem Objekt verbunden sind, zum Beispiel hat ein Auto eine Farbe, Marke und Modell; ein Logeintrag hat einen Zeitstempel, Quell-IP und Nachricht.

Behavior: Actions the object can perform or actions that can be performed on it, for example a car can start, accelerate, and brake; a log entry can be parsed or filtered. Verhalten: Aktionen, die das Objekt ausführen kann oder die auf ihm ausgeführt werden können, zum Beispiel kann ein Auto starten, beschleunigen und bremsen; ein Logeintrag kann geparst oder gefiltert werden.

OOP allows us to model these real-world or conceptual objects directly in our code. We create blueprints for objects, define their state and behavior, and then create and interact with instances of those objects. OOP ermöglicht es uns, diese realen oder konzeptionellen Objekte direkt in unserem Code zu modellieren. Wir erstellen Blaupausen für Objekte, definieren ihren Zustand und ihr Verhalten und erstellen dann Instanzen dieser Objekte und interagieren mit ihnen.

Why use OOP? Warum OOP verwenden?

Organization: Groups related data and functions together, making code easier to understand, manage, and maintain. Organisation: Gruppiert zusammenhängende Daten und Funktionen zusammen, macht Code leichter verständlich, verwaltbar und wartbar.

Reusability: Allows you to define object blueprints, called classes, once and reuse them to create multiple objects. You can also reuse code through mechanisms like inheritance, which we might touch upon later. Wiederverwendbarkeit: Ermöglicht es dir, Objekt-Blaupausen, genannt Klassen, einmal zu definieren und sie wiederzuverwenden, um mehrere Objekte zu erstellen. Du kannst auch Code durch Mechanismen wie Vererbung wiederverwenden, die wir vielleicht später berühren.

Modularity: Objects are often self-contained, making it easier to work on different parts of a program independently. Modularität: Objekte sind oft in sich geschlossen, was es einfacher macht, an verschiedenen Teilen eines Programms unabhängig zu arbeiten.

Modeling: Provides a natural way to model complex systems and real-world entities. In cybersecurity, this could be modeling things like network connections, security alerts, malware samples, or configuration settings. Modellierung: Bietet einen natürlichen Weg, komplexe Systeme und reale Entitäten zu modellieren. In der Cybersicherheit könnte dies das Modellieren von Dingen wie Netzwerkverbindungen, Sicherheitswarnungen, Malware-Proben oder Konfigurationseinstellungen sein.

Core Concepts Kernkonzepte

Let's break down the fundamental building blocks of OOP in Python. Lass uns die fundamentalen Bausteine von OOP in Python aufschlüsseln.

Classes Klassen

A class is like a blueprint or template for creating objects. It defines the properties, state, and actions, behavior, that all objects created from that class will share. You define a class using the class keyword. Eine Klasse ist wie eine Blaupause oder Vorlage zum Erstellen von Objekten. Sie definiert die Eigenschaften, den Zustand, und Aktionen, das Verhalten, die alle aus dieser Klasse erstellten Objekte teilen werden. Du definierst eine Klasse mit dem class-Schlüsselwort.

Example of a simple class definition: class Dog, colon. This is a special method called the constructor, more on this soon. Beispiel einer einfachen Klassendefinition: class Dog, Doppelpunkt. Das ist eine spezielle Methode, genannt Konstruktor, mehr dazu bald.

def underscore underscore init underscore underscore(self, name, breed), colon. These are attributes, state. self.name equals name. self.breed equals breed. def Unterstrich Unterstrich init Unterstrich Unterstrich(self, name, breed), Doppelpunkt. Das sind Attribute, Zustand. self.name gleich name. self.breed gleich breed.

This is a method, behavior. def bark(self), colon, print(f"{self.name} says Woof!"). Das ist eine Methode, Verhalten. def bark(self), Doppelpunkt, print(f"{self.name} says Woof!").

In this blueprint: Dog is the name of the class. By convention, class names start with a capital letter. In dieser Blaupause: Dog ist der Name der Klasse. Per Konvention beginnen Klassennamen mit einem Großbuchstaben.

underscore underscore init underscore underscore is a special method called the constructor. It's automatically called when you create a new object from the class. It's used to initialize the object's state. The self parameter refers to the specific object being created. Unterstrich Unterstrich init Unterstrich Unterstrich ist eine spezielle Methode, genannt Konstruktor. Sie wird automatisch aufgerufen, wenn du ein neues Objekt aus der Klasse erstellst. Sie wird verwendet, um den Zustand des Objekts zu initialisieren. Der self-Parameter bezieht sich auf das spezifische Objekt, das erstellt wird.

name and breed are attributes. They store the data associated with a specific dog object. We assign the values passed during creation to self.name and self.breed. name und breed sind Attribute. Sie speichern die Daten, die mit einem bestimmten Hunde-Objekt verbunden sind. Wir weisen die während der Erstellung übergebenen Werte self.name und self.breed zu.

bark is a method. It defines an action that a Dog object can perform. Notice it also takes self as its first parameter, allowing the method to access the object's attributes, like self.name. bark ist eine Methode. Sie definiert eine Aktion, die ein Dog-Objekt ausführen kann. Beachte, dass sie auch self als ersten Parameter nimmt, was der Methode erlaubt, auf die Attribute des Objekts zuzugreifen, wie self.name.

Objects, Instances Objekte, Instanzen

An object, also called an instance, is a specific entity created from a class. If Dog is the blueprint, then individual dogs like Fido, Rex, or Luna are the objects created from that blueprint. Each object has its own set of attribute values. Ein Objekt, auch Instanz genannt, ist eine spezifische Entität, die aus einer Klasse erstellt wurde. Wenn Dog die Blaupause ist, dann sind einzelne Hunde wie Fido, Rex oder Luna die Objekte, die aus dieser Blaupause erstellt wurden. Jedes Objekt hat seinen eigenen Satz von Attributwerten.

You create an object by calling the class name as if it were a function, passing any arguments required by the underscore underscore init underscore underscore method: Du erstellst ein Objekt, indem du den Klassennamen aufrufst, als wäre er eine Funktion, und alle Argumente übergibst, die von der Unterstrich Unterstrich init Unterstrich Unterstrich Methode benötigt werden:

Creating objects, instances, of the Dog class: my_dog equals Dog("Fido", "Golden Retriever"). your_dog equals Dog("Rex", "German Shepherd"). Objekte, Instanzen, der Dog-Klasse erstellen: my_dog gleich Dog("Fido", "Golden Retriever"). your_dog gleich Dog("Rex", "German Shepherd").

Now, my_dog and your_dog are two distinct Dog objects. Jetzt sind my_dog und your_dog zwei verschiedene Dog-Objekte.

Attributes Attribute

Attributes are variables that belong to an object. They represent the object's state or data. You access an object's attributes using dot notation, object.attribute. Attribute sind Variablen, die zu einem Objekt gehören. Sie repräsentieren den Zustand oder die Daten des Objekts. Du greifst auf die Attribute eines Objekts mit Punkt-Notation zu, object.attribute.

print(f"My dog's name is: {my_dog.name}") outputs: My dog's name is: Fido. print(f"Your dog's breed is: {your_dog.breed}") outputs: Your dog's breed is: German Shepherd. print(f"Der Name meines Hundes ist: {my_dog.name}") gibt aus: Der Name meines Hundes ist: Fido. print(f"Die Rasse deines Hundes ist: {your_dog.breed}") gibt aus: Die Rasse deines Hundes ist: German Shepherd.

You can also modify attributes if appropriate: my_dog.name equals "Buddy". print(f"My dog's new name is: {my_dog.name}") outputs: My dog's new name is: Buddy. Du kannst auch Attribute ändern, wenn angemessen: my_dog.name gleich "Buddy". print(f"Der neue Name meines Hundes ist: {my_dog.name}") gibt aus: Der neue Name meines Hundes ist: Buddy.

Each object maintains its own values for its attributes. Changing my_dog.name does not affect your_dog.name. Jedes Objekt behält seine eigenen Werte für seine Attribute. Das Ändern von my_dog.name beeinflusst your_dog.name nicht.

Methods Methoden

Methods are functions that belong to an object. They define the object's behavior or actions. You call an object's methods using dot notation, object.method(). Methoden sind Funktionen, die zu einem Objekt gehören. Sie definieren das Verhalten oder die Aktionen des Objekts. Du rufst die Methoden eines Objekts mit Punkt-Notation auf, object.method().

Calling methods on the objects: my_dog.bark() outputs: Buddy says Woof! your_dog.bark() outputs: Rex says Woof! Methoden auf den Objekten aufrufen: my_dog.bark() gibt aus: Buddy says Woof! your_dog.bark() gibt aus: Rex says Woof!

When you call my_dog.bark(), the bark method defined in the Dog class is executed for the my_dog object. The self parameter inside the bark method automatically refers to my_dog in this case, allowing it to access my_dog.name. Similarly, when your_dog.bark() is called, self refers to your_dog. Wenn du my_dog.bark() aufrufst, wird die bark-Methode, die in der Dog-Klasse definiert ist, für das my_dog-Objekt ausgeführt. Der self-Parameter innerhalb der bark-Methode bezieht sich in diesem Fall automatisch auf my_dog, was ihr erlaubt, auf my_dog.name zuzugreifen. Ähnlich bezieht sich self auf your_dog, wenn your_dog.bark() aufgerufen wird.

The self Parameter Der self-Parameter

The self parameter is crucial. It's the first parameter of instance methods, including underscore underscore init underscore underscore, within a class definition. It represents the specific instance, object, on which the method is being called. Python passes the object itself automatically as the first argument when you call a method using dot notation, for example my_dog.bark() implicitly passes my_dog as self to the bark method. You must include self in the method definition to access the object's attributes and other methods. Der self-Parameter ist entscheidend. Er ist der erste Parameter von Instanzmethoden, einschließlich Unterstrich Unterstrich init Unterstrich Unterstrich, innerhalb einer Klassendefinition. Er repräsentiert die spezifische Instanz, das Objekt, auf dem die Methode aufgerufen wird. Python übergibt das Objekt selbst automatisch als erstes Argument, wenn du eine Methode mit Punkt-Notation aufrufst, zum Beispiel übergibt my_dog.bark() implizit my_dog als self an die bark-Methode. Du musst self in der Methodendefinition einschließen, um auf die Attribute und andere Methoden des Objekts zuzugreifen.

Think about it Denke darüber nach

Consider a simple cybersecurity scenario: analyzing log entries. How could you represent a single log entry using a class? What attributes, state, would a LogEntry object need? What methods, behavior, might be useful? For example timestamp, source IP, message, severity? A method to check if it's an error? Betrachte ein einfaches Cybersicherheitsszenario: Analysieren von Logeinträgen. Wie könntest du einen einzelnen Logeintrag mit einer Klasse repräsentieren? Welche Attribute, Zustand, würde ein LogEntry-Objekt brauchen? Welche Methoden, Verhalten, könnten nützlich sein? Zum Beispiel Zeitstempel, Quell-IP, Nachricht, Schweregrad? Eine Methode, um zu prüfen, ob es ein Fehler ist?

Try it yourself Probiere es selbst aus

Open your Python interpreter or create a new dot py file in Visual Studio Code. Öffne deinen Python-Interpreter oder erstelle eine neue Punkt-py-Datei in Visual Studio Code.

Copy the Dog class definition from above. Kopiere die Dog-Klassendefinition von oben.

Create two different Dog objects with different names and breeds. Erstelle zwei verschiedene Dog-Objekte mit verschiedenen Namen und Rassen.

Print the name of the first dog. Drucke den Namen des ersten Hundes.

Call the bark method on the second dog. Rufe die bark-Methode auf dem zweiten Hund auf.

Try changing the breed of the first dog and print its new breed. Versuche, die Rasse des ersten Hundes zu ändern und drucke seine neue Rasse.

Starter code for you to complete: class Dog, colon, def underscore underscore init underscore underscore(self, name, breed), colon, self.name equals name. self.breed equals breed. def bark(self), colon, print(f"{self.name} says Woof!"). Starter-Code zum Vervollständigen: class Dog, Doppelpunkt, def Unterstrich Unterstrich init Unterstrich Unterstrich(self, name, breed), Doppelpunkt, self.name gleich name. self.breed gleich breed. def bark(self), Doppelpunkt, print(f"{self.name} says Woof!").

Your code below: Create dog_one, for example name "Lassie", breed "Collie". Dein Code unten: Erstelle dog_one, zum Beispiel Name "Lassie", Rasse "Collie".

Create dog_two, for example name "Bolt", breed "White Shepherd". Erstelle dog_two, zum Beispiel Name "Bolt", Rasse "White Shepherd".

Print the name of dog_one. Drucke den Namen von dog_one.

Call the bark method on dog_two. Rufe die bark-Methode auf dog_two auf.

Change dog_one's breed to "Rough Collie". Ändere dog_ones Rasse zu "Rough Collie".

Print dog_one's new breed. Drucke dog_ones neue Rasse.

Summary Zusammenfassung

Object-Oriented Programming helps structure code by modeling real-world or conceptual entities as objects. Objektorientierte Programmierung hilft, Code zu strukturieren, indem reale oder konzeptionelle Entitäten als Objekte modelliert werden.

Class: A blueprint defining attributes, state, and methods, behavior. Klasse: Eine Blaupause, die Attribute, Zustand, und Methoden, Verhalten, definiert.

Object, Instance: A specific item created from a class, with its own attribute values. Objekt, Instanz: Ein spezifisches Element, das aus einer Klasse erstellt wurde, mit seinen eigenen Attributwerten.

Attribute: Data or variable belonging to an object. Accessed via object.attribute. Attribut: Daten oder Variable, die zu einem Objekt gehören. Zugriff über object.attribute.

Method: Function belonging to an object, defining its actions. Called via object.method(). Methode: Funktion, die zu einem Objekt gehört, definiert seine Aktionen. Aufgerufen über object.method().

underscore underscore init underscore underscore: The constructor method, used to initialize a new object's state. Unterstrich Unterstrich init Unterstrich Unterstrich: Die Konstruktor-Methode, verwendet, um den Zustand eines neuen Objekts zu initialisieren.

self: Refers to the specific object instance within its class methods. self: Bezieht sich auf die spezifische Objektinstanz innerhalb ihrer Klassenmethoden.

This is just the beginning of OOP. In our live session, we'll dive deeper into more advanced topics. Das ist nur der Anfang von OOP. In unserer Live-Sitzung werden wir tiefer in fortgeschrittenere Themen eintauchen.

The slides for the live session can be viewed here. Try not to peek before class, spoilers inside! Die Folien für die Live-Sitzung können hier angesehen werden. Versuche nicht vor dem Unterricht zu spicken, Spoiler darin!