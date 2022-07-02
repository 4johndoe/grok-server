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

## Topics
- author    (Ref)
- title     (string)
- tags      (vector of strings)

## Cards
- topic             (Ref)
- front             (string)
- back              (string)
- progress          (long)
- next-study-date   (date|instant)