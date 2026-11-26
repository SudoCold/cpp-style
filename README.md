# C++ OOP Practice

This repository contains a coding practice skill for generating C++ object-oriented programming exercises and solutions in a consistent, beginner-friendly style.

## What It Provides

- Easy, medium, and hard C++ OOP practice problems
- Complete compilable C++ solutions
- Consistent PascalCase and lowerCamelCase naming
- Constructor-based class initialization
- Beginner-friendly control flow
- STL containers and algorithms when appropriate
- C++11-compatible examples by default

## Repository Structure

- `cpp-oop-practice/SKILL.md` contains the instructions and coding style used to generate C++ exercises.
- `cpp-oop-practice/agents/openai.yaml` contains the skill metadata and default prompt.
- `.gitignore` excludes local environment and certificate files.

## Coding Style

Generated C++ code follows these principles:

- Classes and structs have explicit constructors.
- Fields use lowerCamelCase and start with a lowercase letter.
- Code uses four-space indentation and opening braces on their own lines.
- `using namespace std;` is included in complete programs.
- STL containers and algorithms are preferred when they fit the problem.
- The generated code avoids comments and unnecessary shortcuts.
- Complete solutions use portable C++11 syntax unless another standard is requested.

## Example

```cpp
class Student
{
private:
    string name;
    int score;

public:
    Student(string studentName, int studentScore)
        : name(studentName), score(studentScore)
    {
    }

    bool hasPassed() const
    {
        if (score >= 75)
        {
            return true;
        }
        else
        {
            return false;
        }
    }
};
```
