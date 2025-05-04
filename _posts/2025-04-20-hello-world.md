---
layout: post 
title: "hello"
date: 2025-05-04 16:00:00 -0700 # Use full date/time/timezone for accurate sorting
categories: ['misc']
---

Hello, my name is Dominic, as you may have guessed from the site domain. I made this github repo a long time ago, before considering the privacy concerns of hosting public source code under my full name. 

---

I set up this site using github pages and jekyll, their default static site generator. I think the jekyll template gemini generated for me was garbage. It will stay until I get annoyed with it.

I originally wanted to host a static site on a raspberry pi, with tiny file sizes and a fast file serving software that would let me get away with a low-power, fanless server sitting in a corner of my office. I wanted to write, and I wanted to create games. I think I still want to do these things. I would gladly constrain both of these activities to small file sizes, though file size matters less for text. 

As it turns out, github pages is free and comes with a static site generator. There's still *some* rational for keeping file sizes small, in that ["Published GitHub Pages sites may be no larger than 1 GB."](https://docs.github.com/en/pages/getting-started-with-github-pages/github-pages-limits#usage-limits)

The more interesting problem is serving small games. Godot, the game engine I prefer, can build games that run in-browser. Though uncompressed web builds sit around 15MB at their smallest. Godot has some [documentation](https://docs.godotengine.org/en/stable/contributing/development/compiling/optimizing_for_size.html) on reducing the build size, and [popcar wrote a good summary](https://popcar.bearblog.dev/how-to-minify-godots-build-size/#conclusion). The compressed web-version can be under 3MB.

Another option is writing games using javascript drawn on a canvas - there are a number of resources on the [js13kGames](https://js13kgames.github.io/resources/) website. This is a bit of a rabbit hole, an entire niche dedicated to writing games that fit under 13KB. The two frameworks I had in my notes were kontra.js and littlejs.js, uncompressed at 33KB and 50KB respectively (might be off, these numbers are coming from my network tab in FireFox). These are pretty small, but I wasn't jazzed about writing games in JavaScript (or puzzling out the TypeScript setup).

When I was playing games listed on the js13kGames site, I made the connection that while the file size is small, the CPU requirements to run the game may not be. As of 5 years ago my computer could be described as beefy, but some of these games made my fans unexpectedly loud. I didn't list this earlier, or really realize it myself, but I wanted the games I wrote to be portable.

What I really want (I think?) is a fantasy console. Designed in the spirit of retro game console hardware, they typically have imposed constraints that mimic the hardware constraints of old consoles, yet can run "cartridges" in a browser or natively on your computer (or raspberry pi).

[UXN](https://100r.co/site/uxn.html)
- written in opcodes (looks like a more convient assembly) for a stack based VM
- ~22KB in files for web emulator (though some probably aren't needed)
- developers live on a boat

[PICO-8](https://www.lexaloffle.com/pico-8.php)
- have to pay
- lua (without the lua std lib)
- did not check runtime

[TIC-80](https://tic80.com/)
- similar to PICO-8
- scripting languages (lua/javascript/others)
- ~60KB runtime

[WASM-4](https://wasm4.org/)
- web assembly supported languages (C/C++/D/Rust/Zig/others)
- ~24KB runtime
- adds a native gamepad for mobile :o

For now, I'm going with WASM-4 because of the language choices and runtime size. Though I admit the other fantasy consoles are more advanced (as in, have more than 4 colors, larger display, etc.).
