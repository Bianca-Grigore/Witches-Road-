##Witches Road - Console-Based Survival Game
Witches Road is a console-based, object-oriented survival and exploration game developed in C++. The game features tactical combat, dynamic environments, and a robust character management system. Players can navigate through two distinct levels, face various environmental hazards (Spikes, Quicksand), and battle entities like Ghosts.

The primary goal of this project is to demonstrate a deep understanding of Advanced Object-Oriented Programming (OOP) concepts, Modern C++ features, the Standard Template Library (STL), and software Design Patterns.

General Architecture
The project is structured around multiple highly cohesive but cleanly separated class hierarchies, modeling the game's entities, environments, and equipment. It uses smart pointers extensively to ensure safe and leak-free memory management.

1. Character Hierarchy (Entity Management)
This hierarchy models the playable entities in the game. Characters can be uniquely customized or generated using default templates via the Factory Design Pattern.

Base class: Character (Abstract) – Defines the core attributes and polymorphic interface for all entities.

Derived classes:

Witch – A mortal character relying on speed, life points, and coven affiliations.

Deity – A powerful, immortal entity featuring flight mechanics (flySpeed, flyHeight), reincarnation abilities, and specific divine powers.

2. Equipment & Abilities Hierarchy (Multiple Inheritance)
Models the combat and utility systems, showcasing advanced C++ inheritance mechanics.

Base classes: `Spell` (handles magical casting, healing, and AOE parameters) and `Weapon` (handles physical durability, attack range, and status effects).

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
