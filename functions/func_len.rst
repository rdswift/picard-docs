.. MusicBrainz Picard Documentation Project

$len
====

| Usage: **$len(text)**
| Category: text

**Description:**

Returns the number of characters in ``text``.


**Example:**

The following statements will return the values indicated::

    $set(foo,)
    $len(%foo%)    ==>  "0"

    $set(foo,ABC)
    $len(%foo%)    ==>  "3"

    $len()         ==>  "0"
    $len(ABC)      ==>  "3"
