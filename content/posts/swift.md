+++
title = "Learn Swift"
date = "2020-04-21"
author = "Benjamin Cai"
description = "Learn some basic swift"
showFullContent = false
+++

### I start to learn swift 

Basically because do some ios development is the why I bought Macbook even it cannot play games

## Notes

###1. The Basics  ###
    ```Swift
    // nil is a special representation for no value 
    var apple = String ?
    // apple now is nil 
    ```

###2. Operators
```Swift
    for index in 1...5 {
    print("\(index) times 5 is \(index * 5)")
}
// 1 times 5 is 5
// 2 times 5 is 10
// 3 times 5 is 15
// 4 times 5 is 20
// 5 times 5 is 25
```
    There is half-range operator ..< and one sides operator [2..]

###3. String Interpolation

```Swift
let multiplier = 3
let message = "\(multiplier) times 2.5 is \(Double(multiplier) * 2.5)"
// message is "3 times 2.5 is 7.5"
```

some properties can passed into the list:
startIndex, endIndex

prefix(:) can used to find subString

### 4. Collection Types
Arrays are ordered collections of values.
Sets are unordered collections of **unique** values
Dictionaries are unordered collections of key-value associations

Array needs specification in the type of array
example:
```Swift 
var shoppingList: [String] = ["Egg", "Milk"]

// Array can iterate by for loop,  enumerated() method
```

### 5. Sets: 
A type must be hashable in order to be stored in a set

Set Type Syntax
```Swift
var letters = Set<Character>()
print("letters is of type Set<Character> with \(letters.count)items." )
// some functions in set: removeAll(), contains(:)
```

### 6. Dictionaries

Dictionary Type Syntax
```Swift
var namesOfIntergers = [Int:String]()
namesOfIntergers[16] = "sixteen"
// Specify both the key types and value types
// Some function for dictionary: updateValue(_:forKey:)
```
Remove a key-value pair from a dictionary
```Swift
airports["APL"] = "Apple International"
// "Apple International" is not the real airport for APL, so delete it
airports["APL"] = nil
// APL has now been removed from the dictionary
```
When you want to iterate over a dictionary using a for loop, also need to care about `(key,value)` tuple

Example:
```Swift
for (airpostcode, airportName) in airports {
    print("\(airportCode): \(airportName)")
}
// LHR: London Heathrow
// YYZ: Toronto Pearson
```

### 7. Control Flow ###

`for in loop`, `while loop` old-schooled

Repeat-while:
```Swift
repeat {
    // repeat doing something
}
while (condition)
```
Conditional Statements
`If, Switch`

### 8. Functions 

Function can return no value
For more returned values, can let function returns Tuple

```Swift
func minMax(array: [Int]) -> (min: Int, max: Int)? {
    if array.isEmpty { return nil }
    var currentMin = array[0]
    var currentMax = array[0]
    for value in array[1..<array.count] {
        if value < currentMin {
            currentMin = value
        } else if value > currentMax {
            currentMax = value
        }
    }
    return (currentMin, currentMax)
}
```

### 8. Closure
Closure expression
```Swift
reversedNames = names.sorted (by:{(s1:String,           s2:String) -> Bool in 
        return s1 > s2})
// The return type and parameters are written inside the curly braces
```
Shorthand Argument Names
`$0,$1,$2` refer to the values of the closure's arguments
`reversedNames = names.sorted(by: {$0 > $1})`
##### Capturing Values

```Swift
func makeIncrementer(forIncrement amount: Int) -> () -> Int {
    var runningTotal = 0
    func incrementer() -> Int {
        runningTotal += amount
        return runningTotal
    }
    return incrementer
}
```
#### Closures are reference Types

"Whenever you assign a function or a closure to a constant or a variable, you are actually setting that constant or variable to be a reference to the function or closure"

#### Escape Closures
`escaping` before the parameter's type to indicate that the closure is allowed to escape


### 9. Structures and Classes

```Swift
struct Resolution {
    var width = 0
    var height = 0
}
class VideoMode {
    var resolution = Resolution()
    var interlaced = false
    var frameRate = 0.0
    var name: String?
}
```

#### Structures and Enumerations are Value Types

```Swift
let hd = Resolution(width: 1920, height: 1080)
var cinema = hd
cinema.width = 2048
// This only change the cinema width, it is like pass by value
```

#### Classes are reference Types
```Swift
let tenEighty = VideoMode()
tenEighty.resolution = hd
tenEighty.interlaced = true
tenEighty.name = "1080i"
tenEighty.frameRate = 25.0

let alsoTenEighty = tenEighty
alsoTenEighty.frameRate = 30.0

// This change the frameRate of alsoTenEighty as well as tenEighty, passing with reference
```


### 10. Properties
Stored properties store constant and variable values as part of an instance;
Computed properties calculate a value
Lazy Stored Properties

Properties Observers:
    `willSet and didSet`
```Swift
class StepCounter {
    var totalSteps: Int = 0 {
        willSet(newTotalSteps) {
            print("About to set totalSteps to \(newTotalSteps)")
        }
        didSet {
            if totalSteps > oldValue  {
                print("Added \(totalSteps - oldValue) steps")
            }
        }
    }
}
let stepCounter = StepCounter()
stepCounter.totalSteps = 200
// About to set totalSteps to 200
// Added 200 steps
stepCounter.totalSteps = 360
// About to set totalSteps to 360
// Added 160 steps
stepCounter.totalSteps = 896
// About to set totalSteps to 896
// Added 536 steps
```