---
layout: project
type: project
image: img/cotton/oop-square.png
title: "Animal Farm OOP"
date: 2022
published: true
labels:
  - C
  - C++
  - Object-Oriented Programming
summary: "Project to design and implement classes and learn about OOP principles"
---

Developed an exhaustive database in Linux C++ via Object-Oriented Programming, storing 500 records and 10 attributes from scratch.

Used Bash & POSX Linux to design & execute highly-optimized algorithms in C, leading to 50% improvement in efficiency.

Created automated testing with BoostTests and CLion in C++ that reduced the number of development iterations by 30%, ensuring code accuracy & timely delivery of projects.

Animal.cpp:
```
using namespace std;

/// Default constructor
Animal::Animal() : gender(Gender::UNKNOWN_GENDER), weight(0.01F) {}

/// Constructor that takes only Gender as argument
Animal::Animal(Gender newGender) : gender(newGender), weight(0.01F) {}

/// Constructor that takes only Weight as argument
Animal::Animal(float newWeight) : gender(Gender::UNKNOWN_GENDER), weight(newWeight) {}

/// Constructor that takes both Weight and Gender as arguments
Animal::Animal(float newWeight, Gender newGender) : gender(newGender), weight(newWeight) {}


std::string_view Animal::getKingdom() const noexcept { // NOLINT(readability-convert-member-functions-to-static)
    return "Animalia";
}

float Animal::getWeight() const noexcept {
    return weight;
}

void Animal::setWeight(const float newWeight) {
    if (validateWeight(newWeight)) {
        weight = newWeight;
    }
}

bool Animal::validate() const noexcept {
    if (getKingdom().empty() || info().empty()) {
        return false;
    }
    if(!validateWeight(getWeight())){
        return false;
    }

    return true;
}

void Animal::dump() const noexcept {
    Node::dump();
    FORMAT_LINE_FOR_DUMP("Animal", "kingdom") << getKingdom() << std::endl;
    FORMAT_LINE_FOR_DUMP("Animal", "weight") << getWeight() << std::endl;
}

bool Animal::compare(Animal* lhs_animal, Animal* rhs_animal) const noexcept { // NOLINT(readability-convert-member-functions-to-static)
    if (lhs_animal->getKingdom() == rhs_animal->getKingdom()) {
        return lhs_animal->getWeight() < rhs_animal->getWeight();
    }
    return lhs_animal->getKingdom() < rhs_animal->getKingdom();
}

bool Animal::validateWeight(float weight) {
    return weight > 0;
}

Gender Animal::getGender() const noexcept {
    return gender;
}

void Animal::setGender(Gender newGender) {
    if (gender == Gender::UNKNOWN_GENDER) {
        gender = newGender;
    }
}
```
Link to repository: <a href="https://github.com/EE-205/ee205_animal_farm-kreyeshuynh"><i class="large github icon "></i>kreyeshuynh/ee205/animalfarm</a>
