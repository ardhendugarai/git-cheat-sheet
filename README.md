<h2 align="center">  Bengali git-cheat-sheet </h2>
<br>

<p>
    <img src="https://drive.google.com/file/d/1KKphbhaUX-_xEVooqHEML5ScFxlznNJ0/view?usp=sharing"  />
</p>

# Why?
> This is a collection of Git commands.  
> I believe that we can find something interesting and learn somthing.  
> This idea comes from [this project](https://github.com/github/training-kit/blob/master/downloads/github-git-cheat-sheet.md)





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
 
# Share  
> Like this project? Why not share to your friend :)  
>   
> <a href="https://twitter.com/intent/tweet?text=Look%20at%20this%20nice%20project,%20a%20collection%20of%20Android%20open%20source%20apps.%20Made%20by%20@pcq019.%20https://github.com/pcqpcq/open-source-android-apps" target="_blank" title="share to twitter" style="width:100%"><img src="http://i.imgur.com/GlSWEr7.png" title="share to twitter"/></a>&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://www.facebook.com/sharer/sharer.php?u=https://github.com/pcqpcq/open-source-android-apps" target="_blank" title="share to facebook" style="width:100%"><img src="http://i.imgur.com/0evE2QJ.png" title="share to facebook"/></a>&nbsp;&nbsp;&nbsp;&nbsp;<a href="https://plus.google.com/share?url=https://github.com/pcqpcq/open-source-android-apps" target="_blank" title="share to google+" style="width:100%"><img src="http://i.imgur.com/zvDBPqj.png" title="share to google+"/></a>&nbsp;&nbsp;&nbsp;&nbsp;<a href="http://service.weibo.com/share/share.php?searchPic=false&title=Android%25E5%25BC%2580%25E6%25BA%2590%25E5%25BA%2594%25E7%2594%25A8%25E9%259B%2586%25E5%2590%2588%2520by%2520@pcqpcq%2520&url=https://github.com/pcqpcq/open-source-android-apps&utm_content=share_button&utm_campaign=post_show&utm_medium=github&utm_source=weibo" target="_blank" title="share to sina weibo" style="width:100%"><img src="http://i.imgur.com/pH9q4qu.png" title="share to sina weibo"/></a> 
 
 
 
