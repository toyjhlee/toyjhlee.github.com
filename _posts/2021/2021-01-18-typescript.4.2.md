---
title: 'Typescript 4.2'
---

## Announcing TypeScript 4.2

[Announcing TypeScript 4.2](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2/)

## Announcing TypeScript 4.2 Beta

[Announcing TypeScript 4.2 Beta](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/)

-   [Leading/Middle Rest Elements in Tuple Types](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#template-literal-expressions-have-template-literal-types)

```javascript
let foo: [...string[], number];

foo = [123];
foo = ["hello", 123];
foo = ["hello!", "hello!", "hello!", 123];

let bar: [boolean, ...string[], boolean];

bar = [true, false];
bar = [true, "some text", false];
bar = [true, "some", "separated", "text", false];
```

-   [Smarter Type Alias Preservation](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#smarter-type-alias-preservation)
-   [Template Literal Expressions Have Template Literal Types](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#template-literal-expressions-have-template-literal-types)

```javascript
const n: number = 123;

// Has the type `${number}px`
const s1 = `${n}px`;

// Works!
const s2: `${number}px` = s1;

// Error!
const s3: `${number}pt` = s1;

// Has the type 'string' because of widening.
let v1 = s1;
```

-   [Stricter Checks for the in Operator](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#stricter-checks-for-the-in-operator)

-   [--noPropertyAccessFromIndexSignature](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#nopropertyaccessfromindexsignature)

-   [abstract Construct Signatures](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#abstract-construct-signatures)

-   [--explainFiles to understand why files have been included in a program](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#explainfiles-to-understand-why-files-have-been-included-in-a-program)

-   [Relaxed Rules Between Optional Properties and String Index Signatures](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#relaxed-rules-between-optional-properties-and-string-index-signatures)

-   [Declare Missing Helper Function](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#declare-missing-helper-function)

-   [Breaking Changes](https://devblogs.microsoft.com/typescript/announcing-typescript-4-2-beta/#breaking-changes)
