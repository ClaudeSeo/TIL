#### General Notes
>  * a `tsc --init` puts your directory under `typescript` management so to say, the default settings allow you to compile all of your typescript files in the current directly into javascript with just `tsc`

#### Snippets
```typescript
// string type
let myName = 'Max'
// Type '55' is not assignable to type 'string'.
// reassigning to number throws err
// in regular JS, we can do this
// myName = 55
let hisName: string
hisName = 'John'

// number type
let myAge = 26.5
// Type '"potato"' is not assignable to type 'number'.
// myAge = 'potato'

// boolean type
let hasHobbies = true
// Type '1' is not assignable to type 'boolean'.
// hasHobbies = 1
let iAmAwesome: boolean
iAmAwesome = false

// explicity assign types
let myKoreanAge: number
myKoreanAge = 28
// Type '"28"' is not assignable to type 'number'.
// myKoreanAge = '28'

// array type
let foods = ['pizza', 'pineapple']
alert(foods[1])
// Type 'number[]' is not assignable to type 'string[]'.
// Type 'number' is not assignable to type 'string'.
// TypeScript is expecting an array of strings
// foods = [1, 2]

// the `any` type allows for relaxed reassignment
let sizes: any
sizes = ['a', 'b']
sizes = [1, 2]

// tuple type
// order is important in a tuple type
let identifier: [string, number] = ['Joseph', 26]
let cityState: [string, string] = ['Baltimore', 'Maryland']
let bankDeposit: [number, string] = [999, 'AJF26KAJASDF']

// enum type
enum Color { Red, Green, Blue }
let myColor: Color = Color.Green
console.log(myColor) // outputs: 1

// you can also explicity declare values for each enum
enum Car {
  Toyota     = 111,
  Hyundai    = 222,
  Mitsubishi = 333
}
console.log(Car.Toyota + Car.Hyundai + Car.Mitsubishi) // outputs: 666

// any type
// this is basically a regular, JavaSCript, dynamic type
let myVar: any
myVar = 'dog'
myVar = 123
myVar = false

// explicitly declaring return type of function
function returnMyAge (): number { return myAge }
alert('my age is: ' + returnMyAge())
// void type explicity declares that a function does not return anything
function justShout (): void { alert('just shout baby!') }
justShout()
// explicity declare function argument types
function add (num1: number, num2: number): number { return num1 + num2 }
alert(add(123, 321))
function subtract (num1: number, num2: number): number {
  return num1 - num2
}
alert(subtract(100, 1))
function concatStrings (string1: string, string2: string): string {
  return string1 + ' ' + string2
}
// function types
let myNewFunc: (num1: number, num2: number) => number
myNewFunc = subtract
alert(myNewFunc(200, 50))
let myNewFunc2: (str1: string, str2: string) => string
myNewFunc2 = concatStrings
alert(myNewFunc2('Hello', 'world!'))

// object types
// for objects in TypeScript, name of properties is important
let obj1 = { a: 1, b: 'hello' }
// Type '{}' is not assignable to type '{ 'a': number; 'b': number; }'.
// Property ''a'' is missing in type '{}'.
// obj1 = {}
// reassignment is okay so long as all the property names match up
obj1 = { a: 123, b: '321' }
// you can be explicit with the names and types of properties
let obj2: { x: number, y: number } = { x: 32.5, y: 124.2 }

```
