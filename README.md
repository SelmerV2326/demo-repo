# Demo
function bitcoinMinig(input){
   let buffer = 0;
   let len = input.length;
   let day = 0; 
   let leftMoney = 0;
   let myDay = 1;
   let flag = false;
   /*
        1 Bitcoin 11949.16 lv.
        1 g of gold 67.51 lv
   */
  for(let i = 0; i < len; ++i){
       day++;
       if(day % 3 === 0){
           input[i] = input[i] - 30*input[i]/100;
       }
       buffer += Number(input[i])*67.51;
       if(buffer >= 11949.16){
         myDay = day;
       }
  }
  myDay = myDay  - (day-1)
    leftMoney = buffer - (Math.floor(buffer / 11949.16)*11949.16);
    console.log(`Bought bitcoins: ${Math.floor(buffer / 11949.16)}`);
    console.log(`Day of the first purchased bitcoin:${myDay}`);
    console.log(`Money left: ${leftMoney.toFixed(2)} lv.`);
}
bitcoinMinig([100, 200, 300])
