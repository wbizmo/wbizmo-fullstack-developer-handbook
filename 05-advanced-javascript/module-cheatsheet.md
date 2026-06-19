# Advanced JavaScript Module Cheatsheet

Scope:
    Controls variable access.

Closure:
    Function remembers outer variables.

Callback:
    Function passed into another function.

Higher-order function:
    Accepts or returns a function.

Array methods:

    forEach
    map
    filter
    find
    some
    every
    reduce
    includes
    sort

Destructuring:

    const { name } = user;
    const [first] = items;

Spread:

    const copy = [...items];
    const updated = { ...user };

Rest:

    function sum(...numbers) {}

Named export:

    export function add() {}

Named import:

    import { add } from "./math.js";

Default export:

    export default function log() {}

Async:

    async function run() {}

Await:

    const data = await promise;

try catch:

    try {
      // code
    } catch (error) {
      console.error(error.message);
    }

JSON:

    JSON.stringify(value)
    JSON.parse(json)

Fetch:

    const response = await fetch(url);
    const data = await response.json();

Key takeaway:
    Advanced JavaScript is the bridge between beginner syntax and real application development.
