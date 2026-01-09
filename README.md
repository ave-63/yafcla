# Yet Another First Course in Linear Algebra

Quick download: [yafcla_book.pdf](https://ben-smith.thegood.cloud/s/bKBRKBKtKfkpe7b) [yafcla_notes.pdf](https://ben-smith.thegood.cloud/s/YjKqFGim4CwKWWj)

License: CC-BY-SA 4.0

## Preface for Instructors
### Features

There are many free elementary linear algebra textbooks to choose from. Here are some features of this one:

- **Lots of exercises.** Most sections have 20 to 50, including some true/false, basic calculations, easy proofs, and a few hard proofs. There's an emphasis on making connections between a graphical view of linear combinations, systems of linear equations, linear transformations, and matrix-vector multiplication.
- **Open source.** You are free to modify your own copy of the latex code as much or as little as you like, distribute your version freely, as long as you use the CC BY-SA 4.0 license and give me credit (eg, "by Ben Smith and Your Name").
- **Lecture notes/textbook combo.** The file `yafcla_notes.pdf` includes big blank spaces to work out examples and some proofs in class. The file `yafcla_book.pdf` includes the same content but with example solutions and all proofs included. In class, the instructor can either annotate the PDF with tablet/projector, or write on the printed notes with a document camera/projector, or record videos for a flipped classroom. Students can write on the printed notes or annotate their copy of the PDF notes. The landscape orientation was chosen because it's the natural orientation of most screens. Instructors probably want to modify the lecture notes to fit their class, by expanding/contracting blank space, or by adding/removing examples or space for proofs.
- **Flexible rigor.**  In my experience, expecting linear algebra students to write some simple proofs in HW and tests shakes them out of their recipe-following habits from earlier math classes, and results in much better understanding of the concepts. The subject matter is ripe for lots of simple proof exercises. It's also a good place to learn *about* mathematical rigor, and one principle of mathematical rigor is that every theorem should have a proof, based on previous definitions and theorem; so, in the textbook, every theorem (with one exception in chapter 3) is proven. That said, depending on your students, it's probably not a good idea to spend class time proving everything. Some of the proofs are much harder than anything I'd expect a student to do, and some are tedious and not instructive. For the proofs I teach in my class, there's a blank space in the lecture notes under the theorem, and other proofs are relegated to the textbook. In your class, you may prefer to cover more or fewer proofs. You can even skip assigning proofs for HW altogether. 
- **Motivation first.** Where possible, I have tried to include concrete examples to illustrate definitions and theorems *before* the definition/theorem. Sometimes these give an argument why a theorem should true in general, which I've found is very helpful for students at this level, but shouldn't be confused with a "proof" by example. The exposition in chapters 3 and 4 are unconventional, in a motivation-first kind of way. Chapter 3 introduces determinants as *signed volume* of parallelograms/parallelopipeds, and shows how this leads to the traditional cofactor expansion, an approach inspired by Sergei Treil's excellent *Linear Algebra Done Wrong*. Chapter 4 covers linear difference equations and diagonalizability before eigenstuff, which arises naturally as a way to describe linear difference equations.
- **Brisk pace.** At my school, linear algebra is sadly only a 3-unit class which meets twice a week. This makes it hard to finish the material with many textbooks, which are often divided into too many sections, or repeat too much material. This book covers a standard outline of topics, plus an optional proof-writing section, in 25 sections (or, it *will* have 25 sections, after I write chapter 6). The longer sections are divided into subsections, in case your school has shorter class periods.
- **No calculator needed.** Every exercise and example in the book can be done with a reasonable amount of computation by hand. Fractions and big numbers are avoided. Instead of asking questions like "*diagonalize the following $3\times 3$ matrix*" which takes many steps and may require a computer, we'll have questions like "*write the characteristic equation of the following matrix*," or "*given that the eigenvalues of the following matrix are 8, 9, and 10, diagonalize it.*" I have a few reasons for doing this. One is that I can give exams with no calculators allowed, which eliminates the advantage that students students with a pricey graphing calculators have. Another reason is that I believe that doing mental math gives students a better *feel* for things like linear combinations and matrix multiplication. 

## Possible downsides
Here are some things that you may find are downsides of the book:
- **No technology instruction.** If you want to teach your students to use sympy, sage, or MATLAB, this book won't help you do it. And all of the exercises are doable by hand, so students won't feel motivated to use technology. If you have time, and want to make technology part of your class, I recommend David Austin's excellent free online book *Understanding Linear Algebra*, which teaches sage with fancy embedded code widgets throughout the book. It also has some excellent application sections which you could use to supplement this book.
- **Not a ton of applications.** This book does have some application exercises, and I do try hard to give a sense of how linear algebra is useful for anyone studying or working in STEM. But it doesn't include the wide range of application problems that some books have. Again, you may want to supplement with Austin. And if you have problems you think I should include, feel free to email them to me at smithbt@laccd.edu or with a github pull request.
- **It is a work in progress.** Here is a list of things, from highest to lowest priority, that I still need to do, as of January 8, 2026:
  - A mini-section about the Graham-Schmidt process.
  - Chapter 6 (Symmetric matrices and quadratic forms).
  - More synthesis/review type questions in the last few chapters.
  - Solutions to exercises.
  - More application exercises throughout.

## How to compile your own version
There are many good reasons to edit the latex code and compile your own version. Maybe you want your own version of the lecture notes with different examples, or more/less blank space. Maybe you want to add your own exercises. Maybe you want the book to be in portrait orientation. Maybe you want little pictures of cute cats on every page. Go for it! Here's what you need to do:
1. Install a distribution of latex on your computer. Windows users usually use MiKTeX, mac users usually use MacTex, and linux users usually use TeXLive.
2. Make your changes to the `yafcla.tex` file. If you want to make a version of the lecture notes, make sure the second of the following two lines is commented out like so:

```
\lecturenotestrue  % comment out with % for textbook
%\lecturenotesfalse % comment out with % for lecture notes
```
This will make it so anything in a `book` environment will be ignored when you compile. If you want to make a version of the textbook, move the `%` to the other line and anything inside a `notes` environment will be ignored.
3. In a terminal (aka console or command prompt), use `cd` to  navigate to the directory where you have your `yafcla.tex` file, and run the command:

```
lualatex --file-line-error --synctex=1 -interaction=nonstopmode yafcla.tex
```
This may prompt you to install a bunch of latex packages, and may take some time, but it should eventually create `yafcla.pdf`. Then, run the above command again because the first time, labels and references won't be linked up. Then you should rename `yafcla.pdf` to something else, like `yafcla_book.pdf` or `yafcla_notes.pdf`, so that doesn't get overwritten when you compile the other version.
