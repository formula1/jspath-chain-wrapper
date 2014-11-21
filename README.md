Jspath Chain Wrapper
====================

Provides a wrapper around [jspath](https://github.com/dfilatov/jspath) that allows you to chain calls togethor with and without a context

Example

`
PathWrapper('..{.color === "red"}').apply({a:{b:{color:"red"}}}).map(console.log).set("color","blue").map(console.log).prep('..{.color === "blue"}').map(console.log).set("background-color","red").map(console.log).delete("color").map(console.log).get().forEach(function(item){
 console.log("this is an array item");
})
`

## Notes

* Javascript returns objects by reference
* if you want to edit something and have that happen to all pointers, you'll need to get the reference rather than the value using `{.path == value}`
* if you just want the values, then the set and delete methods do almost nothing
