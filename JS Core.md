**How to compute the min/max of an array of numbers?**  
`Math.min(...array1));` 

**How to properly return within a for loop?** 

  `function getFirstBlockOfColor(blocks, color) {
    let firstBlockOfColor = null;
    for (var i=0 ; i < blocks.length ; i++) {
      if (blocks[i].color === color) {
        firstBlockOfColor = blocks[i];
        return; // won't return an error but function will return nothing! The correct way is `return firstBlockOfColor;`
      }
    }
  }`
 
**Remove an item from an array?**  
Mutative:  
Use `arr.splice(itemIndex, 1)`. !!! Splice is mutative and returms the removed element! So just call it, don;t use its return value.  
Immutable approach:  
Copy the array first with `arrCopy = [...arr]`. (or `arrCopy = arr.slice()`)
