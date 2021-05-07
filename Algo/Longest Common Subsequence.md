```js
function lcs(str1, str2) {
    let ma = [];
    let res = [];
    for(let i =  0; i <= str2.length; i++) {
      ma.push(new Array(str1.length + 1).fill(0));
    }
  
    for(let row = 1; row <= str2.length; row++){
      for(let col = 1; col <= str1.length; col++){
        if(str1[col - 1] == str2[row - 1]) {
          // console.log(col,str1[col - 1], row, str2[row - 1])
          ma[row][col] = Math.min((Math.max(ma[row - 1][col], ma[row][col - 1]) + 1)
                                 , Math.min(row, col));
        } else {
          ma[row][col] = Math.max(ma[row - 1][col], ma[row][col - 1]);
        }
      }
    }
  
  console.log(ma);
  
    let row = str2.length, col = str1.length;
    while(row > 0 && col > 0) {
      let cur = ma[row][col];
      //console.log(cur, row, col);
      if(cur > ma[row - 1][col] && cur > ma[row][col - 1]){
         console.log(row, col, cur, ma[row - 1][col], ma[row][col - 1]);
        res.unshift(str1[col - 1]);
        row--;
        col--;
      }else {
        if (cur == ma[row - 1][col]){
          row--;
        }else{
          col--;
        }
      }
      console.log(res);
    }
  
    return res;
}

/*
    a p p l e
    0 0 0 0 0
p 0 0 1 1 1 1
i 0 0 1 1 1 1
n 0 0 1 1 1 1
e 0 0 1 1 1 2
a 0 1 1 1 1 2
p 0 1 2 
p 0
l 0
e 0

*/

```