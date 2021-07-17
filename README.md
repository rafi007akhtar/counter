# counter

Welcome to the overly-simplified counter project.

This repository is a single-file folder, containing but an [index.html](index.html) file. This file serves to be the be-all and end-all of this tiny project.

## Quick setup
When you open the index file on a browser, it will show you _three_ buttons:
1. A giant red **circular button** on the middle. This will be your counter. When loading for the first time on your device, it should show **0** as the count. You can tap on it to increase the count.
2. A **Decrement count** button on top. You can tap on it to decrease the count by 1. The count cannot go below 0.
3. A **Delete progress** button on the bottom. When you click on it, the count turns to 0. Be careful with this! Once you click on it, your count will get deleted, and there is no way (so far as I know) to bring them back.

## File contents
As mentioned earlier, this repository contains only *one* HTML file. The skeleton, the stylings, and the logic are all maintained by this file. The reason for including only one file was because I wanted to create a super simple counter that *just works*. No hassle, no installation, and runs on pretty much any device with a web browser - that's what I wanted.

## How to run
Steps:
1. Download the [index.html](index.html) file on your device.
2. Open it.

That's it. That's all it takes. Once you have opened it, you can follow the steps mentioned under Quick setup and use it as needed.

## Where does it store the count
The file is designed such that even after closing the tab or the browser and reopening it, the count will show. Even if you delete the file, download it again, and reopen it, the count still shows. The only way of deleting the count from your memory is clicking on the **Delete progress** button on the bottom.

I managed to achieve this functionality using only one file by using **local storage**. If you peek into the code:
```js
// you'll see lines like
localStorage.setItem("countsNum", this.countsNum);
// and also like:
localStorage.removeItem("countsNum");
```

To the technically adept, you would have guessed by now how things are working here. The `<body>` tag in the file takes care of the skeleton of the code, the `<style>` tag takes care of the appearance, and the `<script>` tag runs the counter logic. And to retain the count in memory, `localStorage` does the trick. Hence, no need of an external file for storing the count or splitting the file into CSS or JS files. Since the size and scope of the counter is _so_ small, it all fits in a single file.