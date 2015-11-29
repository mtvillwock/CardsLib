# CardsLib

[![Gem Version](https://badge.fury.io/rb/cards_lib.svg)](http://badge.fury.io/rb/cards_lib)[![Build Status](https://travis-ci.org/danielpclark/CardsLib.svg?branch=master)](https://travis-ci.org/danielpclark/CardsLib)[![Code Climate](https://codeclimate.com/github/danielpclark/CardsLib/badges/gpa.svg)](https://codeclimate.com/github/danielpclark/CardsLib)[![Test Coverage](https://codeclimate.com/github/danielpclark/CardsLib/badges/coverage.svg)](https://codeclimate.com/github/danielpclark/CardsLib/coverage)

I apply best practices in designing this gem and each feature has had
a LOT of thought put into it. Just look at how the Deck works. It's
designed with an immutable set of cards to draw from and to return
cards to. You can even seed it to write robust tests and get the same
results time after time. Card evaluation is written in a functional
way that allows, and is optimized for, lazy evaluation. The set
verification is as simple as handing it some cards and the names of
the rules to apply.

I'm willing to bet you that there is no other Ruby card game library
out there as easy to use, as well thought out, and as simple to
understand as mine. Come on, I dare you to use it and review it! ;-)


##Install

```
gem install 'cards_lib'
```
Requires Ruby 2 or greater.

##Usage

Create a Card with Card.new(face)

```ruby
CardsLib::Card.new("As")
```

Use a Macro to create a list of Card instances from card faces.

```ruby
CardsLib::Cards["Ah","2h","3h","4h","5h"]
```

Create a Deck with Deck.new(cards)
A default deck is generated if no parameters are given.

```ruby
CardsLib::Deck.new
```

Pick what rules you'd like to use in determining a set of cards.

```ruby
# BOOLEAN RESULT
CardsLib::IsSet.verify(
  card_instances_array,
  rules = [:unique, :ordered, :paired, :suited],
  specifications = {min: 3, max: Float::INFINITY}
)
```

##Goodies

* **lib/cards_lib/is_set.rb** is a golden tool in card hand verification.

* In **lib/cards_lib/standard.rb** there are some basic deck templates.

* In **lib/cards_lib/standard/rules/poker.rb** there are some working Poker hand verification methods.

##License

The MIT License (MIT)

Copyright (c) 2015 by Daniel P. Clark

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.
