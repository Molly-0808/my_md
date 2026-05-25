## TDD

### 安裝 Jest

Jest 是由 Meta (Facebook) 開發並維護的一個 JS 測試框架。

npm i -D jest

```js
在 package.json 裡寫上腳本：
{
  "scripts": {
    "test": "node --disable-warning=ExperimentalWarning  --experimental-vm-modules node_modules/jest/bin/jest.js"
  },
  "type": "module",
  "devDependencies": {
    "jest": "^30.4.2"
  }
}
```

npm run test

### Regex (Regular Expression)

Regex 是一串用來定義「搜尋模式」的文字字串。

https://regex101.com/

![regex](./image/regex.png)

email常規表示法：

https://stackoverflow.com/questions/201323/how-can-i-validate-an-email-address-using-a-regular-expression

```
(?:[a-z0-9!#$%&'*+\x2f=?^_`\x7b-\x7d~\x2d]+(?:\.[a-z0-9!#$%&'*+\x2f=?^_`\x7b-\x7d~\x2d]+)*|"(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21\x23-\x5b\x5d-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])*")@(?:(?:[a-z0-9](?:[a-z0-9\x2d]*[a-z0-9])?\.)+[a-z0-9](?:[a-z0-9\x2d]*[a-z0-9])?|\[(?:(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9]))\.){3}(?:(2(5[0-5]|[0-4][0-9])|1[0-9][0-9]|[1-9]?[0-9])|[a-z0-9\x2d]*[a-z0-9]:(?:[\x01-\x08\x0b\x0c\x0e-\x1f\x21-\x5a\x53-\x7f]|\\[\x01-\x09\x0b\x0c\x0e-\x7f])+)\])
```

返回[JavaScript 技術筆記](#javascript-技術筆記)

## TDD 實作

```
建立 __tests__ 資料夾 和 lib 資料夾

__tests__ 裡面放測試檔案

lib 裡面放原始碼檔案

原則：先寫測試再寫原始碼
```

```js
在 __tests__ 的 temperature.test.js 裡：

import { f2c, c2f } from "../lib/temperature.js";

test("1 + 1 = 2", () => {
  expect(1 + 1).toBe(2);
});

test("溫度轉換公式(華氏轉攝氏)", () => {
  expect(f2c(150)).toBe(65.6);
  expect(f2c(178)).toBe(81.1);
});

test("溫度轉換公式(攝氏轉華氏)", () => {
  expect(c2f(38)).toBe(100.4);
  expect(c2f(66)).toBe(150.8);
});
```

```js
在 lib 的 temperature.js 裡：

function f2c(f) {
  return Number((((f - 32) * 5) / 9).toFixed(1));
}
f2c(140);

function c2f(c) {
  return Number(((c * 9) / 5 + 32).toFixed(1));
}
c2f(40);

export { f2c, c2f };
```

```js
在 __tests__ 的 atm.test.js 裡：

存錢功能
可以存錢
不可以存 0 元或是小於 0 元的金額（越存錢越少！）
領錢功能
可以領錢
不能領 0 元或是小於 0 元的金額（越領錢越多！）
不能領超過本身餘額
// 以上是題目

// 存錢功能
import { BankAccount } from "../lib/BankAccount.js";

  // 3A原則
test("可以存錢", () => {
  // Arrange
  const account = new BankAccount(5);

  // Act
  account.deposit(10);

  // Assert
  expect(account.balance()).toBe(15);
});
```

```js
在 lib 的 BankAccount.js 裡：

class BankAccount {
  // Arrange
  constructor(amount) {
    this.balance = amount;
  }

  // Act: 存錢
  deposit(money) {
    if (money > 0) {
      this.balance += money;
    }
  }

  // Assert: 查詢餘額
  getBalance() {
    return this.balance;
  }
}

export { BankAccount };
```
