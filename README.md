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
# Configuration Files
রেপোজিটরি নির্দিষ্ট কনফিগারেশন ফাইল [- লোকাল]:
```
<repo>/.git/config
```
ব্যবহারকারী নির্দিষ্ট কনফিগারেশন ফাইল [- গ্লোবাল]:
```
~/.gitconfig
```
সিস্টেম-ওয়াইড কনফিগারেশন ফাইল [- সিস্টেম]:
```
/etc/gitconfig
```
#Create

একটি বিদ্যমান সংগ্রহস্থল ক্লোন করুন:
দুটি উপায় আছে:

SSH মাধ্যমে
```
$ git clone ssh://user@domain.com/repo.git
```
HTTP মাধ্যমে
```
$ git ক্লোন http://domain.com/user/repo.git
```
বর্তমান ডিরেক্টরির মধ্যে একটি নতুন স্থানীয় সংগ্রহস্থল তৈরি করুন:
```
$ git init
```
একটি নির্দিষ্ট ডিরেক্টরির মধ্যে একটি নতুন স্থানীয় সংগ্রহস্থল তৈরি করুন:
```
$ git init <directory> 
```
# Local Changes 

কাজের ডিরেক্টরি পরিবর্তন:
```
$ git status
```
ট্র্যাক করা ফাইল পরিবর্তন:
```
$ git diff
```
একটি নির্দিষ্ট ফাইল পরিবর্তন / পার্থক্য দেখুন:
```
$ git diff <file>
```
পরবর্তী কমিটিতে সব বর্তমান পরিবর্তন যোগ করুন:
```
$ git add .
```
<ফাইল> এর মধ্যে পরবর্তী পরিবর্তনগুলিতে কিছু পরিবর্তন যুক্ত করুন:
```
$ git add -p <file>
```


ট্র্যাক ফাইলে সমস্ত স্থানীয় পরিবর্তন কমিট করুন:
```
$ git commit -a
```
পূর্বে মঞ্চ পরিবর্তন:
```
$ git commit
```
বার্তা দিয়ে Commit:
```
$ git commit -m 'message here'
```
Staging এলাকা skipping এবং বার্তা যোগ কমিট:
```
$ git commit -am 'message here'
```
কিছু পূর্ববর্তী তারিখ কমিট করুন:
```
$ git commit --date="`date --date='n day ago'`" -am "<Commit Message Here>"
```
সর্বশেষ কমিটি পরিবর্তন করুন:
### <i> প্রকাশিত কমিটি সংশোধন করবেন না!<i>
```
$ git commit -a --amend
```
শেষ কমিট সঙ্গে সংশোধন কিন্তু পূর্ববর্তী কমিট লগ বার্তা ব্যবহার করুন
প্রকাশিত কমিটি সংশোধন করবেন না!
```
$ git commit --amend --no-edit
 ```
সর্বশেষ কমিটির কমিটির তারিখ পরিবর্তন করুন:
```
GIT_COMMITTER_DATE="date" git commit --amend
  ```
সর্বশেষ কমিটির লেখক তারিখ পরিবর্তন করুন:
```
$ git commit - amend --date = "date"
```
বর্তমান শাখা থেকে অন্য কোন শাখায় অনিয়মিত পরিবর্তনগুলি সরান:
```
$ git stash
$ git checkout branch2
$ git stash pop
```
বর্তমান শাখা ফিরে স্ট্যাশ পরিবর্তন পুনরুদ্ধার করুন:
```
$ git stash appl
```
বর্তমান শাখা ফিরে বিশেষ stash পুনরুদ্ধার করুন:
{stash_number} গিট স্ট্যাশ তালিকা থেকে প্রাপ্ত করা যেতে পারে
```
$ git stash apply stash@{stash_number}
```
স্ট্যাশ পরিবর্তনের শেষ সেট সরান:
```
$ git stash drop 
```
#
