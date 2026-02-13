# ব্রাঞ্চ এ চেকআউট

## চেকআউট মানে কি?

চেকআউট মানে এক ব্রাঞ্চ থেকে আরেক ব্রাঞ্চে যাওয়া। ধরো তুমি এখন `main` ব্রাঞ্চে আছো, তুমি `dark-mode` ব্রাঞ্চে যেতে চাও। এটাকেই বলে চেকআউট।

## ব্রাঞ্চ বদলানো

```bash
git checkout dark-mode
```

অথবা নতুন ভার্শনে:

```bash
git switch dark-mode
```

আউটপুট:

```
Switched to branch 'dark-mode'
```

## কোন ব্রাঞ্চে আছো চেক করো

```bash
git branch
```

আউটপুট:

```
* dark-mode
  main
```

`*` এখন `dark-mode` এ — মানে তুমি `dark-mode` ব্রাঞ্চে আছো!

## আবার main এ ফিরে যাওয়া

```bash
git checkout main
```

অথবা:

```bash
git switch main
```

## checkout vs switch — কোনটা ব্যবহার করবো?

`git switch` হলো নতুন কমান্ড, শুধু ব্রাঞ্চ বদলানোর জন্য। `git checkout` পুরানো কমান্ড, এটা আরো অনেক কাজ করে (ফাইল রিস্টোর, পুরানো কমিটে যাওয়া ইত্যাদি)।

| কাজ | পুরানো উপায় | নতুন উপায় |
|---|---|---|
| ব্রাঞ্চ বদলানো | `git checkout dark-mode` | `git switch dark-mode` |
| নতুন ব্রাঞ্চ তৈরি ও যাওয়া | `git checkout -b new-branch` | `git switch -c new-branch` |

দুইটাই কাজ করে। তবে `git switch` বেশি ক্লিয়ার, কারণ এটা শুধু ব্রাঞ্চের জন্য।

## গুরুত্বপূর্ণ কথা

ব্রাঞ্চ বদলানোর আগে নিশ্চিত করো তোমার কোনো আনকমিটেড চেইঞ্জ নেই। `git status` দিয়ে চেক করো:

```bash
git status
```

যদি "working tree clean" দেখায়, তাহলে নিশ্চিন্তে ব্রাঞ্চ বদলাও। নাহলে আগে কমিট করো অথবা স্ট্যাশ করো (স্ট্যাশ পরে শিখবো)।

## উদাহরণ: পুরো ফ্লো

```bash
# main ব্রাঞ্চে আছো
git branch
# * main

# dark-mode ব্রাঞ্চে যাও
git switch dark-mode
# Switched to branch 'dark-mode'

# কোন ব্রাঞ্চে আছো চেক করো
git branch
# * dark-mode
#   main

# আবার main এ ফিরে যাও
git switch main
```

পরের পেজে শিখবো — ব্রাঞ্চে গিয়ে কিভাবে কাজ করবে এবং কমিট করবে।
