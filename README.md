# Comprehensive TypeScript Cheat Sheet

TypeScript is a statically typed superset of JavaScript, offering optional static typing, classes, and interface. It's designed for development of large applications and transpiles into JavaScript.

## Basic Types
- **Boolean:** `let isDone: boolean = false;`
- **Number:** `let decimal: number = 6;`
- **String:** `let color: string = "blue";`
- **Array:** `let list: number[] = [1, 2, 3];` or `let list: Array<number> = [1, 2, 3];`
- **Tuple:** `let x: [string, number] = ["hello", 10];`
- **Enum:** `enum Color {Red, Green, Blue}` then `let c: Color = Color.Green;`
- **Any:** `let notSure: any = 4;`
- **Void:** `function warnUser(): void { console.log("This is my warning message"); }`
- **Null and Undefined:** `let u: undefined = undefined; let n: null = null;`
- **Never:** `function error(message: string): never { throw new Error(message); }`

## Interfaces
- **Basic Interface:** `interface LabelledValue { label: string; }`
- **Optional Properties:** `interface SquareConfig { color?: string; width?: number; }`
- **Readonly properties:** `interface Point { readonly x: number; readonly y: number; }`
- **Function Types:** `interface SearchFunc { (source: string, subString: string): boolean; }`
- **Indexable Types:** `interface StringArray { [index: number]: string; }`

## Classes
- **Basic Class:** `class Greeter { greeting: string; constructor(message: string) { this.greeting = message; } greet() { return "Hello, " + this.greeting; } }`
- **Inheritance:** `class Animal { move(distanceInMeters: number = 0) { console.log(`Animal moved ${distanceInMeters}m.`); } }`
- **Access Modifiers:** `public`, `private`, `protected`
- **Getters/Setters:** `get fullName(): string { return this.firstName + " " + this.lastName; }`
- **Abstract Classes:** `abstract class Animal { abstract makeSound(): void; move(): void { console.log("roaming the earth..."); } }`

## Functions
- **Named Function:** `function add(x, y) { return x + y; }`
- **Anonymous Function:** `let myAdd = function(x, y) { return x + y; };`
- **Function Types:** `interface SearchFunc { (source: string, subString: string): boolean; }`
- **Optional and Default Parameters:** `function buildName(firstName: string, lastName?: string) { ... }`
- **Rest Parameters:** `function buildName(firstName: string, ...restOfName: string[]) { ... }`

## Generics
- **Generic Function:** `function identity<T>(arg: T): T { return arg; }`
- **Generic Interface:** `interface GenericIdentityFn<T> { (arg: T): T; }`
- **Generic Class:** `class GenericNumber<T> { zeroValue: T; add: (x: T, y: T) => T; }`
- **Generic Constraints:** `interface Lengthwise { length: number; } function loggingIdentity<T extends Lengthwise>(arg: T): T { console.log(arg.length); return arg; }`

## Enums
- **Numeric Enums:** `enum Direction {Up = 1, Down, Left, Right}`
- **String Enums:** `enum Direction { Up = "UP", Down = "DOWN", Left = "LEFT", Right = "RIGHT" }`
- **Computed and Constant Members**

## Advanced Types
- **Union Types:** `function padLeft(value: string, padding: string | number) { ... }`
- **Intersection Types:** `type Combined = Drivable & Flyable;`
- **Type Guards:** `function isFish(pet: Fish | Bird): pet is Fish { return (<Fish>pet).swim !== undefined; }`
- **Type Assertions:** `let someValue: any = "this is a string"; let strLength: number = (<string>someValue).length;`
- **Literal Types:** `type Easing = "ease-in" | "ease-out" | "ease-in-out";`

## Modules
- **Exporting a module:** `export interface StringValidator { isAcceptable(s: string): boolean; }`
- **Importing a module:** `import { StringValidator } from "./StringValidator";`

## Namespaces
- **Internal modules:** `namespace Validation { export interface StringValidator { isAcceptable(s: string): boolean; } }`

## Decorators
- **Class Decorator:** `@sealed`
- **Method Decorator:** `@enumerable(false)`
- **Accessor Decorator:** `@configurable(false)`
- **Property Decorator:** `@format("Hello, %s")`
- **Parameter Decorator:** `@required`
