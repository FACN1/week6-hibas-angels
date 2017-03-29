# week6-hibas-angels
Hiba LOVES Reading, but she doesn't have a good place to see which books her friends might be able to offer her. So Hiba's Angels decided to create Hiba Reads.

## Outline
Our website will show a list of books owned by members of the F&C community. It will offer people the chance to add books they own to the list, and make a reservation to borrow a book they want to read.

## User Stories
**As a member of F&C Nazareth community:**
> I want to see a list of books people own

> So that I can browse and see if I'm interested in any

**As a member of F&C Nazareth community who owns some books:**
> I want to be able to add my book to the list

> So other people can see information about my book and maybe borrow it

**As an avid reader in F&C Nazareth community who likes to stick to a carefully structured timetable:**
> I want to be able to reserve a book on the website

> So I can be sure I will have a chance to read it at a time which is convenient for me

## Schema
#### books

Column   |          Type          | Modifiers | Info
--- | --- | --- | ---
 id         | integer                | not null | primary key, serial
 title      | character varying(100) | not null |
 author     | character varying(100) |          |
 owner      | character varying(30)  | not null |
 summary    | TEXT                   | not null |
 date_added | date                   |          |


#### reservations
Column    |         Type          | Modifiers | Info
--- | --- | --- | ---
  id           | integer               | not null | primary key, serial
  book_id      | integer               | not null | foreign key, references books(id)
  name         | character varying(30) | not null |
  from_date    | date                  | not null |
  to_date      | date                  | not null |
  date_created | date                  |          |

## Stretch Goals
- Input validation
- Show which books are currently available
- HTML Templates
- generate list.html file on server
