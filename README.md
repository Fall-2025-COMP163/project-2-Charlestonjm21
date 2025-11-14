[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/mMxhKicI)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=21449004&assignment_repo_type=AssignmentRepo)
# COMP 163 - Project 2: Character Abilities Showcase

## 🎯 Project Overview

Build a simple character system that demonstrates mastery of object-oriented programming fundamentals: inheritance, method overriding, polymorphism, and composition. This project focuses on core OOP concepts without the complexity of a full game system.

## 📋 Getting Started

1. **Complete your implementation** in `project2_starter.py`
2. **Test your code** by running: `python project2_starter.py`
3. **Run automated tests** with: `python -m pytest tests/ -v`
4. **Commit and push** to see GitHub test results

## 🏗️ What You're Building

### **Class Structure (6 Classes Total)**

```
Character (base class)
    ↓
Player (inherits from Character)  
    ↓
Warrior, Mage, Rogue (inherit from Player)

Weapon (composition - separate class)
```

### **Required Stats for Each Class:**

| Class   | Health | Strength | Magic | Special Ability |
|---------|--------|----------|-------|-----------------|
| Warrior | 120    | 15       | 5     | Power Strike    |
| Mage    | 80     | 8        | 20    | Fireball        |
| Rogue   | 90     | 12       | 10    | Sneak Attack    |

## 🎮 Core Functionality

### **All Characters Must Have:**
- `attack(target)` - Basic attack method
- `take_damage(damage)` - Reduce health
- `display_stats()` - Print character information

### **Players Additionally Have:**
- `character_class` attribute (like "Warrior", "Mage")
- `level` and `experience` attributes
- Enhanced `display_stats()` that shows player info

### **Special Abilities (Each Class):**
- **Warrior**: `power_strike(target)` - High damage attack
- **Mage**: `fireball(target)` - Magic damage attack
- **Rogue**: `sneak_attack(target)` - Critical hit attack

### **Weapons (Composition):**
- `Weapon(name, damage_bonus)` - Characters can HAVE weapons
- `display_info()` - Show weapon information

## ✅ Testing Your Code

### **Local Testing**
```bash
# Run all tests
python -m pytest tests/ -v

# Run specific test categories
python -m pytest tests/test_inheritance.py -v
python -m pytest tests/test_method_overriding.py -v
python -m pytest tests/test_special_abilities.py -v

# Test your main program
python project2_starter.py
```

### **GitHub Testing**

After pushing your code, check the **Actions** tab to see automated test results:

- ✅ **Inheritance Tests** (20 points) - Class structure and inheritance chain
- ✅ **Method Overriding Tests** (20 points) - Polymorphism and customized methods
- ✅ **Special Abilities Tests** (15 points) - Character abilities and composition

## 🎮 Example Usage

Your program should work like this:

```python
# Create characters (inheritance)
warrior = Warrior("Marcus")
mage = Mage("Aria")  
rogue = Rogue("Shadow")

# Polymorphism - same method, different behavior
for character in [warrior, mage, rogue]:
    character.attack(target)  # Each attacks differently

# Special abilities
warrior.power_strike(enemy)
mage.fireball(enemy)
rogue.sneak_attack(enemy)

# Composition
sword = Weapon("Iron Sword", 15)
sword.display_info()

# Test battle system (provided for you)
battle = SimpleBattle(warrior, mage)
battle.fight()
```

## 🎲 SimpleBattle System (Provided)

You have a **SimpleBattle** class already written that you can use to test your characters:

```python
battle = SimpleBattle(character1, character2)
battle.fight()  # Simulates a simple battle
```

**⚠️ DO NOT MODIFY the SimpleBattle class** - it's provided for testing your implementations.

## ⚠️ Important Notes

### **Protected Files**
- **DO NOT MODIFY** files in the `tests/` directory
- **DO NOT MODIFY** the `SimpleBattle` class
- Modifying protected files will result in automatic academic integrity violation

### **AI Usage Policy**
- ✅ **Allowed**: AI assistance for implementation, debugging, learning
- 📝 **Required**: Document AI usage in code comments
- 🎯 **Must be able to explain**: Every class and method during interview

## 🏆 Grading

- **Inheritance Tests (20%)**: Proper 3-level inheritance chain
- **Method Overriding (20%)**: Polymorphism and customized behaviors
- **Special Abilities (15%)**: Character-specific methods and composition
- **Code Quality (5%)**: Professional comments and documentation
- **Interview (40%)**: Code explanation and live coding

## 🎨 Bonus Creative Elements

Feel free to add your own creative touches for bonus points:
- Additional character classes beyond the three required
- More weapon types with different properties
- Enhanced special abilities with unique effects

## 🎮 HOW TO PLAY THE GAME

Game Overview
This is a TURN-BASED CHARACTER BATTLE SYSTEM where different character types
(Warrior, Mage, Rogue) fight each other using their unique abilities and stats.
Character Types & Playstyles
1️⃣ WARRIOR - Physical Tank
- Health: 120 (HIGHEST - can take the most damage)
- -Strength: 15 (HIGHEST - strongest physical attacks)
- Magic: 5 (LOWEST - weak spells)
- Playstyle: Heavy hitter, can tank damage
- Basic Attack: Strength + 10 damage
- Example: 15 + 10 = 25 damage per attack
- Special Ability - Power Strike: Strength × 2 + 15 damage
- Example: (15 × 2) + 15 = 45 damage
- ✓ Use when you need high burst damage
- ✓ Great for finishing off enemies
- Best Against: Mages (who have low health)
- 2️⃣ MAGE - Magical Specialist
- Health: 80 (LOWEST - fragile)
- Strength: 8 (LOWEST - weak physical attacks)
- Magic: 20 (HIGHEST - powerful spells)
- Playstyle: Powerful spells from range, fragile
- Basic Attack: Magic + 8 damage (Uses MAGIC not strength!)
- Example: 20 + 8 = 28 damage per attack
- Special Ability - Fireball: Magic × 2 + 10 damage
- Example: (20 × 2) + 10 = 50 damage
- ✓ Use for powerful magical attacks
- ✓ Great for burst damage
- Best Against: Warriors (to damage from distance)
- 3️⃣ ROGUE - Fast & Tricky
- Health: 90 (BALANCED)
- Strength: 12 (BALANCED)
- Magic: 10 (BALANCED)
- Playstyle: 30% chance for critical hits, weapon specialist
- Basic Attack: Strength + 8 damage with 30% critical chance
- Normal: 12 + 8 = 20 damage
- Critical (30% chance): 20 × 2 = 40 damage!
- Special Ability - Sneak Attack: Strength × 2 + 12 damage
-  Example: (12 × 2) + 12 = 36 damage
-  ✓ Use for guaranteed high damage
-  ✓ Always a critical hit (ignores 30% random chance)
- est Against: Mages and other Rogues
- Weapons & Bonuses
- Characters can equip weapons that provide DAMAGE BONUSES to ALL attacks:
- Iron Sword:       +10 damage
- Magic Staff:      +15 damage
- Poisoned Dagger:  +8 damage (Rogues get +3 extra = +11 total!)
- HOW WEAPONS WORK:
- Damage bonus adds to EVERY attack
- Rogues are specialists - they get extra bonus with daggers
- Example: Warrior with Iron Sword: 25 damage + 10 bonus = 35 damage!
- Battle System
- Turn Order:
- Step 1: Character 1 attacks Character 2
- Step 2: Character 2 attacks Character 1 (if still alive)
- Step 3: Battle ends when one character's health reaches 0
- Step 4: Winner is whoever has the most health remaining
## 📚 WHAT I LEARNED WORKING ON THIS PROJECT
- Core OOP Concepts:
- 1️⃣ INHERITANCE - Code Reuse Through Class Hierarchies
- What I Learned:
- Created a 3-level inheritance chain (Character → Player → Warrior/Mage/Rogue)
- Parent classes provide common functionality
- Child classes inherit and specialize
- Use super() to call parent constructors and methods
- Real-World Application:
- Instead of writing attack/defense code 3 times, wrote it once in
- Character and all subclasses inherit it
- Key Insight:
- Inheritance saves code and makes maintenance easier
- 2️⃣ METHOD OVERRIDING - Customizing Inherited Behavior
- What I Learned:
-  Subclasses can override parent methods with their own versions
- Same method name, different implementations
- Warrior, Mage, Rogue all override attack() differently:
- Warrior: strength + 10
- Mage: magic + 8 (uses different stat!)
- Rogue: strength + 8 with critical chance
- Also override display_stats() to show player-specific info
- Real-World Application:
- Each character type attacks uniquely without breaking the interface
- Key Insight:
- Method overriding lets subclasses customize behavior
- 3️⃣ POLYMORPHISM - Same Interface, Different Behaviors
What I Learned:
- SimpleBattle calls attack() without caring about character type:
- for character in [warrior, mage, rogue]:
-    character.attack(enemy)
- The CORRECT attack() runs automatically
- No if/else statements needed
- Code is flexible and extensible
- Real-World Application:
- Can add new character types and SimpleBattle works without changes!
- Key Insight:
- Polymorphism makes code flexible and maintainable
- 4️⃣ COMPOSITION - Objects Working Together
- What I Learned:
-  Characters HAVE weapons (not ARE weapons)
- eapon is a separate class not in the inheritance chain
- Characters can equip/unequip weapons dynamically
- More flexible than inheritance
- Real-World Application:
- Same weapon can be used by different character types
- Same dagger works for Warrior, Mage, or Rogue
- Key Insight:
- Composition is more flexible than inheritance for "has-a" relationships

## 🚀 BONUS FEATURES ADDED
- YES - BONUS FEATURES WERE ADDED! Here's what was included:
- 1️⃣ ENHANCED WARRIOR CLASS
- Feature: Armor Attribute
- Added self.armor = 5 to Warrior class
- Represents additional damage reduction
- Could be expanded later for damage reduction logic
- Example: future armor-based defense mechanics
- Why It's Useful:
- Makes Warriors feel more tanky with armor attribute
- 2️⃣ CRITICAL HIT SYSTEM FOR ROGUES
- Feature: 30% Chance for Double Damage on Basic Attacks
- Rogues have crit_roll = random.randint(1, 10)
- If roll <= 3: damage is doubled (30% chance)
- Added skill/luck element to combat
- Makes Rogue playstyle unique and interesting
- Code Example:
- crit_roll = random.randint(1, 10)
- is_critical = crit_roll <= 3
- if is_critical: damage = damage * 2
- Result: Rogues can get lucky and deal massive damage!
- Why It's Useful:
- Adds unpredictability and excitement to battles
- 3️⃣ WEAPON DAMAGE SCALING FOR CHARACTER TYPES
- Feature: Different Weapon Effectiveness Per Class
- Rogues get +3 extra bonus with weapons
- damage += self.weapon.damage_bonus + 3
- Other classes get standard bonus
- damage += self.weapon.damage_bonus
- Reflects Rogue specialty with weapons
- Incentivizes equipping weapons for Rogues
- Example Scenario:
- Warrior with sword: 25 + 10 = 35 damage
- Rogue with dagger: 20 + 8 + 3 = 31 damage
- Rogues benefit more from weapons despite lower strength!
- Why It's Useful:
- Makes weapon choice matter based on character class
- 4️⃣ COMPREHENSIVE BATTLE SYSTEM
- Feature: Simple but Complete Battle Simulation
- SimpleBattle class with full turn-based system
- Shows starting stats
- Displays each attack and damage
- Shows final health
- Determines winner
- Can be easily extended to multi-round battles
- urrent Features:
- 1 round battles
- Character vs Character combat
- Dynamic winner determination
- Clear, readable output
- Why It's Useful:
- Demonstrates polymorphism in action
- 5️⃣ EXTENSIBLE WEAPON SYSTEM
- Feature: Easy to Add New Weapons
- Weapon class is flexible
- Easy to create new weapons:
- sword = Weapon("Iron Sword", 15)
- Can add more weapon properties later
- Supports composition pattern perfectly
Example:
- sword = Weapon("Iron Sword", 15)
- staff = Weapon("Magic Staff", 15)
- dagger = Weapon("Poisoned Dagger", 10)
- Why It's Useful:
- Shows good extensible design
