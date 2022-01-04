# Examples of Entities

* Users
* Stores
* Teachers
* Students
* Orders
* Assignments
* Purchases
* Clothes
* Politics
* Organizations
* Cultures
* Sessions
* Confirmation Codes
* Connections
* Follows
* Likes
* Upvotes/Downvotes
* Permissions

# Examples of Relationships

* Users can...
  * Place orders
  * Start/end sessions
  * Make connections
  * Like posts
  * Provide (or have) permissions
* Teachers can...
  * Create assignments
  * Assign assignments... to Students
    * Teachers are related to students through assignments
* Students belong to a group
* Students have required materials (a table that could contain things like books, tools, or software)

# What do I want to do with my data?

* Teachers should know who they've assigned assignments to
* Teachers should know who their students are
* Teachers should be able to check whether students have completed assignments
* It should be possible to know how long an assignment took to complete
* It should be possible to know when an assignment was assigned
* Teachers should know whether students are/have:
  * Currently enrolled
  * Graduated
  * Dropped out
* Teachers know the assignment due date
* Teachers know whether the assignment was accepted or rejected
* Students should know which assignments come from which teachers
* Students should know which group(s) they belong to
* Students should know which materials they require for each assignment (course?)

# Entities

* Teachers
* Students
* Assignments
* Courses
* Groups
* Materials

# Relationships

* Teachers create assignments
* Teachers assign assignments to students
* Students enroll in courses
* Teachers have courses
* Students belong to groups
* Teachers belong to groups
* Assignments belong to courses
* Materials belong to students
* Courses have materials


# Naming Conventions and Other Best Practices

* Table names should be plural
* Table and column names should be snake case
  * snake_case
  * camelCase -> `camelcase`
  * PascalCase
  * SCREAMING_SNAKE_CASE
  * kebab-case
  * SCREAMING-KEBAB-CASE


Why snake case? SQL is case-insensitive, so these are all equivalent:

`SELECT * FROM USERS`
`select * from users`
`selecT * fRoM USers`

That gets weird (hard to read, or ambiguous) when you have table names with more than one word:

`studentsAssignments`

`SELECT * FROM STUDENTSASSIGNMENTS`

* Primary keys should be called `id`
* Foreign keys should be called `other_table_name_id`
  * e.g. `teacher_id`, `user_id`, etc.
  * The name of the other table should be singularized
* Primary keys and foreign keys should almost always be `int`
* For every other column, you have to pick your own type
  * Usually, `text` is fine
  * For numbers, `numeric` is the safe bet, but `int` is often fine
  * For dates, we have:
    * `timestamp` - An exact moment in time (down to the microsecond)
    * `date` - A year-month-day, but no time (e.g. 2022-01-03)
    * `time` - A time, but with no particular date (e.g. 2:00 PM)
    * `interval` - A time range (e.g. 16 days, 3 hours, and 22 minutes)
  * JSON (or even better: JSONB) is great for storing/querying whole objects, but try to stay away from it for now
  * Postgres supports [many, _many_ types](https://www.postgresql.org/docs/9.5/datatype.html) that you can gradually learn about and try out on your own. Some good ones to keep an eye on:
    * UUID - Unique, non-sequential IDs, which could be good for primary keys or random-ish resource links
    * Booleans
    * The monetary types
    * The geometric types (points, polygons, circles, etc.)
    * Postgres arrays

## The ERD that we made

To open it, download the file `w05d2-2022-01-03-teachers-students-erd.drawio` in this repo. Then go to [draw.io](draw.io) and select `File > Open from... > Device...` and select that file.

Alternatively, get the URL in this repo for that file and paste it into `File > Open from... > URL...`.
