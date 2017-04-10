# hapi.js Authentication Workshop

Last week you will have had a brief introduction to authentication during research day. The aim of this workshop is to introduce you to the methods that you can use to authenticate users with `hapi.js`.

Use [the same method as yesterday](https://github.com/foundersandcoders/oauth-workshop) - pair (with someone new this time) and don't copy/paste code. In fact, try not to look at yesterday's workshop. See how much you can do from memory, and then use the [hapi docs](https://hapijs.com/tutorials/getting-started?lang=en_US) when you get stuck.


## Getting started

1. Set up a basic hapi server. Having just done this yesterday, I won't give you too many hints now.

2. Create a new database with:
  + One table for all the students & mentors who contribute to the kitty
  + Either:
    + Simpler - one table to track the expenditure from the kitty
    + More complex - one table per type of item (e.g. `coffee`, `milk`, etc.). Don't do more than 2 or 3. This isn't database week :wink:

Just so that you don't go down a rabbit hole and spend to long on this, here are some very simple table examples:

**facsters**

Column      |     Type    |    Modifiers          
--- | --- | --- | ---
id          | SERIAL       | PRIMARY KEY  NOT NULL
name        | VARCHAR(255) | NOT NULL |

**kitty**

Column      |     Type    |    Modifiers          
--- | --- | --- | ---
id          | SERIAL       | PRIMARY KEY  NOT NULL
facster_id  | INTEGER      | FOREIGN_KEY REFERENCES facsters(id) |
item        | VARCHAR(400) | NOT NULL |
amount      | INTEGER      | NOT NULL |
spend_date  | TIMESTAMP    | NOT NULL |

Remember, you will need the following:
+ an sql file that defines your database schema (`db_build.sql` from week 6)
+ a JavaScript file that initialises a pool of connections using the `pg` module (`db_connection.js`)
+ a JavaScript file that builds runs your schema file (`db_build.js`)
