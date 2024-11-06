# C-Sharp-Notes

## Datatypes
![{D974D263-11FF-4BFA-960D-45FCF64BD7DE}](https://github.com/user-attachments/assets/fd7d976c-b36e-4105-b214-6d47b1933e46)

## Type Casting
![image](https://github.com/user-attachments/assets/8c604b20-a448-4095-9d62-a9c8da712049)

- Converting Methods for Mannual typecasting:
  - string str = Convert.ToString(x);
  - int a = Convert.ToInt32(x);
  - double b = Convert.ToDouble(x);
  - long c = Convert.ToInt64(x);
  - bool st = Convert.ToBoolean(x);
 
## Input / Output

- Output: Console.WriteLine("HI");
- Input: Console.ReadLine()
// it waits for the input from user. But always give it in string datatype. Change it using type casting.

## Math

- Math.Max(a, b);
- Math.Min(a, b);
- Math.Abs(a);
- Math.Sqrt(a);
- Math.Round(a);

## String 
- str.Length
- str.ToUpper();
- str.ToLower();
- Concatenation (a+b);
- String Interpolation
  ```
  string firstName = "John";
  string lastName = "Doe";
  string name = $"My full name is: {firstName} {lastName}";
  Console.WriteLine(name);
  ```
- str.IndexOf('a');
- string abc = og_str.Substing(start_idx, no_of_elems);

## Conditional Statements
- if
- if..else
- else..if
- switch

## Loops
- do while
- while
- for
- foreach (string i in cars){...}

## Array 
- define the variable type with square brackets.
- e.g., string[] str, int[] arr
- int[] arr -> 1D array
- int[,] arr -> 2D array
- int[,,] arr -> 3D array
- Access in 2D array is like arr[0,3]
- Looping in 2D array is like 
```
// Also note that we have to use GetLength() instead of Length to specify how many times the loop should run:

int[,] numbers = { {1, 4, 2}, {3, 6, 8} };

for (int i = 0; i < numbers.GetLength(0); i++) 
{ 
  for (int j = 0; j < numbers.GetLength(1); j++) 
  { 
    Console.WriteLine(numbers[i, j]); 
  } 
} 
```
- Array.Sort(arr_name);

### Usefull functions on array is in System.Linq Namespace
- arr.Max();
- arr.Min();
- arr.Sum();


## Methods
- Methods/Functions only execute if they got called and are always inside the class.
- Parameters and Arguments:
  - Default Parameters
    ```
    static void Main(string country = "hue"){
      Console.WriteLine(country);
    }
    ```
  - Return Parameters
    - If we want to return the values from the function/Method then we have to use the required datatype instead of void in declaration and must include return type inside the function.
  - Named Arguments
      ```
      static void MyMethod(string child1, string child2, string child3) 
      {
        Console.WriteLine("The youngest child is: " + child3);
      }
      
      static void Main(string[] args)
      {
        MyMethod(child3: "John", child1: "Liam", child2: "Liam");
      }
      
      // The youngest child is: John
      ```
- We can do Method Overloading :- Multiple methods can have the smae name with different parameters.

# OOPS in C#

## Basics:
- A class is a template for objects, and an object is an instance of a class.
- Class:
  ```
  class Car {
    public string color = "red";
  }

  class Program{
    static void Main(string[] args){
      Car myObj = new Car();
      Console.WriteLine(myObj.color);
    }
  }  
  ```
  - Constructors make code simple and fast, Constructor overloading is allowed.

  ## Access Specifiers
  - ![image](https://github.com/user-attachments/assets/2e228471-12df-4919-9163-0b28bb00ee79)
 
  ## Encapsulation:
  - make class member private and give public get set methods to work with.
    ```
    class Person
    {
      private string name;

      public string Name
      {
        get { return name; }
        set { name = value; }
      }
    }

    //so for accessing 
    Console.WriteLine(obj.Name);
    obj.Name = "Rushi";
    ```
    - Or can make short-hand like
      ```
      class Person
      {
        public string Name
        {get; set;}
      }
      ```
## Inheritance
```
class Vehicle  // base class (parent) 
{
  public string brand = "Ford";  // Vehicle field
  public void honk()             // Vehicle method 
  {                    
    Console.WriteLine("Tuut, tuut!");
  }
}

class Car : Vehicle  // derived class (child)
{
  public string modelName = "Mustang";  // Car field
}

class Program
{
  static void Main(string[] args)
  {
    // Create a myCar object
    Car myCar = new Car();

    // Call the honk() method (From the Vehicle class) on the myCar object
    myCar.honk();

    // Display the value of the brand field (from the Vehicle class) and the value of the modelName from the Car class
    Console.WriteLine(myCar.brand + " " + myCar.modelName);
  }
}
```
  - Use **sealed** keyword, if we want to never inherit any sub-class from the class

## Polymorphism
- Polymorphism uses those methods to perform different tasks. This allows us to perform a single action in different ways.
- If we use same function then the base class function will over-write the other subclass functions.
- If we want to override the parent function then we have to use **virtual** and **override** keyword as follows.
  ```
  class Animal  // Base class (parent) 
  {
    public virtual void animalSound() 
    {
      Console.WriteLine("The animal makes a sound");
    }
  }
  
  class Pig : Animal  // Derived class (child) 
  {
    public override void animalSound() 
    {
      Console.WriteLine("The pig says: wee wee");
    }
  }
  
  class Dog : Animal  // Derived class (child) 
  {
    public override void animalSound() 
    {
      Console.WriteLine("The dog says: bow wow");
    }
  }
  
  class Program 
  {
    static void Main(string[] args) 
    {
      Animal myAnimal = new Animal();  // Create a Animal object
      Animal myPig = new Pig();  // Create a Pig object
      Animal myDog = new Dog();  // Create a Dog object
  
      myAnimal.animalSound(); // The animal makes a sound
      myPig.animalSound(); // The pig says: wee wee
      myDog.animalSound(); // The dog says: bow wow
    }
  } 
  ```
## Abstraction
- **Abstract class:** is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
- **Abstract method:** can only be used in an abstract class, and it does not have a body. The body is provided by the derived class (inherited from).

