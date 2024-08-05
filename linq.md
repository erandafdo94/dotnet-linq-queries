# LINQ Methods

## 1. Where

Filters a sequence of values based on a predicate.

**Example:**

```csharp
int[] numbers = { 1, 2, 3, 4, 5, 6 };
var evenNumbers = numbers.Where(n => n % 2 == 0);

foreach (var num in evenNumbers)
{
    Console.WriteLine(num);
}
```

**Output**

```text
4
5
```

## 2. Select

Projects each element of a sequence of a new form.

**Example:**

```csharp
int[] numbers = { 2, 3, 4, 5 };
var result = numbers.Select(n => n * n);

foreach (var number in result)
    Console.WriteLine(number);
```

**Output**

```text
4
6
8
10
```

## 3. OrderBy

Sorts the elements of a sequence in ascending order.

**Example:**

```csharp
string[] names = { "Tom", "Dick", "Harry" };
var result = names.OrderBy(n => n);

foreach (var name in result)
    Console.WriteLine(name);
```

**Output**

```text
Dick
Harry
Tom
```

## 4. OrderByDescending

Sorts the elements of a sequence in ascending order.

**Example:**

```csharp
string[] names = { "Tom", "Dick", "Harry" };
var result = names.OrderByDescending(n => n);

foreach (var name in result)
    Console.WriteLine(name);
```

**Output**

```text
Tom
Harry
Dick
```

## 4. OrderByDescending

Sorts the elements of a sequence in ascending order.

**Example:**

```csharp
string[] names = { "Tom", "Dick", "Harry" };
var result = names.OrderByDescending(n => n);

foreach (var name in result)
    Console.WriteLine(name);
```

**Output**

```text
Tom
Harry
Dick
```

## 5. GroupBy

Groups elements into a sequence.

**Example:**

```csharp
string[] words = { "cat", "dog", "bird", "tiger", "bear" };
var result = words.GroupBy(n => n.Length);

foreach (var group in result)
{
    Console.WriteLine($"Length: {group.Key}");
    foreach (var word in group)
        Console.WriteLine(word);
}
```

**Output**

```text
Length: 3
cat
dog
Length: 4
bird
bear
Length: 5
tiger

```

## 5. Join

Joins two sequences based on a key.

**Example:**

```csharp
var people = new[]
{
    new { Name = "Tom", Age = 23 },
    new { Name = "Dick", Age = 30 },
    new { Name = "Harry", Age = 25 }
};

var jobs = new[]
{
    new { Name = "Tom", Job = "Developer" },
    new { Name = "Dick", Job = "Manager" }
};

var result = people.Join(jobs, p => p.Name, j => j.Name, (p, j) => new { p.Name, p.Age, j.Job });

foreach (var person in result)
    Console.WriteLine($"{person.Name}, {person.Age}, {person.Job}");

```

**Output**

```text
Tom, 23, Developer
Dick, 30, Manager
```
