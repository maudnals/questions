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
