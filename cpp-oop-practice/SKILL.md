---
name: cpp-oop-practice
description: Generates easy, medium, and hard C++ OOP practice problems with a consistent personal coding style. Applies the same style when generating, explaining, or revising C++ code, starter code, hints, and solutions. Recognizes difficulty-only practice requests such as "Give me a hard problem" in this C++ practice context.
---

# C++ OOP Practice

Keep C++ code consistent across requests and difficulty levels. Apply these preferences to every C++ snippet, including examples, hints, starter code, and complete solutions, unless the user explicitly requests a different style.

## User preferences

- I prefer OOP. Always include constructors
- Fields will start with a small letter. Not \_
- Prioritize conditional statements and loops and avoid shortcuts
- Don't include code comments
- Use namespace std
- If possible, use STL instead of making your own data structure and algorithm

## Consistent C++ style

- Organize solutions around classes with meaningful responsibilities. Explicitly write a constructor for every class or struct you introduce and initialize its fields. Use private fields and public constructors and methods by default.
- Initialize fields with constructor member initializer lists, such as `Book(string bookTitle) : title(bookTitle), isBorrowed(false)`. Place the initializer list on the next line, indented one level beyond the constructor signature, with opening and closing braces on their own lines as shown in the example below. Do not replace member initialization with assignments inside the constructor body. Keep the body empty unless additional logic is needed, and list initializers in field declaration order.
- Name classes in PascalCase. Name fields, local variables, parameters, and methods in lowerCamelCase. Fields start with a lowercase letter, with no leading or trailing underscore and no `m_` prefix. Use descriptive names.
- Use four spaces for indentation, opening braces on their own lines, and braces for every conditional and loop body. Keep one statement per line.
- Include `using namespace std;` after the headers in complete programs. Include the individual standard headers needed by the program.
- Favor clear `if`, `else if`, `else`, `switch`, `for`, and `while` statements. Avoid ternary operators, macros for ordinary logic, compressed one-liners, clever side effects, and lambdas that hide simple control flow. Use explicit types when they keep beginner code easier to follow.
- Prefer STL containers such as `vector`, `string`, `map`, `set`, `queue`, and `stack`, and standard algorithms such as `sort`, when appropriate. Standard library use is compatible with the preference for readable control flow: use loops for ordinary traversal, validation, and business logic; use library algorithms for established operations. Implement a custom structure or algorithm only when required by the exercise or unavailable in the STL.
- Do not put `//` or block comments in generated C++ code. Place explanations in prose outside code blocks.
- Use portable C++11 by default. Ensure all syntax and standard library features are available in C++11 unless the user explicitly requests another version. Keep the same naming, brace placement, and explicit control flow at every difficulty level.

Use this small example as a formatting anchor; adapt the design to each problem:

```cpp
#include <iostream>
#include <string>

using namespace std;

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

int main()
{
    Student student("Ana", 80);

    if (student.hasPassed())
    {
        cout << "Passed" << endl;
    }
    else
    {
        cout << "Failed" << endl;
    }

    return 0;
}
```

## Practice prompts

Recognize these prompts and equivalent wording:

1. "Give me an easy OOP problem" → Create one easy C++ OOP problem.
2. "Give me a medium OOP problem" → Create one medium C++ OOP problem.
3. "Give me a hard problem" → Create one hard C++ OOP problem when this skill is invoked or the conversation is about C++ practice. Do not reinterpret an unrelated hard problem request as C++ practice.

Choose a reasonable topic without asking the user to choose. Follow any topic they supply. Increase reasoning and design complexity as difficulty rises while preserving the same readable code style:

- **Easy:** One main class, an explicit constructor, a few private fields and public methods, simple decisions, and basic iteration when useful.
- **Medium:** Interacting classes, composition, STL collections, searching or sorting, and validation involving several rules.
- **Hard:** A larger object model with interacting rules, meaningful edge cases, and efficient STL use. Include inheritance or polymorphism only when the problem benefits from it; difficulty does not require every OOP feature or obscure syntax.

## Response format

For a difficulty prompt, provide one problem followed by a complete solution by default:

1. Give the problem title and difficulty, a clear scenario, required behavior, and relevant constraints or validation rules.
2. Describe the classes, fields, constructors, and methods the learner should implement without requiring unnecessary getters, setters, or inheritance.
3. Show an example interaction or sample input and output consistent with the specification and solution.
4. Provide a complete, compilable C++ solution, including required headers and `main`, in the prescribed style.
5. Briefly explain the OOP design and core logic outside the code block.

If the user asks for only a problem, a hint, starter code, or a solution, provide only the requested material. Preserve their opportunity to solve the exercise: do not reveal a full solution in response to a hint request. When continuing an existing exercise, keep its specification and code style consistent.

Before responding, check that every introduced class has an explicit constructor using member initializer lists, fields follow lowerCamelCase without underscores, code has no comments, complete programs use `using namespace std;`, all code is compatible with C++11 unless another version was requested, and sample behavior agrees with the code. Check basic boundary cases and the fit between the problem and its difficulty.
