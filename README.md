# Grok

Grok is memoise card tool

using the next technologies:

- Clojure
- Datomic
- ClojureScript
- Re-Frame
- DataScript (via Re-Posh)

# Information Model

## User
- id        (uuid)
- full-name (string)
- username  (string)
- email     (string => unique)
- password  (string => hashed)
- token     (string)

## Desks
- id        (uuid)
- author    (Ref)
- title     (string)
- tags      (vector of strings)

## Cards
- id                (uuid)
- desk              (Ref)
- front             (string)
- back              (string)
- progress          (long)
- next-study-date   (date|instant)

# HTTP Rest endpoints

## Auth
/api/login
- POST => login a user
/api/register
- POST => register a user

## Users
/api/users/:user-id
- GET    => get a single user by ID
- PUT    => update a user
- DELETE => delete a user

/api/users
- POST   => create a new user

## Desks
/api/users/:user-id/desks/:desk-id
- GET    => get a single desk by ID belonging to a user
- PUT    => update a desk
- DELETE => delete a desk

/api/users/:user-id/desks
- POST   => create a new desk

## Cards
/api/users/:user-id/desks/:desk-id/cards/:card-id
- GET    => get a single card by ID belonging to a desk
- PUT    => update a card
- DELETE => delete a card

/api/users/:user-id/desks/:desk-id/cards
- POST   => create a new card

how to get datomic locally
https://nextjournal.com/vgautam/getting-started-with-datomic-and-postgres