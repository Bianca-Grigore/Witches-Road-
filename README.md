Witches Road - Console-Based Survival Game
Witches Road is a console-based, object-oriented survival and exploration game developed in C++. The game features tactical combat, dynamic environments, and a robust character management system. Players can navigate through two distinct levels, face various environmental hazards (Spikes, Quicksand), and battle entities like Ghosts.

The primary goal of this project is to demonstrate a deep understanding of Advanced Object-Oriented Programming (OOP) concepts, Modern C++ features, Standard Template Library (STL), and software Design Patterns.

General Architecture
The project is structured around multiple strongly-coupled but cleanly separated class hierarchies, modeling the game's entities, environments, and equipment. It uses std::shared_ptr extensively to ensure safe and leak-free memory management.

1. Character Hierarchy (Entity Management)
This hierarchy models the playable entities in the game. Characters can be uniquely customized or generated using default templates via the Factory Design Pattern.

Base class: Character (Abstract) – Defines the core attributes and polymorphic interface for all entities.

Derived classes:

Witch – A mortal character relying on speed, life points, and coven affiliations.

Deity – A powerful, immortal entity featuring flight mechanics (flySpeed, flyHeight), reincarnation abilities, and specific divine powers.

2. Equipment & Abilities Hierarchy (Multiple Inheritance)
Models the combat and utility systems, showcasing advanced C++ inheritance mechanics.

Base classes: Spell (handles magical casting, healing, and AOE parameters) and Weapon (handles physical durability, attack range, and status effects).

Derived class: MagicItems – A complex class that inherits from both Spell and Weapon. It successfully resolves the Diamond Problem (via virtual inheritance from a common Items base). It implements custom damage calculation logic based on item rarity, durability degradation, and spell charges.

3. Environment & Hazards Hierarchy
Models the interactive world.

Base class: Obstacles

Derived classes: Spikes, Quicksand, Ghost. These interact polymorphically with the characters, applying damage or status effects based on the entity's type.

Technical Highlights & OOP Implementation
This project strictly adheres to clean code principles and fulfills advanced academic requirements:

Design Patterns:

Singleton Pattern: Used for the Game class to centralize game state management and ensure only one instance of the game loop runs.

Factory Method: Used for seamless character creation (instantiating customized or default Witches and Deities).

Robust Memory Management:

Strict adherence to the Rule of Three/Five (custom copy constructors, assignment operators, and virtual destructors).

Exclusive use of smart pointers (std::shared_ptr) for object ownership.

Advanced Polymorphism: Extensive use of abstract classes, virtual functions, and runtime polymorphism (Upcasting and Downcasting) to manage interactions between characters, weapons, and obstacles.

Modern C++ & STL:

Integration of multiple STL containers (e.g., std::vector, std::list) to manage inventory and map entities.

Data processing and entity filtering using STL algorithms combined with Lambda functions.

Implementation of Custom Template Classes with multiple instantiations to handle generic game data.

Exception Handling: A custom, hierarchical error-handling system derived from std::exception. It demonstrates exception propagation and polymorphic catch blocks (upcasting exceptions) to safely handle invalid game states.

Class Design Best Practices: Heavy use of const correctness, non-trivial static members/methods for shared class states, and extensive Operator Overloading (<<, >>, arithmetic, and logic operators).

# Nu primesc notă pentru că nu am pus titlu și descriere

### Folosiți template-ul corespunzător grupei voastre!

| Laborant  | Link template                                |
|-----------|----------------------------------------------|
| Dragoș B  | https://github.com/Ionnier/oop-template      |
| Tiberiu M | https://github.com/MaximTiberiu/oop-template |
| Marius MC | https://github.com/mcmarius/oop-template     |

## Instrucțiuni de compilare

Proiectul este configurat cu CMake.

Instrucțiuni pentru terminal:

1. Pasul de configurare
```sh
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug
# sau ./scripts/cmake.sh configure
```

Sau pe Windows cu GCC:
```sh
cmake -S . -B build -DCMAKE_BUILD_TYPE=Debug -G Ninja
# sau ./scripts/cmake.sh configure -g Ninja
```

La acest pas putem cere să generăm fișiere de proiect pentru diverse medii de lucru.

## Cerințe obligatorii

Nerespectarea duce la nepunctarea proiectului

  - programul va fi scris în C++
  - programul va avea un meniu interactiv (doar pentru ilustrarea funcționalității)
  - programul nu are erori de compilare
  - fară variabile globale
  - datele membre private(sau protected)
  - GitHub Actions trecute
  - commit-uri pe Git adecvate si punctuale
  - folosirea a funcționalităților limbajului fără sens
  - folosirea a funcționlităților limbajului cu scopul de a încălca "legal" o altă regulă
      - folosirea excesivă a claselor friend
      - folosirea excesviă a elementelor statice
  - lipsa separarea implementarii de definitie

## Cerințe
- [ ] definirea a minim **2-3 ieararhii de clase** care sa interactioneze in cadrul temei alese (fie prin compunere, agregare sau doar sa apeleze metodele celeilalte intr-un mod logic) (6p)
  - minim o clasa cu:
    - [ ] constructori de inițializare [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] constructor supraîncărcat [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-func%C8%9Biilor)
    - [ ] constructori de copiere [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] `operator=` de copiere [*](https://github.com/Ionnier/poo/tree/main/labs/L02#supra%C3%AEnc%C4%83rcarea-operatorilor)
    - [ ] destructor [*](https://github.com/Ionnier/poo/tree/main/labs/L02#crearea-obiectelor)
    - [ ] `operator<<` pentru afișare (std::ostream) [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L123)
    - [ ] `operator>>` pentru citire (std::istream) [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L128)
    - [ ] alt operator supraîncărcat ca funcție membră [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L32)
    - [ ] alt operator supraîncărcat ca funcție non-membră [*](https://github.com/Ionnier/poo/blob/main/labs/L02/fractie.cpp#L39) - nu neaparat ca friend
  - in derivate
      - [ ] implementarea funcționalităților alese prin [upcast](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding) și [downcast](https://github.com/Ionnier/poo/tree/main/labs/L04#smarter-downcast-dynamic-cast)
        - aceasta va fi făcută prin **2-3** metode specifice temei alese
        - funcțiile pentru citire / afișare sau destructorul nu sunt incluse deși o să trebuiască să le implementați 
      - [ ] apelarea constructorului din clasa de bază din [constructori din derivate](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-la-derivare)
      - [ ] suprascris [cc](https://github.com/Ionnier/poo/tree/main/labs/L04#comportamentul-constructorului-de-copiere-la-derivare)/op= pentru copieri/atribuiri corecte
      - [ ] destructor [virtual](https://github.com/Ionnier/poo/tree/main/labs/L04#solu%C8%9Bie-func%C8%9Bii-virtuale-late-binding)
  - pentru celelalte clase se va definii doar ce e nevoie
  - minim o ierarhie mai dezvoltata (cu 2-3 clase dintr-o clasa de baza)
  - ierarhie de clasa se considera si daca exista doar o clasa de bază însă care nu moștenește dintr-o clasă din altă ierarhie
- [ ] cât mai multe `const` [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L04#reminder-const-everywhere)
- [ ] funcții și atribute `static` (în clase) [0.5p](https://github.com/Ionnier/poo/tree/main/labs/L04#static)
  - [ ] 1+ atribute statice non-triviale 
  - [ ] 1+ funcții statice non-triviale
- [ ] excepții [0.5p](https://github.com/Ionnier/poo/tree/main/labs/L04#exception-handling)
  - porniți de la `std::exception`
  - ilustrați propagarea excepțiilor
  - ilustrati upcasting-ul în blocurile catch
  - minim folosit într-un loc în care tratarea erorilor în modurile clasice este mai dificilă
- [ ] folosirea unei clase abstracte [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L04#clase-abstracte)
 - [ ] clase template
   - [ ] crearea unei clase template [(1p)](https://github.com/Ionnier/poo/tree/main/labs/L08)
   - [ ] 2 instanțieri ale acestei clase (0.5p)
 - STL [(0.25p)](https://github.com/Ionnier/poo/tree/main/labs/L07#stl)
   - [ ] utilizarea a două structuri (containere) diferite (vector, list sau orice alt container care e mai mult sau mai putin un array)
   - [ ] utilizarea a unui algoritm cu funcție lambda (de exemplu, sort, transform)
 - Design Patterns [(0.75p)](https://github.com/Ionnier/poo/tree/main/labs/L08)
   - [ ] utilizarea a două șabloane de proiectare

### Observații

* Pot exista depunctări până la 2p pentru diferite aspecte precum:
  - memory leak-uri
  - nefolosirea destructorului virtual la nevoie
  - abuzarea de diferite concepte (toate funcțiile declarate virtual)
  - apelarea de funcții virtual în constructori

* În general, acestea sunt prezente în [CppCoreGuideline](https://github.com/isocpp/CppCoreGuidelines/blob/master/CppCoreGuidelines.md), dar nu e nevoie să parcurgeți documentul, doar să scrieți codul suficient de organizat

* folderele `build/` și `install_dir/` sunt adăugate în fișierul `.gitignore` deoarece
conțin fișiere generate și nu ne ajută să le versionăm.
