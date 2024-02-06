# `console.log` আমরা ইউজ করি ব্রাউজারে বা node.js এ আউপুট দেখতে। `log` ফাংশনটি `console` এর। `console` এর আরো ফাংশন রয়েছে। সেগুলো আজ দেখবো।

## `console.count`

`console.count` ইউজ হয় কতবার এটি সেইম আর্গুমেন্ট দিয়ে কল হয়েছে তা দেখতে।
Example:

```js
console.count("Hello");
//Output: Hello: 1
console.count("Hello");
//Output: Hello: 2
console.count("World");
//Output: World: 1
```

## `console.time`

`console.time` ইউজ হয় কোডের বিভিন্ন লাইনে যেতে কত সময় লেগেছে তা দেখতে। এটি ইউজ করতে প্রথমে `console.time` দিয়ে তার ভিতর আর্গুমেন্ট হিসেবে একটি ইউনিক লেভেল দিয়ে দিয়ে স্টার্টিং পয়েন্ট বসাতে হয়। এই স্টার্টিং পয়েন্ট থেকে সময় গণনা শুরু হবে। `console.timeLog` দিয়ে বিভিন্ন লাইন পর্যন্ত যেতে কত সময় লাগছে সেটা আউটপুটে দেখা যাবে। সবশেষে `console.timeEnd` দিয়ে সেই টাইম এর শেষ পয়েন্ট নির্দেশ করবে। Example:

```js
console.time("loop monitor 1");
for (let i = 0; i < 1000000; i++) {}
console.timeLog("loop monitor 1");
for (let i = 0; i < 1000000000; i++) {}
console.timeLog("loop monitor 1");
console.timeEnd("loop monitor 1");
/* 
Output:
loop monitor 1: 2.197938475ms
loop monitor 1: 2.288433432ms
loop monitor 1: 2.315934322ms
*/
```

**লিমিটেশনঃ এইরকম টাইম লগ একটি পেইজে সর্বোচ্চ ১০ হাজারবার রাখতে পারবেন।**

## `console.assert`

বিভিন্ন কন্ডিশন ভ্যালিডেড কিনা চেক করার জন্য `console.assert` ইউজ করা হয়। `console.assert` প্রথম আর্গুমেন্ট হিসবে কন্ডিশন নেয় ও ২য় আর্গুমেন্টে অপশনাল ইরর মেসেজ দেকায় যেটি শর্ত পূরন করতে না পারলে ইরর মেসেজ হিসেবে দেখাবে। Example:

```js
console.assert(2 == 6);
//Output: Assertion failed: console.assert
console.assert(2 == 6, "The numbers are not equal");
//Output: Assertion failed: The numbers are not equal
```

## `console.table`

`console.table` একটি অবজেক্টকে টেবুলার আকারে দেখাতে ব্যাবহার করা হয়। এটি প্রথম আর্গুমেন্ট হিসেবে একটি অবজেক্ট বা একটি Array of Object গ্রহন করে, ২য় অপশনাল আর্গুমেন্ট হিসেবে স্পেসিফিক অবজেক্ট যে প্রপার্টি দেখাতে চান তার Array গ্রহন করে। Example:

```js
const car1 = { brand: "Ford", model: "Raptor" };
const car2 = { brand: "Ford", model: "RAM" };
const car3 = { brand: "Toyota", model: "Supra" };
console.table([car1, car3, car3]);
//Output:
```

| (index) | brand  | model  |
| ------- | ------ | ------ |
| 0       | Ford   | Raptor |
| 1       | Ford   | RAM    |
| 2       | Toyota | Supra  |

**With 2nd property argument**

```js
console.table([car1, car3, car3], ["model"]);
//Output
```

| (index) | model  |
| ------- | ------ |
| 0       | Raptor |
| 1       | RAM    |
| 2       | Supra  |

**Single Object**

```js
console.table(car1);
```

| (index) | value  |
| ------- | ------ |
| brand   | Ford   |
| model   | Raptor |
