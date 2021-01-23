# SofosIssues

A public repository made to collect issues regarding my greek-translator/analyzer [telegram bot](https://t.me/feg_exe_greek1_bot).
If you have any issue or idea to submit, feel free to do so in the issues page of this repository.

## About the bot

Sofos is a bot made in order to help people translate from greek to other languages, and is currently available on telegram.

Its main features are:
1. Integration with perseus' analysis
1. Integration with witionary translations
1. Integration with bing translations for italian
1. Support for community translations

## About language support
In this repository, together with this readme file, you'll find a json file containing all the text the bot uses.
### Text structure
Every translation has a different name, which contains translations for each language, stored under a number. Let's take "start_0" as an example:
```json
"start_0":
    {
        "0":"<b>Welcome to Unnamed bot!</b>\n——————————\nPlease select your prefered language\nPer favore seleziona il linguaggio che preferisici",
        "1":"<b>Benvenuto da Unnamed bot!</b>\n——————————\nPlease select your prefered language\nPer favore seleziona il linguaggio che preferisici"
    }
```
The way translations are stored is always similar to this:
```json
"name":
  {
    "0":"This is an english translation",
    "1":"This is an italian translation"
  }
```
First is the name of the translation, put between quotation marks. After the name of the translation, inside a curly bracket, stands a sort of list of numbers, which are paired with a translation. Since until now the bot only supports english and italian, there are only 0s and 1s. If you were to add a new language, you would just add a 2 to the list, like this:
```json
"name":
  {
    "0":"This is an english translation",
    "1":"This is an italian translation",
    "2":"This is a translation in a new language"
  }
```
Here you have a list of the various languages and of their ids. If new languages are being added, you'll be sure to find them here!
1. 0=English
1. 1=Italian

### Variables
Variables are words which vary. For example, if the bot needed to say hi to a user, it would not be possible to write a translation valid for everyone, being the name of the user something which can vary. This is where variables come in; you can recognize them because of their syntax: they are always written like §number (Like §0, §1, §2, etc.).
When translating, you should consider a variable as a unique word, and shall not, in any case, remove it. Of course the order of words can vary from language to language, just be sure to include every variable like they were a separate word.
Here you have an example, together with the text that is going to be printed out:
```json
"test":{"0":"Hi §0! How are you doing?"}
```
> Hi John! How are you doing?

Or maybe
```json
"test":{"0":"Oh look, it's §0! How are you doing?"}
```
> Oh look, it's Maria! How are you doing?

### Cross-translation references
Some translations integrate with some other translations, adding text from another tag. They just work by putting the name of the translation which contains the text they want to be integrated between $$. Here's an example:
```json
"test":{"0":"Oh look, it's §0 again! $$are_u_k$$"},
"are_u_k":{"0":"Are you ok?"}
```
> Oh look, it's John again! Are you ok?

The most advanced example of this you can find, is when a text reference contains a variable, like $$a_name_§0$$; in this case, the variable will be first replaced with its value (so if it was 123, it would become $$a_name_123$$), and then it would be linked to the corresponding text. Here is an example in which the variable's value was 2:
```json
"test":{"0":"Well, I have to say that $$answer_§0$$"},
"answer_0":{"0":"I like you"},
"answer_1":{"0":"I don't know who you are"},
"answer_2":{"0":"I want to thank you for reading to this point"}
```
> Well, I have to say that I want to thank you for reading to this point

### Adding translations
If you want to add a translation, you can do so by opening an issue, remembering to specify which language you are translating to. Remember to send translations already formatted in json format, like the given translation. So, for example:
```json
"old_tag_that_existed":{"2":"Your wonderful translation"}
```
I'll be sure to link your github in the credits page!

### Suggesting translations
If you want to suggest a different translation or correct an error, you can also do so by opening an issue.

## About ads

Since money won't rain from the sky, I built a coin system, and I plan on adding ads or a paid purchases system in order to gain something from all the time I spent and I'm still spending on this project
