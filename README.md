# Enchanting Kata

> Credits for the Enchanting Kata go to [Giulio Perrone](https://www.codurance.com/katas/arithmetics-0). This repository is merely an alternative way of describing the same exercise.

## Background

For this coding exercise, imagine you are developing code for a Role Playing Game. Think Dungeons and Dragons, or something similarly fantastical.

The hero of this game is called Durance. Durance has a weapon, a famous sword called the "Dagger of the Nooblet". And, Durance has a magic book, which contains spells with which he can enchant his weapon.

## Exercise 1

The first exercise is to write code that allows Durance to describe his weapon. An example response from this code might look like this:

```
Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
```

## Exercise 2

For the second exercise, you should implement code that allows Durance to enchant his weapon. An enchanted weapon gains an additional attribute, but that's not all: with the enchantment, the weapon's name gets a prefix that reflects is newly gained enhancements.

For example, when the "Fire" enchantment is applied, the weapon's description will look like this:

```
Inferno Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
+5 fire damage
```

### Rules

When Durance enchants his weapon, there are 5 possible enchantments that might be applied:

| Enchantment | Prefix  | Attribute      |
| ----------- | ------- | -------------- |
| Ice         | Icy     | +5 ice damage  |
| Fire        | Inferno | +5 fire damage |
| Lifesteal   | Vampire | +5 lifesteal   |
| Agility     | Quick   | +5 agility     |
| Strength    | Angry   | +5 strength    |

Magic is tricky business. Using his magic book, Durance can enchant his weapon, but he cannot choose _which_ enchantment he gets. The following rules apply:

- Enchantment selection is randomized, Durance does not know which enchantment he'll get.
- Only 1 enchantment can be active at a time.
- You cannot get the enchantment that you already have, they are always different.
- There is a 1/10 probability of losing the current enchantment.
- For the simple version of this exercise, the enchantment attribute has no effect on the base stats of the weapon. They are considered extra stats.
- Enchanted weapons have the prefix of the enchantment on them.

## Example

Durance starts out without any enchantments.

```
Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
```

After enchanting it, Durance got the Fire enchantment!

```
Inferno Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
+5 fire damage
```

Not satisfied, he enchanted it again and this time he got the Agility enchantment.

```
Quick Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
+5 agility
```

He felt confident thinking that he could get something better and tried again, sadly, he lost his enchantment!

```
Dagger of the Nooblet
5 - 10 attack damage
1.2 attack speed
```

## Starting point (optional)

For an (optional) starting point, see the [Durance.cs](Durance.cs) class for C#, or [Durance.java](Durance.java) for Java.

## Harder version

Durance can now carry more weapons and each one can have up to 3 unique enchantments. He is also worried about dealing the most damage possible, so DPS (Damage per Second) should be displayed as well.

### Damage per Second (DPS)

We take the **agility** attribute into account, converting it to an attack speed increase equal to: 

`Increase in Attack Speed = Attack Speed + Agility Points / 10`

DPS is calculated as:

`((Min Damage + Max Damage) / 2) / Attack Speed`

### Rules

- Previous rules apply. 
- In the case of losing an enchantment, only the last enchantment should be removed.