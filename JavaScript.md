## 分离整数的各个数位

    let number = Number(prompt("number:"));
    let str = '';
    
    while(1) {
      if(number > 0) {
        //去除末尾的0
        while(1) {
          if(number % 10 == 0) {
            number /= 10;
          } else break;
        }
        
        str += number % 10;
        number = Math.floor(number / 10);
        if(number == 0) break;
      }
    
      if(number == 0) {
        str += 0;
        break;
      }
    
      if(number < 0) {
        str += "-";
        number = -number;
      }
    }
    
    console.log(str);

## 十进制转任意进制

    function f(n) {
      let arr = [];
      let positive = true;
      let str = "";
    
      if(n < 0) {
        positive = false;
        n *= -1;
      }
    
      while(1) {
        if(n < 7) {
          arr.push(n);
          break;
        } else {
          arr.push( n % 7);
          n = parseInt(n / 7);
        }
      }
    
      for(let i = arr.length - 1; i >= 0; i--) {
        str += arr[i];
      }
    
      if(positive) {
        return str;
      } else {
        return "-" + str;
      }
    }

## 特定数字前的所有质数

    let number = Number(prompt("number:"));
    let agent = [];
      
    for(let i = 2; i <= number; i++) {
      let agentCopy = [];
    
      for(let j = 2; j <= i; j++) {
        if(i % j == 0) agentCopy.push(j);
      }
    
      if(agentCopy.length == 1) agent.push(i);
    }
    
    console.log(agent);
