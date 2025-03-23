# ConsoleApp Check Nullable in .NET C#

C# Null Safety: Write Robust and Error-Free Code

https://towardsdev.com/c-null-safety-write-robust-and-error-free-code-72ad127fff41

## Nullable Reference Types (NRTs)
```
string name = null; // Warning: Assignment of null to non-nullable reference type
string? nullableName = null; // No warning
```

## Null-Coalescing Operator (??)
```
string name = null;
string displayName = name ?? "Guest";
Console.WriteLine(displayName); // Output: Guest
```

## Null-Conditional Operator (?.)
```
string[]? names = null;
int? count = names?.Length; // No exception, count is null
Console.WriteLine(count); // Output: (null)
```

## Null-Forgiving Operator (!)
```
string name = null!; // Suppresses null warning
Console.WriteLine(name.Length); // Runtime exception!
```

## ArgumentNullException
```
public void PrintName(string name)
{
    if (name is null)
    {
        throw new ArgumentNullException(nameof(name));
    }
    Console.WriteLine(name);
}
```

## Using Nullable Reference Types

Using Nullable Reference Types

No runtime errors occur in case you activate NRTs for your project and introduce reference types to mark the nullability.

```
#nullable enable
public class User
{
    public string Name { get; set; } // Non-nullable
    public string? Email { get; set; } // Nullable
}
```

## Handling Null Values Gracefully

Use the null-coalescing operator to set default values:
```
string? userInput = null;
string result = userInput ?? "Default Value";
Console.WriteLine(result); // Output: Default Value
```

## Safe Member Access
```
User? user = null;
string email = user?.Email ?? "No email provided";
Console.WriteLine(email); // Output: No email provided
```

## Explicit Null Checks
```
public void SendEmail(string email)
{
    if (email is null)
    {
        throw new ArgumentNullException(nameof(email));
    }
    // Send email logic
}
```

* **API Design**: It improves its own documentation and adheres to consumer safety by making sure that APIs acknowledge the fact that they sometimes return nulls.
* **Databases**: working with possibly incomplete datasets generally requires nullable types to deal with missing data in a graceful manner.

## 📌 Expert tips for null safety
* Activate null-ref types to intercept null problems at compile time: Enable Turn on NRTs on your project.
* Default to Default Values: Use null-coalescing operators, in turn, to handle any null gracefully.
* Overuse of Null Forgiveness Operator(!): The null-forgiving operator hides possible bugs, so do not abuse it.
* Validate inputs: Always validate arguments /string, cant restrain conditional modification/ to make certain that they are not null.
* Employ Null Safe Supporting Libraries-Several modern libraries and frameworks are now being built considering null safety.

## 🔑 Main Points
* Null safety is provided in C#, where nullable reference types, null coalescing operators, and null conditional operators(?.) serve as powerful mainstays.
* If you enable the nullable reference types (#nullable), you will be catching the null error as a compile-time error.
* Employ null-coalescing (??) and null-conditional operators(?.) to make a point of helping handle the null values.
* The power demonstrated in null safety by practical examples, e.g. user input handling, safe object member access, and explicit null checks, is the most convincing.
