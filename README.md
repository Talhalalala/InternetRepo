# API documentation

An API to store and interact with data about people and houses in your neighbourhood.

## Request types

**Look up a house:**

- `GET neighbourhood/houses/:id`
- Returns an object for the house of the form:

```
{
    id: [int],
    address: {
        street_address: [string],
        postcode: [string],
    },
    owner: [string]
}
```

**Find the address of a house:**

- `GET neighbourhood/houses/:id/address`
- Returns an object for the address of the house in the same form as above

**Find the owner of a house:**

- `GET neighbourhood/houses/:id/owner`
- Returns an object containing just the owner of the house

**Find people within an age bracket:**

- `GET neighbourhood/people?age=gt{lower bound}&age=lt{upper bound}`
- Returns an array of people objects of the form:

```
{
    id: [int],
    name: [string],
    age: [int],
    household_size: [int]
}
```

**Find people with a given number of people in their household:**

- `GET neighbourhood/people?household_size={size}`
- Returns an array of people objects with the requested household size
