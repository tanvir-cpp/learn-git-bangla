# গিটহাবের সাথে লিঙ্ক

## লোকাল রিপো আর রিমোট রিপো

এতক্ষণ তুমি গিট দিয়ে তোমার কম্পিউটারে (লোকালি) কাজ করেছো। এখন তোমার কোড গিটহাবে নিয়ে যেতে হবে। এর জন্য তোমার লোকাল রিপো আর গিটহাবের রিপো — দুইটা কানেক্ট করতে হবে।

## ধাপ ১: গিটহাবে নতুন রিপো তৈরি করো

1. [github.com](https://github.com) এ লগইন করো
2. ডান পাশে উপরে **+** বাটনে ক্লিক করো
3. **New repository** সিলেক্ট করো
4. রিপোর নাম দাও (যেমন: `my-first-project`)
5. **Public** রাখো (সবাই দেখতে পারবে)
6. **Add a README file** টিক দিও **না** (কারণ লোকাল রিপো আগেই আছে)
7. **Create repository** ক্লিক করো

## ধাপ ২: লোকাল রিপোর সাথে কানেক্ট করো

গিটহাবে রিপো তৈরি করলে একটা URL পাবে। সেটা কপি করো। তারপর তোমার কম্পিউটারের টার্মিনালে:

```bash
git remote add origin https://github.com/tomar-username/my-first-project.git
```

এখানে:

- `git remote add` = রিমোট রিপো যোগ করো
- `origin` = রিমোটের নাম (কনভেনশন অনুযায়ী `origin` দেওয়া হয়)
- URL = গিটহাব রিপোর লিঙ্ক

## ধাপ ৩: চেক করো কানেক্ট হয়েছে কিনা

```bash
git remote -v
```

আউটপুট:

```
origin  https://github.com/tomar-username/my-first-project.git (fetch)
origin  https://github.com/tomar-username/my-first-project.git (push)
```

এটা দেখায় যে `origin` নামে একটা রিমোট কানেক্ট করা আছে।

## origin মানে কি?

`origin` হলো তোমার রিমোট রিপোর নাম। এটা একটা নিকনেম — পুরো URL বারবার লেখার বদলে শুধু `origin` লিখলেই হয়।

তুমি চাইলে অন্য নামও দিতে পারতে (যেমন `github` বা `server`), কিন্তু সবাই `origin` ব্যবহার করে, তাই এটাই ব্যবহার করো।

## রিমোট URL চেইঞ্জ করা

ভুল URL দিয়ে ফেললে চেইঞ্জ করতে:

```bash
git remote set-url origin https://github.com/correct-username/correct-repo.git
```

## রিমোট ডিলিট করা

```bash
git remote remove origin
```

## মনে রাখো

```
লোকাল রিপো (তোমার কম্পিউটার) ◄──── git remote ────► গিটহাব রিপো (ক্লাউড)
```

কানেকশন তৈরি হয়ে গেছে! এবার চলো শিখি কোড গিটহাবে পুশ করা।
