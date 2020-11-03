### test your typing speed without leaving the terminal

![example](./img/example.gif)

This repo is home to a self contained file `typetest`.
As is it is a near clone of [10fastfingers](https://10fastfingers.com/typing-test/english) with an added bonus of being able to see typing speed as you're typing.

Differences in the way typing speed is calculated and feedback accross platforms got me interested in writing my own program for testing typing speed.
I've come to love how simple and unrestrictive [10fastfingers](https://10fastfingers.com/typing-test/english) and [keybr](https://keybr.com) feel compared to [typingclub](https://www.typingclub.com/) and [typeracer](https://www.typeracer.com).
They all have great advantages for varying purposes but when it comes to warming up or just waiting for a compile of some program to finish (*have you tried [compiling chromium](https://www.reddit.com/r/archlinux/comments/gdeiui/ungoogledchromium_taking_a_long_time_to_build/)?*) I am yet to find a rival to [10fastfingers](https://10fastfingers.com/typing-test/english).
That is why I decided to clone its functionality and add some of the features I love from other sites.

# typetest
`typetest` is a self contained minimal typing test program written with [blessed](https://github.com/jquast/blessed/).
It calculates typing speed as sum of spaces and characters from **correctly written words** divided by test duration.
Adjustable settings are `DURATION`, `SHUFFLE` and `NUMBER_OF_ROWS`, can be set using the the command arguments.
The input text for the typing test is read from the standard input or using the [positional arguments](https://docs.python.org/3/glossary.html#term-argument).

# scappers
Along with `typetest` this repository features sample web scrappers.
`wiki` find a [featured article](https://en.wikipedia.org/wiki/Wikipedia:Featured_articles) on wikipedia and prints it.
`wiki_common` scrapes common words.
Write your own if need be, you may find some suggestions [here](https://en.wikipedia.org/wiki/Lists_of_English_words).
Use them like so: `wiki | typetest` or `wiki_common | typetest`.

```
usage: typetest [-h] [-d DURATION] [-r ROWS] [-s] [words [words ...]]

example:
  typetest -d 3.5 The typing seems really strong today.
  echo 'I love typing' | typetest
  typetest < test.txt

positional arguments:
  words                 provide words via args in lieu of stdin

optional arguments:
  -h, --help            show this help message and exit
  -d DURATION, --duration DURATION
                        duration in seconds
  -r ROWS, --rows ROWS  number of test rows to show
  -s, --shuffle         shuffle words

shortcuts:
  ^c / ctrl+c           end the test and get results now
  ^h / ctrl+h           backspace
  ^r / ctrl+r           restart the same test
  ^w / ctrl+w           delete a word
  ^u / ctrl+u           delete a word
```
