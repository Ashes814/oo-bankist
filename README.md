# 欧欧银行家app

# 1. 流程图

![未命名文件.jpg](%E6%AC%A7%E6%AC%A7%E9%93%B6%E8%A1%8C%E5%AE%B6app%20c30386179086483988c62d03e1ef3190/%25E6%259C%25AA%25E5%2591%25BD%25E5%2590%258D%25E6%2596%2587%25E4%25BB%25B6.jpg)

# 2. HTML

![Untitled](%E6%AC%A7%E6%AC%A7%E9%93%B6%E8%A1%8C%E5%AE%B6app%20c30386179086483988c62d03e1ef3190/Untitled.png)

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width-device-width, initial-scale=1.0" />
    <meta http-equiv="X-UA-Compatible" content="ie=edge" />
    <link rel="shortcut icon" type="image/png" href="/icon.png" />
    <link
      href="https://fonts.googleapis.com/css?family=Poppins:400,500,600&display=swap"
      rel="stylesheet"
    />

    <link rel="stylesheet" href="style.css" />
    <title>欧欧银行家</title>
  </head>

  <body>
    <!-- TOP NAVIGATION-->
    <nav>
      <p class="welcome">登录以开始</p>
      <img src="logo.png" alt="Logo" class="logo" />
      <form class="login">
        <input
          type="text"
          placeholder="用户名"
          class="login__input login__input--user"
        />
        <!-- In practice, use type = 'password' -->
        <input
          type="text"
          placeholder="PIN"
          maxlength="4"
          class="login__input login__input--pin"
        />
        <button class="login__btn">&rarr;</button>
      </form>
    </nav>

    <main class="app">
      <!-- BALANCE -->
      <div class="balance">
        <div>
          <p class="balance__label">当前余额</p>
          <p class="balance__date">日期 <span class="date">05/03/2037</span></p>
        </div>
        <p class="balance__value">0000¥</p>
      </div>

      <!-- MOVEMENTS -->
      <div class="movements">
        <div class="movements__row">
            <div class="movements__type movements__type--deposit"> 2 deposit</div>
            <div class="movements__date"> 3天前</div>
            <div class="movements__value">4 000¥</div>
        </div>
        <div class="movements__row">
            <div class="movements__type movements__type--withdrawal">1 withdrawal</div>
            <div class="movements__date">24/01/2037</div>
            <div class="movements__value">-378¥</div>
        </div>
			</div>

      <!-- SUMMARY -->
      <div class="summary">
        <p class="summary__label">收入</p>
        <p class="summary__value summary__value--in">0000¥</p>
        <p class="summary__label">支出</p>
        <p class="summary__value summary__value--out">0000¥</p>
        <p class="summary__label">利息</p>
        <p class="summary__value summary__value--interest">0000¥</p>
        <button class="btn--sort">&downarrow; 排序</button>
        </div>

      <!-- OPERATION: TRANSFERS -->
      <div class="operation operation--transfer">
        <h2>转账</h2>
        <form class="form form--transfer">
            <input type="text" class="form__input form__input--to" />
            <input type="number" class="form__input form__input--amount" />
            <button class="form__btn form__btn--transfer">&rarr;</button>
            <label class="form__label">转给账户</label>
            <label class="form__label">金额</label>
        </form>
      </div>

      <!-- OPERATION: LOAN -->
      <div class="operation operation--loan">
        <h2>请求贷款</h2>
        <form class="form form--loan">
            <input type="number" class="form__input form__input--loan-amount" />
            <button class="form__btn form__btn--loan">&rarr;</button>
            <label class="form__label form__label--loan">金额</label>
        </form>
      </div>

      <!-- OPERATION: CLOSE -->
      <div class="operation operation--close">
        <h2>关闭账户</h2>
        <form class="form form--close">
            <input type="text" class="form__input form__input--user" />
            <input type="password" maxlength="6" class="form__input form__input--pin" />
            <button class="form__btn form__btn--close">&rarr;</button>
            <label class="form__label">确认用户</label>
            <label class="form__label">确认PIN</label>
        </form>
      </div>

      <!-- LOGOUT TIMER -->
      <p class="logout-timer">
        你将在<span class="timer">05:00</span>后自动退出登录！
      </p>
    </main>

    <!-- <footer>
      &copy; by Jonas Schmedtmann. Modified by OO
    </footer> -->
    <script src="script.js"></script>
  </body>
</html>
```

# 3. CSS

![Untitled](%E6%AC%A7%E6%AC%A7%E9%93%B6%E8%A1%8C%E5%AE%B6app%20c30386179086483988c62d03e1ef3190/Untitled%201.png)

```css
* {
  margin: 0;
  padding: 0;
  box-sizing: inherit;
}

html {
  font-size: 62.5%;
  box-sizing: border-box;
}

body {
  font-family: "Poppins", sans-serif;
  color: #444;
  background-color: #f3f3f3;
  height: 100vh;
  padding: 2rem;
}

nav {
  display: flex;
  justify-content: space-between;
  align-items: center;
  padding: 0 2rem;
}

.welcome {
  font-size: 1.9rem;
  font-weight: 500;
}

.logo {
  height: 5.25rem;
}

.login {
  display: flex;
}

.login__input {
  border: none;
  padding: 0.5rem 2rem;
  font-size: 1.6rem;
  font-family: inherit;
  text-align: center;
  width: 12rem;
  border-radius: 10rem;
  margin-right: 1rem;
  color: inherit;
  border: 1px solid #fff;
  transition: all 0.3s;
}

.login__input:focus {
  outline: none;
  border: 1px solid #ccc;
}

.login__input::placeholder {
  color: #bbb;
}

.login__btn {
  border: none;
  background: none;
  font-size: 2.2rem;
  color: inherit;
  cursor: pointer;
  transition: all 0.3s;
}

.login__btn:hover,
.login__btn:focus,
.btn--sort:hover,
.btn--sort:focus {
  outline: none;
  color: #777;
}

/* MAIN */
.app {
  position: relative;
  max-width: 100rem;
  margin: 4rem auto;
  display: grid;
  grid-template-columns: 4fr 3fr;
  grid-template-rows: auto repeat(3, 15rem) auto;
  gap: 2rem;

  /* Creates the fade in/out animation */
  /* opacity: 0; */
  transition: all 1s;
}

.balance {
  grid-column: 1 / span 2;
  display: flex;
  align-items: flex-end;
  justify-content: space-between;
  margin-bottom: 2rem;
}

.balance__label {
  font-size: 2.2rem;
  font-weight: 500;
  margin-bottom: -0.2rem;
}

.balance__date {
  font-size: 1.4rem;
  color: #888;
}

.balance__value {
  font-size: 4.5rem;
  font-weight: 400;
}

/* MOVEMENTS */
.movements {
  grid-row: 2 / span 3;
  background-color: #fff;
  border-radius: 1rem;
  overflow: scroll;
}

.movements__row {
  padding: 2.25rem 4rem;
  display: flex;
  align-items: center;
  border-bottom: 1px solid #eee;
}

.movements__type {
  font-size: 1.1rem;
  text-transform: uppercase;
  font-weight: 500;
  color: #fff;
  padding: 0.1rem 1rem;
}

.movements__date {
  font-size: 1.1rem;
  text-transform: uppercase;
  font-weight: 500;
  color: #666;
}

.movements__type--deposit {
  background-image: linear-gradient(to top left, #39b385, #9be15d);
}

.movements__type--withdrawal {
  background-image: linear-gradient(to top left, #e52a5a, #ff585f);
}

.movements__value {
  font-size: 1.7rem;
  margin-left: auto;
}

/* SUMMARY */
.summary {
  grid-row: 5 / 6;
  display: flex;
  align-items: baseline;
  padding: 0 0.3rem;
  margin-top: 1rem;
}

.summary__label {
  font-size: 1.2rem;
  font-weight: 500;
  text-transform: uppercase;
  margin-right: 0.8rem;
}

.summary__value {
  font-size: 2.2rem;
  margin-right: 2.5rem;
}

.summary__value--in,
.summary__value--interest {
  color: #66c873;
}

.summary__value--out {
  color: #f5465d;
}

.btn--sort {
  margin-left: auto;
  border: none;
  background: none;
  font-size: 1.3rem;
  font-weight: 500;
  cursor: pointer;
}

/* OPERATIONS */
.operation {
  border-radius: 1rem;
  padding: 3rem 4rem;
  color: #333;
}

.operation--transfer {
  background-image: linear-gradient(to top left, #ffb003, #ffcb03);
}

.operation--loan {
  background-image: linear-gradient(to top left, #39b385, #9be15d);
}

.operation--close {
  background-image: linear-gradient(to top left, #e52a5a, #ff585f);
}

h2 {
  margin-bottom: 1.5rem;
  font-size: 1.7rem;
  font-weight: 600;
  color: #333;
}

.form {
  display: grid;
  grid-template-columns: 2.5fr 2.5fr 1fr;
  grid-template-rows: auto auto;
  gap: 0.4rem 1rem;
}

/* Exceptions for interest */
.form.form--loan {
  grid-template-columns: 2.5fr 1fr 2.5fr;
}
.form__label--loan {
  grid-row: 2;
}

/* END EXCEPTIONS */
.form__input {
  width: 100%;
  border: none;
  background-color: rgba(255, 255, 255, 0.4);
  font-family: inherit;
  font-size: 1.5rem;
  text-align: center;
  color: #333;
  padding: 0.3rem 1rem;
  border-radius: 0.7rem;
  transition: all 0.3s;
}

.form__input:focus {
  outline: none;
  background-color: rgba(255, 255, 255, 0.6);
}

.form__label {
  font-size: 1.3rem;
  text-align: center;
}

.form__btn {
  border: none;
  border-radius: 0.7rem;
  font-size: 1.8rem;
  background-color: #fff;
  cursor: pointer;
  transition: all 0.3s;
}

.form__btn:focus {
  outline: none;
  background-color: rgba(255, 255, 255, 0.8);
}

.logout-timer {
  padding: 0 0.3rem;
  margin-top: 1.9rem;
  text-align: right;
  font-size: 1.25rem;
}

.timer {
  font-weight: 600;
}
```

# 3. JavaScript

```css
"use strict";
// Data
const account1 = {
  owner: "Jonas Schmedtmann",
  movements: [200, 455.23, -306.5, 25000, -642.21, -133.9, 79.97, 1300],
  interestRate: 1.2, // %
  pin: 1111,

  movementsDates: [
    "2019-11-18T21:31:17.178Z",
    "2019-12-23T07:42:02.383Z",
    "2020-01-28T09:15:04.904Z",
    "2020-04-01T10:17:24.185Z",
    "2020-05-08T14:11:59.604Z",
    "2020-07-26T17:01:17.194Z",
    "2020-07-28T23:36:17.929Z",
    "2020-08-01T10:51:36.790Z",
  ],
  currency: "EUR",
  locale: "pt-PT", // de-DE
};

const account2 = {
  owner: "Jessica Davis",
  movements: [5000, 3400, -150, -790, -3210, -1000, 8500, -30],
  interestRate: 1.5,
  pin: 2222,

  movementsDates: [
    "2019-11-01T13:15:33.035Z",
    "2019-11-30T09:48:16.867Z",
    "2019-12-25T06:04:23.907Z",
    "2020-01-25T14:18:46.235Z",
    "2020-02-05T16:33:06.386Z",
    "2020-04-10T14:43:26.374Z",
    "2020-06-25T18:49:59.371Z",
    "2020-07-26T12:01:20.894Z",
  ],
  currency: "USD",
  locale: "en-US",
};

const accounts = [account1, account2];

///////////////////////////////////////
// ELEMENTS
const labelWelcome = document.querySelector(".welcome");
const labelDate = document.querySelector(".date");
const labelBalance = document.querySelector(".balance__value");
const labelSumIn = document.querySelector(".summary__value--in");
const labelSumOut = document.querySelector(".summary__value--out");
const labelSumInterest = document.querySelector(".summary__value--interest");
const labelTimer = document.querySelector(".timer");

const containerApp = document.querySelector(".app");
const containerMovements = document.querySelector(".movements");

const btnLogin = document.querySelector(".login__btn");
const btnTransfer = document.querySelector(".form__btn--transfer");
const btnLoan = document.querySelector(".form__btn--loan");
const btnClose = document.querySelector(".form__btn--close");
const btnSort = document.querySelector(".btn--sort");

const inputLoginUsername = document.querySelector(".login__input--user");
const inputLoginPin = document.querySelector(".login__input--pin");
const inputTransferTo = document.querySelector(".form__input--to");
const inputTransferAmount = document.querySelector(".form__input--amount");
const inputLoanAmount = document.querySelector(".form__input--loan-amount");
const inputCloseUsername = document.querySelector(".form__input--user");
const inputClosePin = document.querySelector(".form__input--pin");

/////////////////////////////////////////////////
// Functions

const formatMovementsDate = function (date, locale) {
  const calcDaysPassed = (date1, date2) =>
    Math.round(Math.abs(date2 - date1) / (1000 * 60 * 60 * 24));
  const daysPassed = calcDaysPassed(new Date(), date);

  if (daysPassed === 0) return "今天";
  if (daysPassed === 1) return "昨天";
  if (daysPassed <= 7) return `${daysPassed}天前`;

  return new Intl.DateTimeFormat(locale).format(date);
};

const formatCur = function (value, locale, currency) {
  return new Intl.NumberFormat(locale, {
    style: "currency",
    currency: currency,
  }).format(value);
};

const displayMovements = function (acc, sort = false) {
  containerMovements.innerHTML = "";

  const movs = sort
    ? acc.movements.slice().sort((a, b) => a - b)
    : acc.movements;

  movs.forEach(function (mov, i) {
    const type = mov > 0 ? "收入" : "支出";

    const date = new Date(acc.movementsDates[i]);
    const displayDate = formatMovementsDate(date, acc.locale);

    const formattedMov = formatCur(mov, acc.locale, acc.currency);

    const html = `
        <div class="movements__row">
          <div class="movements__type movements__type--${type}">${
      i + 1
    } ${type}</div>
          <div class="movements__date">${displayDate}</div>
          <div class="movements__value">${formattedMov}</div>
        </div>
      `;

    containerMovements.insertAdjacentHTML("afterbegin", html);
  });
};

const calcDisplayBalance = function (acc) {
  acc.balance = acc.movements.reduce((acc, mov) => acc + mov, 0);
  labelBalance.textContent = formatCur(acc.balance, acc.locale, acc.currency);
};

const calcDisplaySummary = function (acc) {
  const incomes = acc.movements
    .filter((mov) => mov > 0)
    .reduce((acc, mov) => acc + mov, 0);
  labelSumIn.textContent = formatCur(incomes, acc.locale, acc.currency);

  const outcomes = acc.movements
    .filter((mov) => mov < 0)
    .reduce((acc, mov) => acc + mov, 0);
  labelSumOut.textContent = formatCur(
    Math.abs(outcomes),
    acc.locale,
    acc.currency
  );

  const interest = acc.movements
    .filter((mov) => mov > 0)
    .map((deposit) => (deposit * acc.interestRate) / 100)
    .filter((int, i, arr) => {
      return int >= 1;
    })
    .reduce((acc, int) => acc + int, 0);
  labelSumInterest.textContent = formatCur(interest, acc.locale, acc.currency);
};

const createUsernames = function (accs) {
  accs.forEach(function (acc) {
    acc.username = acc.owner
      .toLowerCase()
      .split(" ")
      .map((name) => name[0])
      .join("");
  });
};
createUsernames(accounts);

const updateUI = function (acc) {
  // Display movements
  displayMovements(acc);

  // Display balance
  calcDisplayBalance(acc);

  // Display summary
  calcDisplaySummary(acc);
};

const startLogOutTimer = function () {
  const tick = function () {
    const min = String(Math.trunc(time / 60)).padStart(2, 0);
    const sec = String(time % 60).padStart(2, 0);

    // In each Call, print the remaining time to UI
    labelTimer.textContent = `${min}:${sec}`;

    // When 0 seconds, stop timer and log out user
    if (time === 0) {
      clearInterval(timer);
      labelWelcome.textContent = "登录以开始";
      containerApp.style.opacity = 0;
    }

    time--;
  };

  // set time to 2 minutes;
  let time = 120;

  // call tick every 1 second
  tick();
  const timer = setInterval(tick, 1000);

  return timer;
};

//////////////////
// EVENT HANDLERS
let currentAccount, timer;

btnLogin.addEventListener("click", function (e) {
  // prevent form from submitting
  e.preventDefault();

  currentAccount = accounts.find(
    (acc) => acc.username === inputLoginUsername.value
  );

  if (currentAccount?.pin === +inputLoginPin.value) {
    // Display UI and message
    labelWelcome.textContent = `欢迎回来, ${
      currentAccount.owner.split(" ")[0]
    }`;
    containerApp.style.opacity = 100;

    // Create current date and time
    const now = new Date();
    const options = {
      hour: "numeric",
      minute: "numeric",
      day: "numeric",
      month: "numeric",
      year: "numeric",
    };

    labelDate.textContent = new Intl.DateTimeFormat(
      currentAccount.locale,
      options
    ).format(now);

    // clear input fields
    inputLoginUsername.value = inputLoginPin.value = "";
    inputLoginPin.blur();

    // Timer
    if (timer) clearInterval(timer);
    timer = startLogOutTimer();

    // update UI
    updateUI(currentAccount);
  }
});

btnTransfer.addEventListener("click", function (e) {
  e.preventDefault();
  const amount = +inputTransferAmount.value;
  const receiverAcc = accounts.find(
    (acc) => acc.username === inputTransferTo.value
  );
  inputTransferAmount.value = inputTransferTo.value = "";

  if (
    amount > 0 &&
    receiverAcc &&
    currentAccount.balance >= amount &&
    receiverAcc?.username !== currentAccount.username
  ) {
    // Doing TRANSFER
    currentAccount.movements.push(-amount);
    receiverAcc.movements.push(amount);

    // Add transfer data
    currentAccount.movementsDates.push(new Date().toISOString());
    receiverAcc.movementsDates.push(new Date().toISOString());

    // Update UI
    updateUI(currentAccount);

    // Reset Timer
    clearInterval(timer);
    timer = startLogOutTimer();
  }
});

btnLoan.addEventListener("click", function (e) {
  e.preventDefault();

  const amount = Math.floor(inputLoanAmount.value);

  if (
    amount > 0 &&
    currentAccount.movements.some((mov) => mov >= amount * 0.1)
  ) {
    setTimeout(function () {
      // Add movement
      currentAccount.movements.push(amount);

      // Add loan date
      currentAccount.movementsDates.push(new Date().toISOString());

      // Update UI
      updateUI(currentAccount);
      // Reset timer
      clearInterval(timer);
      timer = startLogOutTimer();
    }, 2500);
  }
  inputLoanAmount.value = "";
});

btnClose.addEventListener("click", function (e) {
  e.preventDefault();

  if (
    inputCloseUsername.value === currentAccount.username &&
    +inputClosePin.value === currentAccount.pin
  ) {
    const index = accounts.findIndex(
      (acc) => acc.username === currentAccount.username
    );
    console.log(index);
    // .indexOf(23)

    // Delete account
    accounts.splice(index, 1);

    // Hide UI
    containerApp.style.opacity = 0;
  }

  inputCloseUsername.value = inputClosePin.value = "";
});

let sorted = false;
btnSort.addEventListener("click", function (e) {
  e.preventDefault();
  displayMovements(currentAccount, !sorted);
  sorted = !sorted;
});
```

[https://github.com/Ashes814/oo-bankist](https://github.com/Ashes814/oo-bankist)