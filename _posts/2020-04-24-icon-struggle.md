---
layout: post
title:  "The journey to fix one icon"
date:   2020-04-24 23:10:00 -0700
excerpt_separator: ---
---

Now comes with an interesting method for ultimate system customization!

---

### Why?

To write this blog I use a text editor called [VSCodium.](https://vscodium.com/){:target="_blank"} It's a free and libre build of VSCode without any Microsoft telemetry or other proprietary code. (I strongly suggest that you migrate if it fits your workflow) Now as a previous user of VSCode and VSCode Insiders, I was starting to hate this new icon that came with VSCodium.

> ![VSCodium's logo](https://avatars0.githubusercontent.com/u/40338071?s=100)

*VSCodium's logo*

To me, it just looks  unappealing and unoriginal. Keeping most desktop platforms in mind, it simply doesn't fit in well with any other programs or system elements. So I got to thinking... How can I get rid of this thing?

### Creating a replacement

As of writing, I have about three years of experience with [Figma](https://figma.com){:target="_blank"}, the popular Sketchapp-killer. I'm no great designer by any means, but I wanted to make something quick yet high quality. So I decided to go the easy route: take VSCode's current logo (which I very much admire) and build on top of it.

I took the SVG of the current logo, mixing in the outer box from the macOS app icon, and colored it red / blue. The logo appears to be a nice evolution (and looks pretty on my taskbar). You can download the SVG's from the images below.

> ![VSCode's current logo](https://upload.wikimedia.org/wikipedia/commons/9/9a/Visual_Studio_Code_1.35_icon.svg){:height="100px" width="100px"}

![New icon but red](/assets/posts/2020-04-25-icon-struggle/vscode-red.svg){:height="100px" width="100px"}
![New icon but blue](/assets/posts/2020-04-25-icon-struggle/vscode.svg){:height="100px" width="100px"}

*Original and the two new variants*

### Which path to take?

Now that I had my pretty icons, I had to figure out a way to apply them to the application itself. After some research, there was one clear option: **Apply the ICO directly to the shortcut.** Now this solution works in practically every case, but I felt that the solution was lacking elegance. So what does one do?

While exploring the methods to change an icon on Windows, I remembered something. The system itself uses .dll files to store icons somehow. When changing the icon for a system program, you're presented with this friendly little dialog box:

![Icon dialog box](/assets/posts/2020-04-25-icon-struggle/choose-icon.png)

After "discovering" this, I realized: these things are practically icon packs provided by the system. Why not use the same format to store custom icons? This approach has a few pros and cons. 

Getting icons into a .dll in the first place proved to be more extensive than expected. This can be intimidating for a new person and requires a significantly higher amount of effort. 

Fortunately, once the icons are dropped in somehow, this new .dll becomes an extremely portable and convenient way to both store and transfer custom icons. Only one file to backup. Plus, once the tools are set up, it's pretty trivial to add new icons to the pack.

### Getting it done

So to get started, I needed three things.
* [.png to .ico image converter]((https://icoconvert.com/old.php){:target="_blank"})
* A way to edit and add to .dll files
* My icon

Getting the first box checked off that list was trivial. I already had an icon at least 256px in size and with transparency. I just dropped the .png from Figma in, selected the Windows option, and it exported as .ico. The option I used exports in five sizes:
* 16 × 16
* 24 × 24
* 32 × 32
* 48 × 48
* 256 × 256

This should do just fine for most use-cases, but if more are needed the custom option is also there. Once exported, I downloaded [Resource Hacker](http://www.angusj.com/resourcehacker){:target="_blank"}, which is a well featured program for our purposes. All I had to do was hit new, drop in the ico, and save it to a .dll file. (I had to select .dll in the save as dialog or else it saves as another format)

Now that I had this .dll, I added some more icons and now have a portable Windows icon library!

![Icon library](/assets/posts/2020-04-24-icon-struggle/shortcut-properties.png)

---

*Questions or comments? [Get in touch!](/about#contact){:target="_blank"}*