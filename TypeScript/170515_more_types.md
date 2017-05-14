#### General Notes
>  * You can create complex, but relatively clear objects by being explicit about argument and return types

```typescript
// create complex objects
let obj3: { val1: number[], val2: (myString: string) => string[]} = {
  val1: [1, 2, 3],
  val2: function(myString: string) {
    return myString.split('')
  }
}
```

>  * You can create custom type aliases for cleaner code

```typescript
// you can create type aliases for cleaner code
type Complex = { val1: number[], val2: (myString: string) => string[]}
// create complex objects
let obj3: Complex = {
  val1: [1, 2, 3],
  val2: function(myString: string) {
    return myString.split('')
  }
}
```

>  * `union types` allow you to be more flexible with a variable's type without having to resort to the `any` type (which is too broad)

```typescript
// you can define union types for ambiguous situations
let myMixedAge: string | number = "26"
// you can reassign to a number because myMixedAge is of union type
myMixedAge = 26
```

>  * the `never` type allows you to explicitly define functions that will never return

```typescript
// the never type
function neverReturns(): never {
  throw new Error('An error, should never return...')
}
```

>  * `"strictNullChecks": true` in the compilerOptions in the tsconfig.json prevents variables that have been initialized from becoming null

```typescript
// coding challenge 1
type bankAccount = {money: number, deposit: (value: number) => void}
let bankAccount: bankAccount = {
  money: 2000,
  deposit(value: number) {
    this.money += value
  }
}
let myself: {name: string, bankAccount: bankAccount, hobbies: string[]} = {
  name: 'Max',
  bankAccount: bankAccount,
  hobbies : ['Sports', 'Cooking']
}
myself.bankAccount.deposit(3000)
console.log(myself)

```
