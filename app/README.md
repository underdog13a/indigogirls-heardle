# zayn-heardle

_[ZAYN Heardle](https://zayn-heardle.glitch.me/) (or Zeardle, if you will) by [@eggtartemily](https://twitter.com/eggtartemily)_

Updated as of Aug 22, 2022

This is a spin-off of the original [Heardle](https://www.spotify.com/heardle/) but for ZAYN songs. Each song is randomly chosen from his discography, including features. I do not own any rights to the songs used in this game. All copyright goes to ZAYN, RCA Records, and other relevant parties.

**Important note:** Please either remove my Twitter handle or change it to yours in the About tab of the game (line 3816 in the `main.js` file) unless you are giving credit. I have gotten too many DMs about Heardle spin-offs that I did not create.

**Disclaimer:** Please know that this project is not perfect. I acknowledge this. I am not a web developer. I remixed someone else's custom Heardle but fixed some bugs I had the competency to fix and wrote this guide to make it as reproducible and digestible as possible (this is my contribution to the stan community). Thanks for the patience.

### How to create your own custom Heardle

1. Create a Glitch account.
2. Remix this project and rename the project to what you want the game link to be (e.g. artist-heardle).
3. In the `index.html` file, **remove the Google Tag Manager tags** in lines 4-17 and lines 98-107. You can replace them with your own if you want to track your site usage but it's optional. Here are [set-up instructions for Google Analytics](https://support.google.com/analytics/answer/9304153) to get started if you're interested.
4. In the `index.html` file, change every instance of 'ZAYN' to your artist. You can find and replace all by hitting command+option+F on Mac (I don't know what the shortcut is on Windows).
5. In the `index.html` file, there is a long link to a photo of ZAYN. Replace every instance of this link with a URL to a photo of your choice.
6. In the `main.js` file, go to line 9071 where the variable `const Cn` is defined. This is your list of songs. The songs should go in the order you want the game to go. You can manually enter the songs or if you know how to, you can write a separate script to randomize the tracks and then just copy and paste. **Note: These tracks have to follow the format `Artist - Track Title` for it to display correctly in the SoundCloud widget.**
7. Next, in the `main.js` file, scroll down a bit to the section with all the SoundCloud links. Here, you will need to replace each URL and title with the corresponding track in the list that you specified in Step 6. **This has to be in the same order.** Again, the answer needs to be in the `Artist - Track Title` format.
8. In the `main.js` file, search for every instance of 'ZAYN'. These will include the text for the about tab, game link, game messages, etc. Replace these with your artist and customize the text to your liking. **Important:** Change the game link in the clipboard copy to your custom Heardle link. If you forget, users who copy their results will copy the link to this ZAYN Heardle instead. Search 'zayn-heardle.glitch.me' if you can't find the line of code. Also, **please remove my Twitter username** (unless you're giving credit) from the About section, as mentioned in the note above.
9. In the `main.js` file, find where `const Vt` is defined. Below that, there will be a list of game messages that will show depending on how many tries the user guesses the song in. The order goes: failure, 1 try, 2 tries,..., 6 tries. Customize these to your liking.
10. Also in this section is the variable `startDate`. Theoretically, you would change this to the current date so that the game starts with the first track you listed. However, I noticed that if you do this, it will mess up the SoundCloud player. I ended up entering a date like a week earlier which was the latest date I could use without messing up the player, so unfortunately, the game starts at #8. I don't know why this happens. It seems like a bug in the original Heardle code as well, but I don't know JavaScript well enough to know how to fix it. It's not perfect, but as a hacky workaround, you can copy and re-paste tracks 1-7 elsewhere in the list if you still want to include them.
11. As a final check, search the `index.html` and `main.js` files one more time for any instances of 'ZAYN' or 'eggtartemily' to ensure you customized everything.

**UPDATE 5/17:** I was told that the bug in Step 10 was fixed (maybe by Glitch?). Hopefully it now works for you without issue.

Now you're done with all the necessary changes. Congrats! Read on for optional edits.

1. In the `bundle.css` file, go to line 788 (or search 'root'). Here you can change the different accent colors for your game. Simply replace the HEX color codes with ones you want.
2. You are currently reading the `README.md` file. Once you no longer need this, you can delete all this text and write whatever information you want to include about your project.
3. Lastly, share your custom Heardle!

### FAQ
_Why am I just seeing a black screen?_

If you are currently developing your custom Heardle and you see a black screen, then you likely have a typo somewhere that prevents the JavaScript from rendering. If your Heardle has been working for a while and you are just now seeing a black screen, then your game has reached the end of the track list. I don't know how to make the list automatically loop but a hacky workaround is to just reset the `startDate` variable.

_I'm running into some other issue._

I recommend starting over and ensuring you don't accidentally modify something that should not be removed/changed. This includes commas, periods, parentheses, etc.

_Why does this guide use SoundCloud? The original Heardle is powered by Spotify._

The original Heardle was actually powered by SoundCloud until Spotify acquired it and migrated it to its own infrastructure. This guide and many other custom Heardles were created prior to the acquisition.

_What is your favorite ZAYN song?_

[sHe](https://open.spotify.com/track/48qaQk75LoWs5qgsZgbkA5?si=2b28b1817f47402f)!