# apibag
Simple command line tool to make http requests (work in progress)

## Install

```bash
npm install -g apibag
```
## Demo 
![apibag](https://cloud.githubusercontent.com/assets/7697632/24894708/af3d5b76-1e7b-11e7-9247-b2026ca196b9.gif)

## Why?
I love postman, but clicking around is not my favorite part of the day. However its persistent history and collections are cool features. And those are something to miss when using cli tools, like httpie or curl.

Let's  see if the same experience can be recreated in command line.

## Work in progress

apibag can make post and get requests currently, with persistent history, but that's about it! It's a work in progress.

## Milestons
  * get and post methods work just like httpie
  * Separate name spaces / bags can be defined for keeping the history.
  * Users can cd into a name space, ls to see all saved requests, cat to see each etc.


## How will this work?

I don't know. I'm just trying different ideas. So far an immersing cli tool sounds good. But later we might move it to a normal cli, with atomic single commands.

## background:
```bash
Omid
Do you have any recommendation for a friendly cli tool to work with http end points?
During development? I use:
curl
httpie
http-console
Only thing I'm missing from say, postman is history.
It's nice to be able to use the previous api calls, and even save them for ever.

Do you know an unknown unicorn in that realm?


JaniE at 11:36
If we're just riffing on this, I'd like to have a cli tool that works like:
  - npm installable
  - keep saved requests in a human-readable format in a directory, one per file, and can be parameterized and parameters provided on command line tool
  - works like imaginary-tool foobar --user 1 would run request in foobar.txt (or whatever format) and fill in template paremeter {user}
  - can make requests httpie/curl style just on the cli and then --save to imaginary-tool file format for later use
  - requests can specify headers and body
  - requests can specify an "archetype" or a "template" for shared headers for all of them, so they don't need to be duplicated (e.g. if I want all my requests to be json with certain headers)
  - has a global history in ~/.imaginary-tool where you can save global templates for cross-project user


Then I could put all those test requests in source control and version them properly, which you can do with postman, but the format is not super readable
JaniEJaniE on Fri at 11:37
If you make this I will ship you a bottle of fine whisky

```

File format

```bash
// these be http headers, like you know and love em
Header: Value
Header: {parameterized_value}
---
 // this is body, can be anything
 // but it would be nice to have comments
 // and also use relaxed-json here so it's easier to author
{ "foo": "bar"}
```
