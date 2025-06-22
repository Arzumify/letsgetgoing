# A comparison of Go

Go as a language is difficult to place. It's primarily a multi-paradigm language with support for an array of programming styles, such as procedural, object-orientated[^1] or even functional[^2].

For the purposes of this guide, we will be primarily starting off with procedural and slowly build our way into OOP naturally, with functional being touched on slightly. This is due to the vast majority of Go libraries using OOP approaches rather than functional, and most codebases are not written functionally. Sorry to any functional lovers out there!

A table below will compare Go to many other popular languages.

|                         | Go  | C   | JavaScript | Python | Rust |
|-------------------------|-----|-----|------------|--------|------|
| Imperative              | Yes | Yes | Yes        | Yes    | Yes  |
| Object-Orientated       | ~   | No  | Yes        | Yes    | ~    |
| Compiled                | Yes | Yes | No         | No     | Yes  |
| First-class functions   | Yes | Yes | Yes        | Yes    | Yes  |
| Memory-safe             | Yes | No  | No         | No     | Yes  |
| Static typing           | Yes | Yes | No         | No     | Yes  |
| Browser support[^3]     | Yes | No  | Yes        | No     | Yes  |
| Simple ASync            | Yes | Yes | ~[^4]      | ~[^4]  | No   |
| Gracious error handling | Yes | No  | No         | No     | Yes  |
| Easy to code            | Yes | No  | Yes        | Yes    | No   |

Go is primarily used in server environments where both speed, safety and simplicity are critical - in fact, it was originally designed by Google for use in their servers, as their Python codebases started getting much too slow, but C was much too complicated.

[^1]: Albeit without traditional inheritance or statics.
[^2]: Functions are treated very much as first-class citizens. However, pattern matching is a bit iffy compared to fully functional languages.
[^3]: _First party_ browser support. EMScriptein and others are not first party.
[^4]: Not any function can call async functions or be called by an async function