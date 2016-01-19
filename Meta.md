# Meta - A card game

#### Etienne Ott

Meta is a card game based on the concept of stacks, a "Last In, First Out" data
structure. It is heavily influenced by trading card games and highly self-referential in
both its rules and in its contents. Players each possess a memory, or library, of cards,
from which they draw cards into their hands. Cards are played from the hand to a stack
and then are "executed". The winning condition is to be last player active, although
there are cards that can even change the rules of the game during play.

## Stacks

Stacks are, just like regular stacks of paper, a way of arranging elements for later use.
Elements can only be retrieved from the top of the stack. While the top does not
necessarily needs to be the uppermost element on the table, it most easily to imagine it
so.
How the stack is represented on the table is up to the players. One way is to place the
cards on top of each other, but with only the top half intersecting and the bottom half
facing the player who played the card. This maintains the stack structure, while making
it easy to tell which cards belongs to whom.

All players have access to the so called main stack, which serves the purpose of bringing
a card into play. Additionately each player has an endless amount of deactivated trigger
stacks. How these are activated is explained later on. A deactivated trigger stack is
considered nonexisting and can't be targeted.

Every stack has a meta stack associated with it, including meta stacks themselves. That
means each stack is part of a stack tower. Only Meta cards can be played on stacks
other than the base one. 

The graveyard is a stack associated with a player and contains discarded cards. It can be
targeted, but cards can't be played on it. Cards that do target it, are played on the
main stack.

## Players

Each player starts with 15 life points and cannot have more than 25 or less than -15 life
points at any time. A D20<sup>1</sup> is a good way of tracking life points. When a player has 0 or
less life points, they are disabled. Disabled players cannot play cards and discard their
hand the moment they reach 0 life points. They do not draw cards during the drawing stage,
but are still considered in game. All trigger stacks and cards in play are still active
and apply accordingly.

All effects targeting "all players" also effect disabled players, but effects cannot
target specific disabled players. If a player somehow gains more than 0 life points
again, they are back in play.

If a player should draw cards, but has no more cards in memory, they get disabled. If
there are less cards than they are supposed to draw, they draw the remaining cards instead
and lose one life point for every two cards not drawn. A player disabled for lack of
memory can be brought back into play, if effects put cards back into the memory.

If all players, that have not been disabled yet, would be disabled at the same time, for
example during the drawing stage, all players already disabled are permanently removed
from the game. The other players then shuffle their graveyard into their memory and
continue. To be the only player not disabled is an instant winning condition.

<sup>1</sup> This abbrevation means "Die with 20 sides". A regular
cubic die is called D6.

## Cards

A card, regardless of its actual design is composed of several necessary elements:

* Title: The title of the card. This is not meant to be a unique identifier, but to
avoid confusion it should be unique anyway.
* ID: An identifier to reference cards across different editions of Meta. The ID is
given when the card is first created. A suffix is appendend and increased every time the
card changes. These changes can be so thorough, that the most recent version of the card
is no longer comparable to the first version. It is still encouraged to rather change a
card than to introduce a new, but similar card. An outdated version can always be
reintroduced as a new card, but duplicates can be difficult to remove. 
* Type: Determines the behaviour of the card. Types are Event, Meta and Trigger.
Event and Meta describe actions, while Trigger represents conditions.
* Uniqueness: Limits how often this card can occur in a legal deck. This refers to
the card's ID across all versions. If the uniqueness is a number, it is the maximum count
of that card in a deck. If a non-standard deck size is used, these numbers may be
altered. A uniqueness of "\*" behaves like a uniqueness of "1". However, a deck may
contain at most two cards of uniqueness "\*".
* Description: Describes what this card does when it is executed or, for triggers,
when this card is executed. The interpretation of the description should be consistent
across games. Is it not always possible to guarantee an unambigous description. When a
player plays a card, they should be aware of what this card does and should be able to
explain its behaviour. At best, the player states the interpretation at the time of play
even before the card is executed.

When a card refers to a specific other card or some other game element, that is not
directly determined on the card, the player must announce the target at the time of play.
This target does not have to be bound to a specific card, but must be unambigous
nonetheless. It is for example possible to announce "the card below this one on the
stack" as a target. If the card referenced by this target changes during the executing
stage, the target is still valid and now targets the new card. It is even possible to
target something that does not exist yet. If a card's target is no longer valid during
execution, the card is discarded without effect. The same is true if the instructions on
the card no longer make sense.

If the instructions on a card are in conflict with the rules presented in the handbook,
the card automatically wins. This could also be caused by different versions of
the handbook and the cards. Cards should therefore be designed with a specific version of
the rules in mind.


### Card Types

#### Event

An Event card describes a set of actions with a goal. For example, a card with the set
goal of "All players gain 2 life points" would need the implicit actions "Identify all
players" and "Increase the life point counter on each identified player by 2". The
instructions are human-readable and "All players gain 2 life points" are acceptable
instructions in this case. It is hardly possible to cover every angle of ambiguity. When
interpreting the instructions, the players should stick to the simplest interpretation
that makes sense within the ruleset.

Event cards can only be played on the main stack or a trigger stack.

#### Meta

Meta cards are similar to Event cards, but can also address the stack itself. When
played, they are pushed on the meta stack of the highest stack they address. A Meta card
that targets the main stack is pushed on the meta stack. A Meta card that targets the
meta stack is pushed on the meta-meta stack and so on.

#### Trigger

Trigger cards are conditions, that serve the purpose of activating a trigger stack. Only
the player at turn can play Trigger cards and these can only be used to activate trigger
stacks or be the target for effects that are said to target "any card". When activating
a trigger stack, the player lays the card on backside up on its place and announces the
card's target, if it needs one, although they do not have to say what the
condition on the card is. This serves the purpose of laying traps, without allowing for
cheating by secretly switching the target during play.

When the card is triggered the trigger stack and all its meta stacks
are executed in the same manner as the main stack. The instructions should make clear if
the card is triggered after the condition has happened or before. The trigger card itself
is discarded before execution.

### Decks and Collections

All cards in possession or in access of a player form their collection. A deck is a
subset of a collection, that is used for the game. A rule-conforming deck consists of 60
cards and no card occurs more often than its uniqueness.

A player may use any representation of any officially released card. They can even write
the card on a piece of paper on the spot, if they can show that this card is indeed part
of the version of Meta they are playing. It is highly discouraged to prevent players from
using any card. Once a card is released, it should be accessible by anyone, regardless of
the representation used.

## Gameplay

### Before the game

Players should shuffle their memory thoroughly and reset all counters and clocks that are
tied to gameplay, unless these counters are specifically designed to persist between
games. Then the turn order is determined by dice throw. Each player throws a
D20. The turn order is the same as the dice throws in descending order. If several 
players have the same number, they continue to make comparing dice throws, until they
have established a sub-order. This sub-order is then integrated into the main turn order
at the corresponding number.

Players then each draw nine cards from their memory and start the first turn.

###  Turns

Each turn is divided into four stages. The player at turn has priority, which means,
that they determine when each stage starts and ends.

#### Drawing stage

At the beginning of the drawing every event and trigger that is said to happen "at the
beginning of a turn" is executed. Players then each draw the top three cards from their
memory into their hand. The player at turn can put card onto this trigger stacks or
activate new trigger stacks. Other player can play no card at this stage. The first card
played onto the main stack marks the end of the drawing stage. If the player at turn
wishes to play no card, they can say "Play!" to mark the end of the stage.

#### Pushing stage

In the pushing stage each player can play cards on the main stack at any time. If the
order of two cards played is not clear, the players are encouraged to work out the
correct order. The game host is allowed to resolve conflicts that delay the game for too
long. Note, that this stage does not begin before the player at turn has determined it
so. Players are also encouraged to give the other players time to examine the cards they
have played.

When all players have played the cards they want to play and all questions regarding the
effects of cards are cleared, the stages ends.

#### Executing Stage

In this stage no cards may be played, unless specified on the cards. Beginning with the
highest meta stack, the cards are removed from the top of
the stack and the instructions on the cards are executed. As discussed in the Cards
section, the player who played a card, must explain as clearly as possible what actions
the instructions warrant. After the instructions on a card are done, the card is put on
its owners graveyard and the next card is taken.

Players with activated trigger stacks should take care to recognize when a trigger
condition is met, as backtracing to when a trigger should have been activated is not
always possible. (See section Trigger)

The stage ends when all cards have been executed.

##### Paradoxes

The self-referential nature of Meta can on occasion result in paradoxes, that have not
been foreseen by the game developers. If during the executing stage a paradox occurs, the
players should discuss how to resolve the paradox. A common method is to remove all cards
involved in this and put them on the graveyard or to flip a coin as to which effect wins.

#### Discarding stage

All players with more than twelve cards in their hand discard any cards from their hand
until twelve are left. This is supposed to happen simultaniously across all players. If
multiple trigger stacks would be triggered during this process, the turn order is applied.

After this, all events and triggers that are said to be executed "at the end of a turn"
are executed.