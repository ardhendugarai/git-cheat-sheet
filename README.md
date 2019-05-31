<h2 align="center">  Bengali git-cheat-sheet </h2>
<br>

# Git Cheat Sheet Bengali
## Index
* Set Up
* Configuration Files
* Create
* Local Changes
* Search
* Commit History
* anches & Tags
* Update @ Publish
* Merge & Rebase
* Undo
*Git Flow

# Set Up

## বর্তমান কনফিগারেশন প্রদর্শন করুন:
```
$ git config --list
```
## সংগ্রহস্থল কনফিগারেশন প্রদর্শন করুন:
```
$ git config --local --list
```

468/5000
সিস্টেম কনফিগারেশন দেখান:
```
$ git config --system --list
```
সংস্করণ ইতিহাস পর্যালোচনা করার সময় ক্রেডিট জন্য সনাক্তযোগ্য একটি নাম সেট করুন:
```
$ git config --global user.name “[firstname lastname]”
```
প্রতিটি ইতিহাস চিহ্নিতকারীর সাথে যুক্ত করা একটি ইমেল ঠিকানা সেট করুন:
```
$ git config --global user.email “[valid-email]”
```
সহজ পর্যালোচনা করার জন্য গিটের জন্য স্বয়ংক্রিয় কমান্ড লাইন রঙ সেট করুন:
```
$ git config --global color.ui auto
```
প্রতিশ্রুতি জন্য গ্লোবাল এডিটর সেট করুন
```
$ git config --global core.editor vi
```
