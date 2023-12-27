---
title: Palindromes, Tarot Cards, and Logo Design
author: the-wandmaker
date: 2023-12-27 12:27:00 +0100
categories: [Articles, Symbolism]
tags: [magic, art, symbolism, history]
pin: false
math: false
mermaid: false
image:
  path: /commons/2023-12-sorcerer.png
  lqip: data:image/webp;base64,UklGRpoAAABXRUJQVlA4WAoAAAAQAAAADwAABwAAQUxQSDIAAAARL0AmbZurmr57yyIiqE8oiG0bejIYEQTgqiDA9vqnsUSI6H+oAERp2HZ65qP/VIAWAFZQOCBCAAAA8AEAnQEqEAAIAAVAfCWkAALp8sF8rgRgAP7o9FDvMCkMde9PK7euH5M1m6VWoDXf2FkP3BqV0ZYbO6NA/VFIAAAA
  alt: An AI generated image of a sorcerer designing a business logo
---

I've been experimenting with some different designs for a logo that I'd like to eventually use for this blog, as well as other work I create. While iterating through various designs I came to the conclusion that the details that were most interesting and important to me were the history of logos, and the symbolic immutability of certain words and images.

## Guilds and Trades

The origin of companies using logos, icons, and monograms to represent their brand isn't purely for marketing purposes. At various points in history, artists, craftsmen, and guilds of people working within a trade found it necessary to mark their work to signify that it was a valid product they had produced, and to defend that product against competitors who might mimic their work. We see this tradition carried on today as publishers place their monogram along the spines of books, corporations place their logo long the footer of branded materials, even modern day blacksmiths still stamp touch-marks into the items they make.

I was inspired by this idea that a logo was not just a static part of the packaging, but an active tool used to defend a product. But what could a logo possibly be equipped with to assist it in its protective efforts? In nature, organisms often employ the use of thorns, spines, antlers, or horns for defensive purposes. At the same time, these same features can also have decorative purposes for these animals, serving to draw attention. This detail also seems nicely in line with the marketing-oriented aspects of branding.

Drawing inspiration from nature is one of my preferred ways to approach concepts and designs. Somewhat related, is a stylistic engineering principle called _BEAM_, an acronym which stands for Biology, Electronics, Aesthetics, and Mechanics. This principal is typically applied to robots, which can be easily recognized by their simplicity, exposed soldered components, and general bug-like appearance. Having constructed a number of these small robots in the past, I can say that I am significantly a fan of this concept.

## Symmetry and Palindromes

The Sator Square is a well-known acrostic palindrome and [word square](https://en.wikipedia.org/wiki/Word_square) that is first recorded to have existed in Pompeii prior to 62 AD. A breadth of theories exist, speculating its meaning and significance. These range from it originating as a puzzle game, to being a religious amulet with various magical properties. Like all things shrouded in mystery and ambiguity, the Sator Square immediately piques my interest.

_As a brief aside, when we compute the sum of the letters of the Sator Square (such that A = 1, B = 2, etc.), the sum of the ordinal values of each characters is coincidentally 303, a palindromic number._

```python
# The Sator Square represented as a tuple of strings
SATOR_SQUARE = (
    'SATOR',
    'AREPO',
    'TENET',
    'OPERA',
    'ROTAS',
)

def latin_ord(character):
    """
    Function the same as the Python builtin `ord`, function except exclude the letters
    'J' and 'U' by shifting numeric values after them by -1. This is because the Latin
    alphabet excludes the letters J and U.
    *A, B, C, D, E, F, G, H, I, [J], K, L, M, N, O, P, Q, R, S, T, [U], V, W, X, Y, Z)
    """
    J = ord('J')
    U = ord('U')

    order = ord(character)

    if order >= J and order < U:
        order = order - 1
    elif order >= U:
        order = order - 2

    return order

'''
18,01,19,14,17  == 69
01,17,05,15,14  == 52
19,05,13,05,19  == 61
14,15,05,17,01  == 52
17,14,19,01,18  == 69
----------------------
                == 303
'''
total = sum([
    sum(latin_ord(letter) - 64 for letter in word) for word in SATOR_SQUARE
])


print('Sum:', total)
```

Symmetry, or the lack thereof, can have a great deal of symbolic meaning. Palindromes, words or phrases which read the same way both forward and backward, quite literally cannot have their meaning reversed.

When we examine practices in forms of cartomancy such as tarot reading, it is often explained that a card drawn from the deck upside down has its meaning inverted. As a brief example, _The Chariot_ might be seen to symbolize a journey, but with the card inverted the symbol could represent immobility or staying in one place.

Modern divination practices involving runes also tend to follow similar principles to cartomancy when it comes to interpreting symbols. An upside down rune thus has the opposite meaning. Interestingly however, some runes are vertically symmetrical, which might be interpreted as them not having an opposite meaning.

In terms of my own logo, I wanted to draw upon this concept and idea that symmetry allows a symbol to preserve its meaning, that it represents something which is intrinsically immutable. In terms of a logo being used for a business, this relates nicely to having good and unwavering principles: like supporting artists, small businesses, using sustainable and well-sourced materials.

***

_Final thoughts: It shouldn't be disregarded that asymmetry is also a valuable tool. Something I hope to explore more in future designs is intentional ways that symbols might change their meaning when inverted or mirrored in different ways. Exploring this relationship between symbolic interpretation and physical representation can be fascinating and there are likely some incredible designs out there just waiting to be created._
