# Table of contents 


# Swift 4.2 Updates

[#9 Array Functions](https://github.com/apple-avadhesh/Swift-Updates#9-array-functions)     
[#8 Build configuration import testing](https://github.com/apple-avadhesh/Swift-Updates#8-build-configuration-import-testing)         
[#7 Target environment testing](https://github.com/apple-avadhesh/Swift-Updates#7-target-environment-testing)     
[#6 Derived collections of enum cases](https://github.com/apple-avadhesh/Swift-Updates#6-derived-collections-of-enum-cases)     
[#5 Warning and error diagnostic directives](https://github.com/apple-avadhesh/Swift-Updates#5-warning-and-error-diagnostic-directives)       
[#4 Random number generation and shuffling](https://github.com/apple-avadhesh/Swift-Updates#4-random-number-generation-and-shuffling)  
[#3 Boolean toggling](https://github.com/apple-avadhesh/Swift-Updates#3-boolean-toggling)  
[#2 In-place collection element removal](https://github.com/apple-avadhesh/Swift-Updates#2-in-place-collection-element-removal)  
[#1 Checking sequence elements match a condition](https://github.com/avadhesh12345678/Swift-Updates#1-checking-sequence-elements-match-a-condition)   

## [#9 Array Functions](https://github.com/apple-avadhesh)
 # 1. Map
 Use map to loop over a collection and apply the same operation to each element in the collection.
```swift
let arrayOfInt = [2,3,4,5,4,7,2]
let newArrUsingMap = arrayOfInt.map { $0 * 10 } // where $0 is enumrated object of an array/Sequence
// prints [20, 30, 40, 50, 40, 70, 20]
```
# 2. Filter
Use filter to loop over a collection and return an Array containing only those elements that match an include condition.
```swift
let arr = ["Hello","Bye","Halo"]
let filtered = arr.filter { $0.contains("lo") }
// prints ["Hello", "Halo"] 

```
# 3. Flatmap
Flatmap is used to flatten a collection of collections . But before flattening the collection, we can apply map to each elements.
Read it like : map + (Flat the collection)
```swift
[“abc”,”def”,”ghi”].flatMap { $0.uppercased() }
// output : ["A", "B", "C", "D", "E", "F", "G", "H", "I"] but only map function output would be output: [“ABC”, “DEF”, “GHI”]
```
 # All function in one line ;)
 ```swift
 let arrayOfArray = [[2,1],[4]]
let sum = arrayOfArray.flatMap{$0}.filter{$0 % 2 == 0}.map{$0 * $0}
print(sum.reduce(0, +)) //20
 ```
## [#8 Build configuration import testing](https://github.com/apple-avadhesh)

```swift
#if canImport(SpriteKit)
   // this will be true for iOS, macOS, tvOS, and watchOS
#else
   // this will be true for other platforms, such as Linux
#endif
```

## [#7 Target environment testing](https://github.com/apple-avadhesh)

```swift
#if targetEnvironment(simulator)
   // code for the simulator here
#else
   // code for real devices here
#endif
```

## [#6 Derived collections of enum cases](https://github.com/apple-avadhesh)

```swift
enum Developers: CaseIterable {
    case vishal, avadhesh, sandeep, anil
}
```
```swift
for developer in Developers.allCases {
    print("iOS Developer - \(developer).")
}
```
```swift

```

## [#5 Warning and error diagnostic directives](https://github.com/apple-avadhesh)

```swift
func encrypt(_ string: String, with password: String) -> String {
    #warning("This is terrible method of encryption")
    return password + String(string.reversed()) + password
}

struct Configuration {
    var apiKey: String {
        #error("Please enter your API key below then delete this line.")
        return "Enter your key here"
    }
} 
```


## [#4 Random number generation and shuffling](https://github.com/apple-avadhesh)

```swift
let randomInt = Int.random(in: 1..<5)

Similar methods exist for Float, Double, and CGFloat:

let randomFloat = Float.random(in: 1..<10)
let randomDouble = Double.random(in: 1...100)
let randomCGFloat = CGFloat.random(in: 1...1000)
```

## [#3 Boolean toggling](https://github.com/apple-avadhesh)

```swift
var loggedIn = false
loggedIn.toggle()
```

## [#2 In-place collection element removal](https://github.com/apple-avadhesh)

```swift
var developers = ["Avadhesh", "Vishal", "Sandeep", "Anil", "Prashant"]
developers.removeAll { $0.hasPrefix("Sandeep") }
print(developers)
// "["Avadhesh", "Vishal", "Anil", "Prashant"]\n"
```

## [#1 Checking sequence elements match a condition](https://github.com/apple-avadhesh)

```swift
let scores = [80, 88, 95, 92]
let passed = scores.allSatisfy { $0 >= 85 }
```
