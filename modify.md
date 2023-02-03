This document saves knowledge gained in this source code.

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

## TODO: modify `parseContent.js` **code analysis**

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




