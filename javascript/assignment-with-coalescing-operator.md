When using the null coalescing operator to assign a value an assignment can also take place in the
right hand operand:

```csharp
string unassigned;
Console.WriteLine(unassigned ?? (unassigned = "assigned value"));
```

Outputs: `assigned value`

But the string `unassigned` also now contains that value:

```csharp
Console.WriteLine(unassigned);
```

Outputs: `assigned value`

