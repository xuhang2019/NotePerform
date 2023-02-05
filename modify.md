This document saves knowledge gained in this source code.

## Development modification record

Create Date: 2023.2.3
Branch: dev

Useful operation:
```
# git
git checkout -b <branch_name> # create a new branch and switch to it.
git push origin <branch_name>



# visual studio code
command+shift+F: search globally
```

## Electron

main process: main.js, control different render processes, such as index.js (render index.html) 

node.js feature? there is only main.js, without main.html

almost each .js should have ipc communication (to listen main process, i.e., send messages and receive messages)

how to control node.js to change the content (dynamically): using `const aaa = document.getElementById('')`, then render `aaa`.

## About the project

First, find how to modify interpreting music notes.
**- `.\src\function\parseContent.js`**

second, merge all the code together.


index lib js:
    - codemirror
    - simple
    - musicnotes
    - soundfont-player
    - index


musicnotes: only use to **highlight** the music note? Yes!



## Knowledge

What is code mirror?
CodeMirror is a code **highlight** editor in JavaScript. (introduce .css and .js.)

`html: lib\codemirror.js`

## TODO: modify `parseContent.js` 

- [x] add major = A2 
`token <- lib/musicnotes.js CodeMirror.defineSimpleMode (a state machine)`
(very difficult)
involved: parsedContent.js, index.js, index.html (display)
Actually, I didn't see the parse title process in parsedContent.js. (Here, the content is packaged in a class)
    - [x] modify token type in parsedContent.js, still require modification in index and check errors.
    - [x] check if parseContent function remains error.
2023.2.5

- [ ] add a button or leave area to activate `drawdisplayarea`. (actually, is about a callback function.)
2023.2.5

- [ ] allow the major propety to tune the sound.
- [ ] cut down useless functions.

**code analysis**

***Whole procedure***:
    1. index.js: input code (editor)
    2. musicnote.js: define the rule of editor, a state machine
    3. parseContent.js: process code into `parsedContent` based on `musicnote.js`
    4. index.js: `drawDisplayArea`, load `parsedContent`, render to html and katex. (title, major: html; musicnotes: katex)

class:
    BeatInfo
        beatInfo={3/4}
            beatsNumber = 3
            beatsBeat = 4

    MuscialNote
        describe a note?
            3+/
            tone = 
            step = 
            length = ?
            height = ?


    ParsedContent (headInfo, bodyInfo)
            headInfo
            bodyInfo
        getPlayEvents()
        getLatexBody()

function:
    createLatexChar

LETTERNOTATION

module.exports.parseContent: -> new ParsedContent 
    apply pre-defined classes
    input: editor (area)

### analysis of `parseContent`

headInfo: content before music notes
headInfo.headEndAtLine: indicates the beginning of notes part

stage: indicate current procedure
property?
value?

Iterate line:
    judge token (seems defined in musicnotes.js, editor.getLineTokens)
    switch (process headInfo)
        token/propety type?
            keyword
            tone
            note
            operator
    process an item per loop




