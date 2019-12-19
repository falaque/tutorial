Some Concepts on F#
=====================
#### List operations
```F#
let twoToFive = [2;3;4;5]        // Square brackets create a list with
                                 // semicolon delimiters.
let oneToFive = 1 :: twoToFive   // :: creates list with new 1st element
// The result is [1;2;3;4;5]

let zeroToFive = [0;1] @ twoToFive   // @ concats two lists

//Range operator
let list3to7 = [3..7] //[3;4;5;6;7]
let listOdd3to10 = [3..2..10] //[3;5;7;9]
let list = [3..4..15] //[3;7;11;15]

```
#### Lambda Expressions: The fun Keyword
 > fun parameter-list -> expression
```F#
// Lambda expressions with parameter lists.
fun a b c -> ...
fun (a: int) b c -> ...
fun (a : int) (b : string) (c:float) -> ...

// A lambda expression with a tuple pattern.
fun (a, b) -> …

// A lambda expression with a list pattern.
fun head :: tail -> …

let list = List.map (fun i -> i + 1) [1;2;3]
printfn "%A" list

//new list with elements squared using lambda expression.
let squareList list = 
  List.map (fun i-> i*i) list
//Test
squareList [2;3]

```
#### Pattern Matching:
```F#
//matching tuples directly
let x, y =  (1,2)
let firstPart, secondPart, _ =  (1,2,3)  // underscore means ignore

//matching lists directly
let elem1::elem2::rest = [1..10]       // ignore the warning for now

//matching lists inside a match..with
let listMatcher aList = 
    match aList with
    | [] -> printfn "the list is empty" 
    | [firstElement] -> printfn "the list has one element %A " firstElement 
    | [first; second] -> printfn "list is %A and %A" first second 
    | _ -> printfn "the list has more than two elements"

listMatcher [1;2;3;4]
listMatcher [1;2]
listMatcher [1]
listMatcher []

//You can also bind values to the inside of complex structures such as records.
//In the following example, we will create an “Address” type, and then a “Customer” type which contains an address. Next, we will create a customer value, and then match various properties against it.

// create some types
type Address = { Street: string; City: string; }   
type Customer = { ID: int; Name: string; Address: Address}   

// create a customer
let customer1 = { ID = 1; Name = "Bob"; 
      Address = {Street="123 Main"; City="NY" } }     

// extract name only
let { Name=name1 } =  customer1 
printfn "The customer is called %s" name1

// extract name and id
let { ID=id2; Name=name2; } =  customer1 
printfn "The customer called %s has id %i" name2 id2

// extract name and address
let { Name=name3;  Address={Street=street3}  } =  customer1   
printfn "The customer is called %s and lives on %s" name3 street3


```

Ref: https://fsharpforfunandprofit.com/posts/conciseness-pattern-matching/
#### Copy a data structure:
``` F#
type PersonalName = {FirstName:string; LastName:string}
// immutable person
let john = {FirstName="John"; LastName="Doe"}

//copying john to alice
let alice = {john with FirstName="Alice"}
```

Other stuff:
------------
#### Comments
```F#
(* This is a multi-line comment *)
// This is a single-line comment
```

F# Tutorial
------------

* Create a sum function and print result:

* Sum of items in list(using recursion):
```F#
let rec sumList1 list =
    match list with
        | [] -> 0
        | first::rest -> first + (sumList1 rest)

```
* Sum of items in list(using fold):
```F#
let sumList2 list =
    let initVal = 0

    let action sumSoFar x  = sumSoFar + x;
    list |> List.fold action 0

sumList2 []
sumList2 [-1]
sumList2 [-1;2;3]
```

* Reverse a list:
```F#
let rec ReverseList list = 
  match list with
   | [] -> []
   | first::rest -> (ReverseList rest) @ [first]

```
* Max element in list:
```F#
let maxList list =
    let action maxSoFar x= 
        match x with | x when x>maxSoFar -> x | _-> maxSoFar
    match list with
        | [] -> None
        | first::rest -> rest |> List.fold action first |> Some
//Test
maxList [3;2;4;1]
maxList []
```
