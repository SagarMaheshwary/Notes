# TYPESCRIPT

- A fixed length array with specific types is called a tuple

```typescript
// Tuple
const arr: [string, number] = ["hello", 1];

//Tuple array
const students: [number, string][] = [
  [1, "Daniel"],
  [2, "John"],
];
```

- A value can be any of the specified types is called union type

```typescript
//union type, value can either be a string or number
let productId: string | number;

productId = "id-123";
productId = 123;
```

- Enums

```typescript
//Be default enum properties will have values from 0 (like index)
enum Direction {
  Up,
  Down,
  Left,
  Right,
}

//But we can also change the starting order by defining the first value:
enum Direction1 {
  Up = 1,
  Down,
  Left,
  Right,
}

//Assigning string values:
enum Roles {
  Admin = "admin",
  Support = "support",
  User = "user",
}
```

- Type assertion: Type assertion is a Typescript technique that tells the compiler the variable type. Though type assertion doesn't recreate code, typecasting does. You can tell the compiler not to infer the type of a value by using type assertion

```typescript
const id: any = 1;

const customerId = <number>id; // id will be casted as number

//another way:
const orderId = id as number;
```

- Custom types for objects:

```typescript
//can be done with the "type" feature
type Customer = {
  id: number;
  name: string;
};

const customer: Customer = {
  id: 1,
  name: "Daniel",
};

//or with the interfaces (interfaces are generally preferred for object/function types)
interface Order {
  id: number;
  name: string;
}

const order: Order = {
  id: 1,
  name: "Product 1",
};

//Type for functions
interface Log {
  id: number;
  message: string;
}

const log: Log = (id: number, message: string): void => {
    console.log(id, message)
});
```
