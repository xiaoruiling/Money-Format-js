# Money-Format-js
money formatting
```
/**
 *  将金钱格式化
 * */
export function moneyFormat(money) {
    var num = (money || 0).toString(), result = '';
    let numArr = num.split('.');
    let integerNum = numArr[0]; // 整数部分
    var decimalsNum = ''; // 小数部分
    if (numArr.length === 2) {
        decimalsNum = '.' + numArr[1];
    }
    while (integerNum.length > 3) {
        result = ',' + integerNum.slice(-3) + result;
        integerNum = integerNum.slice(0, integerNum.length - 3);
    }
    if (integerNum) { result = integerNum + result + decimalsNum; }
    return result;
}
```
