---
topic: meta
---

2026-02-02 14:57

tags: #fleeting [[plugins]]

## Text Progress bar

Deze plugin bied de mogelijkheid om emoji's en text gebasseerde progressie balken de embedden in markdown. 

# Text Progress Bars for Obsidian
## Usage

[](https://github.com/michaeladams/obsidian-text-progress-bar#usage)

To create a progress bar, start a code block with "text-progress-bar".

A minimal bar contains the bars label, how much is complete, and the total number.

Defaults will be taken from the plugin settings.

````
```text-progress-bar
Books read:1/10
```
````

[![Default example](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-default.jpg)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-default.jpg)

Optionally, all the settings can be specified:

````
```text-progress-bar
Books read:5/10
transition:|
fill:▓
empty: 
prefix:[
suffix:]
length:10
```
````

[![Default example](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-all-settings.jpg)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-all-settings.jpg)

Note that empty has " " - a special empty character.

Want emojis? We got em:

````
```text-progress-bar
Chickens hatched:5/10
fill:🐥
empty:🥚
prefix:[
suffix:]
length:10
```
````

[![Default example](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-emoji.jpg)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-emoji.jpg)

Specify a transition to display a character for partial completion:

````
```text-progress-bar
Thats no moon:10/20
transition: 🌘,🌗,🌔
fill:🌕
empty:🌑
prefix:[
suffix:]
length:3
```
````

[![Default example](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-transition-emoji.jpg)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-transition-emoji.jpg)

And use decimal numbers to specify the partial completion of emojis

````
```text-progress-bar
Books read:5.5/10
transition:📖
fill:📗
empty:📕
length:10
```
````

Or use ASCII characters for the transition:

````
```text-progress-bar
Books read:5/10
transition:⣦
fill:⣿
empty:⣀
prefix:⎸
suffix:⎹
length:3
```
````

[![ASCII Transition](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-transition-ascii.jpg)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-transition-ascii.jpg)

### Multiple progress bars.

[](https://github.com/michaeladams/obsidian-text-progress-bar#multiple-progress-bars)

Progress bars can be grouped together in one block using multiple labels.

````
```text-progress-bar
JAN:10.0/10
FEB:1.0/10
MAR:5.5/10
transition:📖
fill:📗
empty:📕
length:10
```
````

[![Grouped progress](https://github.com/michaeladams/obsidian-text-progress-bar/raw/master/images/example-multiple.png)](https://github.com/michaeladams/obsidian-text-progress-bar/blob/master/images/example-multiple.png)

## Installation

[](https://github.com/michaeladams/obsidian-text-progress-bar#installation)

The plugin can be installed manually:

1. Download the latest release
2. Extract the contents into your ./obsidian/plugins/ folder
3. Reload Obsidian
4. Enable the plugin from your settings


**Refrences**
--

Community GitHub page van de plugin
https://github.com/michaeladams/obsidian-text-progress-bar