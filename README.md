## Mid Unit-1 Review


## Strings

1. **Given a String, return a String with each letter uppercased**

Input: `Hello, there`

Output: `HELLO, THERE`
```
for i in input {
    capitalInput += i.uppercased()
}
print(capitalInput)
```

2. **Given a String, return a String alternating between uppercase and lowercase letters**


Input: `Hello, there`

Output: `HeLlO, tHeRe`
```
var mixedCase = " "

for (i, v) in input.enumerated() {
    if i % 2 == 0 {
    mixedCase += v.uppercased()
}else{
    mixedCase += v.lowercased()
    }
}
print(mixedCase)
```

3. **Given a String, return a String with all occurrences of a given letter removed**

Input: `Hello, there`

Output: `Hllo, thr`
```
var noE = " "

for i in input {
    if i == "e" {
    continue
}else{
    noE += String(i)
    }
}
print(noE)
```

## Arrays


1. **Given an array of type [Int], return the largest element**

Input: `[1,5,2,4,1,4]`

Output: `5`
```
var arrayInput = [1,5,2,4,1,4]
var max = 0

for i in arrayInput {
    if i > max {
    max = i
    }
}
print(max)
```

2. **Given an array of type [Int], return the smallest element**

Input: `[1,5,2,4,1,4]`

Output: `1`
```
var arrayInput1 = [1,5,2,4,1,4]
var min = 1000

for i in arrayInput1 {
    if i < min {
    min = i
    }
}
print(min)
```

3. **Given an array of type [Int], return its sum**

Input: `[1,5,2,4,1,4]`

Output: `17`
```
var arrayInput2 = [1,5,2,4,1,4]
var sum = 0

for i in arrayInput2 {
    sum += i
}
print(sum)
```
4. **Given an array of type [Double], return its average**

Input: `[3,4.5,7.5,2,1]`

Output: `3.6`
```
var arrInput = [3,4.5,7.5,2,1]
var average : Double = 0
var arrCount = arrInput.count

for i in arrInput {
    average += (i)
}
print(average/Double(arrInput.count))
```
5. **Given an array of type [Double] and a Double, return the sum of all numbers in the array greater than a given number**

Input: `[3,4.5,7.5,2,1], 3`

Output: `12`
```
var inputArray = [3,4.5,7.5,2,1]
var sum = 0.0
for i in inputArray {
    if i > 3 {
    sum += i
    }
}
print(sum)
```

6. **Given an array of type [Double], return the product of all the elements**

Input: `[3,4.5,7.5,2,1]`

Output: `202.5`
```
var product = 1.0
    for i in inputArray {
    product *= i
}
print(product)
```
7. **Given an array of type [Int], return the second smallest value in the array**

Input: `[3,6,1,9,4,8]`

Output: `3`
```
var inputArray2 = [3,6,1,9,4,8]
var min = 1000
var min2 = 1000

for i in inputArray2 {
    if i < min {
    min2 = min
    min  = i
    }
}
print(min)
print(min2)
```

## Optionals

1. **Given an array of type [String?] return an array of [String] removing all nil values**

Input: `[nil, "We", "come", nil, "in", "peace"]`

Output: `["We", "come", "in", "peace"]`
```
var input = [nil, "We", "come", nil, "in", "peace"]
var output = [String]()

for i in input {
    if i == nil {
    continue
}
output += [i!]
}

print(output)
```

2. **Given an array of type [String?]? return an array of [String] removing all nil values**

Input: `nil`

Output: `[]`
```
var input2: Optional = [nil,"i"]
var output2 = [String]()

for i in input2! {
    if i == nil {
    continue
}
output2 += [i!]
}

print(output2)
```

3. **Given an array of type [Int?] return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `[4, nil, 9, 5, nil]`

Output: `18`
```
var input3 = [4, nil, 9, 5, nil]
var output3 = 0

for i in input3 {
    guard i != nil else {
    continue
}
output3 += i!
}

print(output3)
```
4. **Given an array of type [Int?]? return the sum of all non-nil values.  Use guard statements in your solution.**

Input: `nil`

Output: `0`
```
var input4: Optional = [nil,1]
var output4 = 0

for i in input4! {
    guard i != nil else {
    continue
}
output4 += i!
}

print(output4)
```

5. **Given an array of type [Int?] and an optional Int, return the sum of all values not equal to the given number.  If the given number is nil, return the sum of all non-nil values.**

Input: `[1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3], 1`

Output: `24`
```
var input5 = [1, 1, nil, 3, 5, nil, 1, nil, 3, 5, nil, 5, nil, 3]
var output5 = 0

for i in input5 {
    if i == 1 || i == nil {
    continue
}
output5 += i!
}

print(output5)
```

## Dictionaries

1. **Given an array of type [String], return a copy of the array with all duplicate values removed**

Input: `["apple", "apple", "banana", "banana", "banana", "cake", "cake"]`

Output: `["apple", "banana", "cake"]`
```
var input = ["apple", "apple", "banana", "banana", "banana", "cake", "cake"]
var output: [String:Int] = [:]

for (i,v) in input.enumerated() {
    output[v] = i
}

print(output)
```

2. **Given a String, find the most frequently occurring letter**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output: `t`
```
var string = "Never trust a computer you can't throw out a window ~ Steve Wozniak"
var alphabet = "abcdefghijklmnopqrstuvwxyz"
var stringArray = Array(string)
var dict: [Character:Int] = [:]
var highestFrequencyTracker = 0
var mostFrequentLetter = String()


for char in stringArray where alphabet.contains(char.lowercased()) {
    if dict.keys.contains(char) {
    dict.updateValue(dict[char]! + 1, forKey: char)
} else {
    dict[char] = 1
}
}


for (key,value) in dict {
    if highestFrequencyTracker < value {
    highestFrequencyTracker = value
    mostFrequentLetter = String(key)
    }
}

print(mostFrequentLetter)



```

3. **Given an array of type [Int], return a copy of the array that contains only elements that appear at least twice**

Input: `[1,1,2,3,3,3,4,5,6,6,7]`

Output: `[1,3,6]`

4. **Given a String, find the second most frequently occurring letter in a string**

Input: `Never trust a computer you can't throw out a window ~ Steve Wozniak`

Output `o`


## Closures

1. **Given an array of type [String], return an array that contains the Strings sorted alphabetically with capital letters first (Swift will do that part automatically)**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "a", "a", "can\'t", "computer", "out", "throw", "trust", "window", "you"]`
```
let input = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.sorted(by: <))
```

2. **Given an array of type [String], return an array that contains the Strings sorted by length**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["a", "a", "you", "out", "Never", "trust", "can\'t", "throw", "window", "computer"]`
```
let input2 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input.sorted(by: {$0.count < $1.count}))
```


3. **Given an array of type [String], return an array containing all Strings at least 4 characters long**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `["Never", "trust", "computer", "can\'t", "throw", "window"]`
```
var input3 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input3.filter {$0.count >= 4})
```

4. **Given an array of type [String], return a String containing all of the Strings from the array combined and separated by spaces.  Do this first without using the `joined(separator:) method`**

Input: `["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]`

Output: `Never trust a computer you can't throw out a window`
```
let input4 = ["Never", "trust", "a", "computer", "you", "can't", "throw", "out", "a", "window"]

print(input4.reduce("", {$0 + " " + $1}))
```

## Enums


1. **Given an array of type [Int] and an instance of NumberType (defined below), return an array containing only all the even or odd numbers.**

```swift
enum NumberType {
    case even
    case odd
}
```

Input: `[1,2,3,4,5,6], NumberType.odd`

Output: `[1,3,5]`
```
enum NumberType {
    case even
    case odd
    func allEvenOrOdd(intArray:[Int]) -> [Int]{
        var array = [Int]()
        switch self {
        case .odd:
            for i in intArray {
                if i % 2 != 0 {
                   array += [i]
                }
            }
        case .even:
            for i in intArray {
                if i % 2 == 0 {
                array += [i]
                }
            }
        }
        return array
    }
}
var odd = NumberType.odd.allEvenOrOdd(intArray: [1,2,3,4,5,6])
var even = NumberType.even.allEvenOrOdd(intArray: [1,2,3,4,5,6])
print(odd)
print(even)
```

2. **Given a String and an instance of StringType (defined below), return the String either lowercased or uppercased**

```swift
enum StringType {
    case lowercase
    case uppercase
}
```

Input: `"Design is not just what it looks like and feels like. Design is how it works", .uppercase`

Output: ``"DESIGN IS NOT JUST WHAT IT LOOKS LIKE AND FEELS LIKE. DESIGN IS HOW IT WORKS"``
```
enum StringType {
    case lowercase
    case uppercase

    func allCapsOrLower(string: String) -> String {
        var newString = ""
        switch self {
        case .uppercase:
            for i in string {
                newString += String(i.uppercased())
                }
        case .lowercase:
            for i in string {
                newString += String(i.lowercased())
            }
        }
return newString
    }
}

var string = "Design is not just what it looks like and feels like. Design is how it works"
var caseType = StringType.uppercase

print(caseType.allCapsOrLower(string: string))
```


3. **Given an array of type [FileStatus] (defined below) and an Int, return an array containing only files that were saved more than that many times**

```swift
enum FileStatus: CustomStringConvertible {
    case unsaved
    case saved(numberOfVersions: Int)
    var description: String {
        switch self {
        case .unsaved: return "Unsaved File"
        case let .saved(numberOfVersions): return "File that has been saved \(numberOfVersions) times"
        }
    }
}
```

Input: `[FileStatus.saved(numberOfVersions: 5), FileStatus.saved(numberOfVersions: 3), FileStatus.saved(numberOfVersions: 8)], 4`

Output: `[File that has been saved 5 times, File that has been saved 8 times]`
