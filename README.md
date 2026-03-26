# Witches Road | Tactical Simulation Framework
A modular, high-performance simulation engine built with Modern C++. This project serves as a technical showcase for scalable system architecture, focusing on decoupled logic, deterministic memory management, and advanced OOP patterns.

## 🏗 System Architecture & Design Philosophy
The engine is designed around the principle of Separation of Concerns (SoC), dividing the simulation into distinct, interoperable modules.

### 1. Data-Driven Level Configuration
Unlike hardcoded environments, the system utilizes a Configurator-based approach (LevelOneConfigurator, LevelTwoConfigurator).

Impact: The core simulation loop is agnostic of specific level data. New environments can be injected by implementing the configurator interface, demonstrating a strong grasp of Dependency Injection principles.

### 2. Entity Management (Factory & Polymorphism)
Creational Logic: Implemented a Factory Pattern to centralize entity generation. This prevents the "leaking" of concrete class types into the main game logic, allowing for easy expansion of the character library.

Complex Hierarchies: Managed diverse entity behaviors (e.g., Mortal vs. Immortal movement) through a clean polymorphic interface, ensuring that the engine treats all agents uniformly while executing specialized logic at runtime.

### 3. Hybrid Item Composition 
To support multi-functional objects (e.g., MagicItems that function as both physical weapons and magical spells), the system employs Virtual Inheritance.

Memory Optimization: By resolving the Diamond Problem through virtual bases, the engine ensures a lean memory footprint and prevents data duplication across complex inheritance graphs.

Logic Composition: Merges durability-based physical logic with charge-based magical logic into a unified, stateful component.

## 🚀 Technical Excellence & Backend Standards
Memory Safety & Resource Management
RAII Implementation: 100% adherence to Resource Acquisition Is Initialization. All object lifecycles are managed through Smart Pointers (std::unique_ptr for exclusive ownership, std::shared_ptr for shared world resources).

Rule of Five: Explicitly implemented move semantics and copy control to ensure efficient resource transfers and prevent dangling pointers or memory leaks.

## Performance & Data Processing
STL Integration: Optimized entity filtering and spatial queries using STL Algorithms (std::find_if, std::for_each, std::remove_if) combined with Lambda expressions.

Generic Programming: Developed a template-based Inventory<T> system, allowing for type-safe storage and manipulation of diverse object types without code duplication.

System Resilience
Custom Exception Hierarchy: Designed a robust error-reporting system derived from std::exception. It handles everything from invalid move-states to resource exhaustion, ensuring the simulation can recover gracefully without a total process crash.
