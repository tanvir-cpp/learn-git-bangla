# কমিট লগ চেক

## git log কি?

তুমি এতক্ষণে কয়েকটা কমিট করেছো। এখন যদি জানতে চাও — "আমি এতদিনে কি কি কমিট করেছি?" — তাহলে `git log` ব্যবহার করবে।

`git log` তোমার প্রোজেক্টের পুরো কমিট হিস্ট্রি দেখায়।

## বেসিক ব্যবহার

```bash
git log
```

আউটপুট এরকম দেখাবে:

```
commit a1b2c3d4e5f6g7h8i9j0 (HEAD -> main)
Author: Tanvir Rahman <tanvir@example.com>
Date:   Thu Feb 13 10:30:00 2026 +0600

    hello.txt আপডেট ও notes.txt যোগ করা হয়েছে

commit b2c3d4e5f6g7h8i9j0k1
Author: Tanvir Rahman <tanvir@example.com>
Date:   Thu Feb 13 10:15:00 2026 +0600

    second.txt ফাইল তৈরি করেছি

commit c3d4e5f6g7h8i9j0k1l2
Author: Tanvir Rahman <tanvir@example.com>
Date:   Thu Feb 13 10:00:00 2026 +0600

    প্রথম কমিট - hello.txt ফাইল যোগ করেছি
```

প্রতিটা কমিটে দেখাচ্ছে:

- **commit hash** = কমিটের ইউনিক আইডি (লম্বা একটা কোড)
- **Author** = কে করেছে
- **Date** = কবে করেছে
- **মেসেজ** = কি করেছে

## ছোট করে দেখা (One Line)

কমিট অনেক হলে লম্বা লিস্ট আসে। ছোট করে দেখতে চাইলে:

```bash
git log --oneline
```

আউটপুট:

```
a1b2c3d hello.txt আপডেট ও notes.txt যোগ করা হয়েছে
b2c3d4e second.txt ফাইল তৈরি করেছি
c3d4e5f প্রথম কমিট - hello.txt ফাইল যোগ করেছি
```

অনেক ক্লিন! শুধু হ্যাশের শুরুটা আর মেসেজ দেখাচ্ছে।

## নির্দিষ্ট সংখ্যক কমিট দেখা

শেষ ৩টা কমিট দেখতে চাইলে:

```bash
git log -3
```

অথবা ওয়ান লাইনে:

```bash
git log --oneline -3
```

## গ্রাফ আকারে দেখা

ব্রাঞ্চ থাকলে গ্রাফ ভিউ অনেক কাজে লাগে:

```bash
git log --oneline --graph
```

আউটপুট:

```
* a1b2c3d hello.txt আপডেট ও notes.txt যোগ করা হয়েছে
* b2c3d4e second.txt ফাইল তৈরি করেছি
* c3d4e5f প্রথম কমিট - hello.txt ফাইল যোগ করেছি
```

## নির্দিষ্ট ফাইলের হিস্ট্রি

শুধু একটা ফাইলে কি কি চেইঞ্জ হয়েছে দেখতে:

```bash
git log hello.txt
```

## লগ থেকে বের হওয়া

লগ অনেক লম্বা হলে স্ক্রল করতে হয়। বের হতে `q` চাপো।

> **টিপ:** `git log --oneline` সবচেয়ে বেশি কাজে লাগে। এটা মনে রাখো!

পরের পেজে শিখবো — পুরানো কোনো কমিটে কিভাবে ফিরে যেতে হয়।
