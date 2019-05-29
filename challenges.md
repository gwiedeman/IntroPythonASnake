# Challenges

ArchivesSnake Challenges

Slides: [http://www.gregwiedeman.com/presentations/workshop/challenges.html](http://www.gregwiedeman.com/presentations/workshop/challenges.html)

## Help

* [Syntax](https://github.com/gwiedeman/IntroPythonASnake/blob/master/syntax.md)
* [Data](https://github.com/gwiedeman/IntroPythonASnake/blob/master/data.md)
* [ArchivesSnake Commonly Used Objects](https://github.com/archivesspace-labs/ArchivesSnake/wiki/Commonly-Used-Objects)


## Challenge 1: Counting Files

* Hint: try `collection = repo.resources(number)`
* How many files are in a collection?
* Try a resource with series, etc.

## Challenge 2: Total Extent

* How many cubic feet are in the repository?
* There may be different types: `cubic feet` and `cubic ft.`

## Challenge 3: Restrictions

* Do any files in a collection have access restrictions?
    * get a list of `ref_id`s and titles
* Is there odd or inconsistent language in notes?
* How many collection have access restrictions?
* try `.resource(157)` if you can't find any


##  Challenge 4: Bad Data

* Do any folder titles start or end with spaces?
* Can you find abbreviations?
* Inconsistent hyphen usage?
* Can you find old HTML special characters?
    * [HTML Special Characters](https://www.html.am/reference/html-special-characters.cfm)
* Test code on one resource
    * Once it works, apply to all


## Challenge 5: Subjects

* Can you find duplicate subject records?
* try `for subject in repo.subjects`

## Challenge 6: DACS notes

* Which Collections do not have DACS minimum notes?
* Test code on one resource
    * Once it works, apply to all
* Use [DACS Single-level Required](https://www2.archivists.org/standards/DACS/part_I/chapter_1)


## Challenge 7: Boxes

* How many oversized boxes are in a collection? 
* Are the the labeles uniform?
  * `oversized`
  * `Oversized`
  * `Oversize`
* Try `top_container.reify()` when you get `{"ref: "/repositories/2/top_containers/54"}`

---

[Part 5: Advanced](advanced.md)