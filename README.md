<!--
author:   André Dietrich

email:    andre.dietrich@ovgu.de

version:  0.0.1

language: en

narrator: US English Female

comment:  Presentation on LiaScript at the elmeurope 2019 conference in Paris.

@red:     <bf style= "color: red">@0</bf>

link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css

import:   https://raw.githubusercontent.com/liaTemplates/vtk/master/README.md
          https://raw.githubusercontent.com/liaTemplates/rextester/master/README.md

-->



# Open-courSe development with LiaScript

<h4> (... or Markdown on steroids, featuring Elm) </h4>


| Name    | André Dietrich                    |
| ------- | --------------------------------- |
| Project | __ https://LiaScript.github.io __ |
| eMail   | andre.dietrich@ovgu.de            |
| GitHub  | https://github.com/andre-dietrich |
| Twitter | @an_dietrich                      |


                               {{1}}
*******************************************************************************

https://github.com/andre-dietrich/elmeurope-2019

![qr-image](pics/qr.png)

https://liascript.github.io/course/?https://raw.githubusercontent.com/andre-dietrich/elmeurope-2019/master/README.md

*******************************************************************************

## What is LiaScript

https://liascript.github.io/course/?https://raw.githubusercontent.com/andre-dietrich/elmeurope-2019/master/README.md#2

                --{{1}}--
Hi there. LiaScript is not intended to be
the next Markup language. It is more or less
a tool for creating interactive
screencast-like online courses. With an easy
to read and write syntax.

                --{{2}}--
You can use for example the double braces
notation as bullet-points, to indicate when
something should appear or disappear.



    {{2-3}}
              Example of an ASCII-Art diagram
    1.9 |
        |                 ***
      y |               *     *
      - | r r r r r r r*r r r r*r r r r r r r
      a |             *         *
      x |            *           *
      i | B B B B B * B B B B B B * B B B B B
      s |         *                 *
        | *  * *                       * *  *
     -1 +------------------------------------
        0              x-axis               1


                  --{{3}}--
You can apply this technique on any kind of
Markdown block, but inlining is also possible.


                    {{3}}
| This   | table                    | will  |
| :----- | :----------------------- | :---- |
| appear | at the {4}{__watch me__} | end   |


           --{{5 French Female}}--
And by using double dashes, you can mark a
paragraph as a comment that should be read
out loud.

## Prehistory

### SelectScript

... a declarative dynamic typed language for simulations and IoT, with
_ternary logic_, _SQL & spatial-temporal reasoning_, _prototypes_,
_temporal variables_, etc...

![robots in a manucactoring hall](pics/robots.png)<!--width="100%"-->


__GitHub:__ https://github.com/andre-dietrich/SelectScriptC

__Publications:__

* Reasoning in complex environments with the _SelectScript_ declarative language

  + URL: https://arxiv.org/abs/1508.04159
  + YouTube: https://youtu.be/EFRV0JSdK3M


* _SelectScript_: A query language for robotic world models and simulations

  + URL: https://ieeexplore.ieee.org/abstract/document/7140077
  + YouTube: https://youtu.be/R_PThP0gwOc


### Industrial eLab Project (BMBF)

<!-- class="animated fadeIn" -->
    {{1-2}}
![php logo](pics/php.svg)<!--
style="width: 70%;
       display: block;
       margin-left: auto;
       margin-right: auto;" -->


<!-- class="animated fadeIn" -->
    {{2-3}}
![elixir logo](pics/elixir.png)<!--
style="width: 70%;
       display: block;
       margin-left: auto;
       margin-right: auto;" -->


<!-- class="animated fadeIn" -->
    {{3}}
![editing](pics/editing.gif)<!--
style="width: 70%;
       display: block;
       margin-left: auto;
       margin-right: auto;" -->


## Let's build a Markdown-interpreter with Elm


<!-- class="animated fadeIn"-->
{{1}} Search for Markdown parsers in Elm: _only JavaScript_

<!-- class="animated fadeIn" -->
{{2}} Search for Parser libraries in Elm: ___Parser-Combinators???___

<!-- class="animated fadeIn" -->
{{3}} AntLR and compile it to: No Elm! But JavaScript.

<!-- class="animated fadeIn" -->
{{4}} What else: _Regular Expressions_

<!-- class="animated fadeIn" -->
{{5}} Go back to: __step 2__


### Modularization (Elm)

    {{0-1}}
<!--
style="width:  calc(100vh);"
class="animated fadeIn"
-->
`````````
.
├── App.elm
├── Lia.elm
└── LiaHelper.elm
`````````


    {{1-2}}
<!--
style="width:  calc(100vh * 0.8);"
class="animated fadeIn"
-->
`````````
.
├── App.elm
└── Lia
    ├── Model.elm
    ├── Parser.elm
    ├── Types.elm
    ├── Update.elm
    └── View.elm
`````````


     {{2}}
<!--
style="width:  calc(100vh * 0.5);"
class="animated fadeIn"
-->
`````````
.
├── App.elm
├── Lia
│   ├── ...
│   ├── Markdown
│   │   ├── ...
│   │   ├── Quiz
│   │   │   ├── Json.elm
│   │   │   ├── Model.elm
│   │   │   ├── Parser.elm
│   │   │   ├── Types.elm
│   │   │   ├── Update.elm
│   │   │   └── View.elm
│   │   ├── Survey
│   │   │   ├── Json.elm
│   │   │   ├── Model.elm
│   │   │   ├── Parser.elm
│   │   │   └── ..
│   │   └── ...
│   └── ...
└── ...
`````````

## LiaScript vs. LMS

    {{0-1}}
> _From Hero to Zero with Learning Management Systems._
>
> https://osf.io/3rweg/

{{1}} **Multimedia**

                           {{1}}
| System | time-on-task | # of clicks | # of pages | satisfaction |
|--------|-------------:|------------:|-----------:|-------------:|
| Canvas |        02:56 |        10.4 |        5.1 |         0.83 |
| Edmodo |        02:33 |         9.1 |        2.9 |         0.00 |
| ILIAS  |        02:59 |        11.2 |        5.3 |         0.00 |
| Moodle |        03:51 |        13.9 |        7.3 |         0.27 |


{{2}} **Quizzes**

                           {{2}}
| System | time-on-task | # of clicks | # of pages | satisfaction |
|--------|-------------:|------------:|-----------:|-------------:|
| Canvas |        08:34 |        51.2 |       15.6 |         0.38 |
| Edmodo |        05:59 |        24.9 |        8.2 |        -0.10 |
| ILIAS  |        04:04 |        19.3 |        7.7 |         0.10 |
| Moodle |        08:33 |        47.5 |        9.9 |        -0.92 |



### __Task:__ Integrating Multimedia Content

https://www.youtube.com/watch?v=8pTEmbeENF4

<!--
width="600" height="400"
-->

### __Task:__ Adding Quizzes


## Lazy Parsing & Refactoring

    {{0}}
<!-- style="width: 80%" class="animated fadeIn" -->
`````````
   Document: String                         Model
 ╔══════════════════════╗                 +---------------------+
 ║ # main title         ║                 | title: List String  |
 ║                      ║                 +---------------------+
 ║ ## sub-title         ║                 | body: List Markdown |
 ║                      ║  (JiT compile)  +---------------------+
 ║ ``` python           ║ --------------> | code: Array Code    |
 ║ print("Hello World") ║                 +---------------------+
 ║ ```                  ║                 | quiz: Array Quiz    |
 ║                      ║                 +---------------------+
 ║ ...                  ║                 | ...                 |
 ╚══════════════════════╝                 +---------------------+
`````````
                          {{1}}
<!-- style="width: 80%;" class="animated fadeIn" -->
`````````
           |
    (Preprocessing)
           |
           v

   Model: Array Slides
 +--------------------+--------------------+--------------------
 | title: main title  | title: sub-title   | title: ...
 | code:  String      | code:  String      | ...
 +--------------------+--------------------+--------------------
`````````
                          {{2}}
<!-- style="width: 80%;" class="animated fadeIn" -->
`````````
           |                                          |
     (JiT compile)                              (JiT compile)
           |                                          |
           v                                          v
 +--------------------+                     - - - - - - - - - - -
 | body: Markdown     |
 +--------------------+
 | code: Vector Code  |
 +--------------------+
 | quiz: Vector Quiz  |
 +--------------------+
 | ...                |
`````````

## Hello World

```javascript
var s = "Hello World";
alert(s);
s + 22;
```
<script>
@input
</script>


### Projects

``` js     -EvalScript.js
let who = data.first_name + " " + data.last_name;

if(data.online) {
  who + " is online"; }
else {
  who + " is NOT online"; }
```
``` json    +Data.json
{
  "first_name" :  "Sammy",
  "last_name"  :  "Shark",
  "online"     :  true
}
```
<script>
  // insert the JSON dataset into the local variable data
  let data = @input(1);

  // eval the script that uses this dataset
  eval(`@input(0)`);
</script>

## Macros

@red(See a List of Templates at:) https://github.com/LiaTemplates

``` markdown
<!--
author: ...

@red:    <bf style= "color: red">@0</bf>

@multiline_macro
<script>
  ... @0 ... @1 ... @input(1)
</script>
@end

link:     https://cdnjs.cloudflare.com/ajax/libs/animate.css/3.7.0/animate.min.css

import:   https://raw.githubusercontent.com/liaTemplates/vtk/master/README.md
          https://raw.githubusercontent.com/liaTemplates/rextester/master/README.md

attribute: _Say thank you_

-->

# Macros

@red(See a List of Templates at:) https://github.com/LiaTemplates

```


    {{1}}
``` c Rextester.c
#include<stdio.h>

int main(void) {
  printf("Hello World\n");
  return 0;
}
```
@Rextester.C


### No Brain

> This might take a while until the patient data is loaded.
>
> `@VTK.load(https://data.kitware.com/api/v1/file/58e665158d777f16d095fc2e/download)`

@VTK.load(https://data.kitware.com/api/v1/file/58e665158d777f16d095fc2e/download)


## What's Next?


                         {{0-1}}
> _Infographic: Textbook Costs Skyrocket 812% in 35 Years_
>
> [[www.aeseducation.com](https://www.aeseducation.com/blog/infographic-the-skyrocketing-cost-of-textbooks-for-schools-students)]
>
> _The cost of getting a (decent) education in India is skyrocketing_
>
> [[qz.com](https://qz.com/india/445500/the-cost-of-getting-a-decent-education-in-india-is-now-staggering/)]
>
> _College Textbook Prices Increasing Faster Than Tuition And Inflation_
>
> [[huffpost.com](https://www.huffpost.com/entry/college-textbook-prices-increase_n_2409153)]


                               {{1}}
*********************************************************************

__Atom:__

* liascript-preview: https://atom.io/packages/liascript-preview
* liascript-snippets: https://atom.io/packages/liascript-snippets

*********************************************************************

                               {{2}}
*********************************************************************

__Projects:__

* http://github.com/LiaTemplates
* http://github.com/LiaBooks

*********************************************************************

## Misc

### Messaging (Elm)

    {{0}}
<!-- class="animated fadeIn" -->
``` elm
type alias Event = { topic : String, section : Int , message : JE.Value }

update : Msg -> Model -> ( Model, Cmd Msg, Maybe Event )
...
```

    {{1}}
<!-- class="animated fadeIn" -->
``````````
  [MODULES]                       ┏━━━━━━━━━━┓      ░  [MESSAGES]
 -----------                      ┃ Terminal ┃      ░ ------------                   { ... }
                                  ┗━━━━━┳━━━━┛      ░                                 =====
                              ┏━━━━━━━━━┛           ░                                   |
      ┌─┬─┬─┬───        ┌─┬─┲━┻━┱───                ░                                   v
 Quiz │0│1│2│...   Code │0│1┃ 2 ┃...                ░      { top: "term", sec: ., msg: ... }
      └┬┴┬┴┬┴───        └┬┴┬┺━┳━┹───                ░       ===============================
       └ ┴ ┼ ─ ─ ─       └ ┴ ─┠ ─ ─ ─               ░                                   |
           └ ─ ─ ─ ─ ─ ─ ─┲━━━┛                     ░                                   |
 ┌──────────┐         ┌─┲━┻━┱─┬─────                ░                                   v
 │ Settings │  Slides │0┃ 1 ┃2│ ...                 ░      { top: "code", sec: 2, msg: ... }
 └─────┬────┘         └┬┺━┳━┹┬┴─────                ░       ===============================
       │               └─ ╂ ─┴ ─ ─ ─                ░                                   |
       │            ┏━━━━━┛                         ░                                   |
 ┏━━━━━┷━━━━━━━━━━━━┻━━━━━━━┓                       ░                                   v
 ┃         LiaScript        ┃                       ░     { top: "slide", sec: 1, msg: ... }
 ┗━━━━━━━━━━━━━━━━━━━━━━━━━━┛                       ░
         |         ^                                ░
         v  ports  |                                ░
``````````



### Lifting a Project and Dependencies to Elm 0.19

<!-- class="animated fadeIn"-->
{{1}} ** Remain on Elm 0.18!!! **

<!-- class="animated fadeIn"-->
{{2}} Update your project first --> webcomponents, ports, operators, lazy, etc.

<!-- class="animated fadeIn"-->
{{3}} Update the libraries --> operators, lazy, etc.

<!-- class="animated fadeIn"-->
{{4}} Upgrade your libraries to Elm 0.19

<!-- class="animated fadeIn"-->
{{5}} Upgrade your project to Elm 0.19
