# Subject 5 — Safe Fetch User

## API Endpoint

```
https://jsonplaceholder.typicode.com/users/{id}
```

## Function name

`safeFetchUser`

## Function interface

```tsx
safeFetchUser(userId)
```

## Description

Fetch a single user by `userId`.

Rules:
- If any error occurs, thorw error with custom name and message "Sec34UserNotFoundError" and return error message
- If successful, return an object with `id`, `name`, `phone`, `address`

## Example input

```tsx
safeFetchUser(1)
```

## Example output

```json
{
  id: 1,
  name: "Leanne Graham",
  address: {
    street: "Kulas Light",
    suite: "Apt. 556",
    city: "Gwenborough",
    zipcode: "92998-3874",
    geo: {
      lat: "-37.3159",
      lng: "81.1496"
    }
  },
  phone: "1-770-736-8031 x56442",
}
```

## Example input

```tsx
safeFetchUser(9999)
```

## Example output
```ts
"Sec34UserNotFoundError"
```

## Edge Cases

### Invalid userId values
Return `Sec34UserNotFoundError` for invalid or non-existent user IDs:

```tsx
safeFetchUser(0)      // returns Sec34UserNotFoundError
safeFetchUser(-1)    // returns Sec34UserNotFoundError
safeFetchUser(9999)  // returns Sec34UserNotFoundError
```

### User with empty address
If the user exists but has an empty address, return it:

```tsx
safeFetchUser(1)
```

```json
{
  id: 1,
  name: "Leanne Graham",
  address: null,
  phone: "1-770-736-8031 x56442",
}
```

## Global Rules

- Use **axios**
- Use **async / await**
- Use **try / catch**
- One function per subject
- Use at least one **array or object method**
- No `any`
- Function must **return value only** (no console.log)

