# গিটহাবে SSH ব্যবহার না করা

## SSH সেটআপ করতে চাও না?

কিছু কারণে SSH সেটআপ করা সম্ভব না বা করতে চাও না? কোনো সমস্যা নেই! HTTPS দিয়েও গিটহাবে কাজ করা যায়।

## HTTPS দিয়ে কাজ করা

HTTPS ব্যবহার করলে গিটহাব রিপোর HTTPS URL ব্যবহার করবে:

```bash
git remote add origin https://github.com/username/repo.git
```

## Personal Access Token (PAT)

গিটহাব এখন আর সরাসরি পাসওয়ার্ড সাপোর্ট করে না। HTTPS ব্যবহার করলে **Personal Access Token** দরকার হবে।

### টোকেন তৈরি করা

1. GitHub → **Settings** (প্রোফাইল ড্রপডাউন থেকে)
2. বাম পাশে **Developer settings**
3. **Personal access tokens** → **Tokens (classic)**
4. **Generate new token** → **Generate new token (classic)**
5. Note দাও (যেমন: "My Laptop Token")
6. Expiration সেট করো (30 days, 60 days, বা No expiration)
7. Scopes এ **repo** তে টিক দাও
8. **Generate token** ক্লিক করো
9. টোকেনটা কপি করো!

> **সাবধান:** টোকেন একবারই দেখানো হবে! কপি করে নিরাপদ জায়গায় রাখো।

## টোকেন ব্যবহার করা

পুশ করার সময় পাসওয়ার্ডের জায়গায় টোকেন দাও:

```
Username: tomar-username
Password: ghp_xxxxxxxxxxxxxxxxxxxx (টোকেন পেস্ট করো)
```

## বারবার টোকেন দিতে হবে?

প্রতিবার পুশ/পুল করার সময় টোকেন দেওয়া ঝামেলা। এটা সমাধান করতে **Credential Manager** ব্যবহার করো:

### Windows

Git for Windows ইন্সটল করলে Git Credential Manager আপনাআপনি ইন্সটল হয়। প্রথমবার টোকেন দিলে পরেরবার থেকে মনে রাখবে।

### Mac

```bash
git config --global credential.helper osxkeychain
```

### Linux

```bash
git config --global credential.helper store
```

> **সাবধান:** `credential.helper store` টোকেনটা প্লেইন টেক্সটে সেভ করে। বেশি সিকিউর চাইলে SSH ব্যবহার করো।

## HTTPS vs SSH

| | HTTPS | SSH |
|---|---|---|
| সেটআপ | সহজ | একটু জটিল |
| অথেনটিকেশন | টোকেন দরকার | Key দিয়ে অটো |
| ফায়ারওয়াল | সাধারণত কাজ করে | মাঝে মাঝে ব্লক হয় |
| সিকিউরিটি | ভালো | আরো ভালো |

## মনে রাখো

- HTTPS দিয়ে শুরু করো, সমস্যা নেই
- কিন্তু যখন পারো SSH সেটআপ করে ফেলো — লং টার্মে অনেক সুবিধা!

> **টিপ:** অফিস/ইউনিভার্সিটির নেটওয়ার্কে SSH পোর্ট (22) ব্লক থাকতে পারে। তখন HTTPS ই একমাত্র অপশন।
