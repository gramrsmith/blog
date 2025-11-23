---
layout: post
title: "Composing Meaning: A First Look at Formal Semantics"
date: 2025-11-23 15:00
categories: linguistics semantics
---

## Why Formal Semantics?

I recently discovered formal semantics in my beginner's journey in theoretical linguistics, and I must admit I didn't expect this level of formalism in the field of linguistics. I stumbled upon logic, lambda calculus (which I knew a bit about because of my background in computer science), what an exciting topic!

Just to give you a first look at formal semantics, let's consider a very simple sentence: "every student sleeps".

How different does it feel compared to "a student sleeps"? It looks like something is happening, especially because of "every" which is called a _quantifier_ (more on that in future posts). "every student sleeps" means that **all** students must be sleeping for the sentence to be true. But "a student sleeps" only requires that **at least one** student is sleeping.
This highlights the difference between universal ("every") and existential ("a") quantification, and formal semantics captures this difference in a rigorous and formal way.

## The Core Idea: Compositionality

The first and foremost concept of formal semantics is **composition**, which means that the meaning of the whole is a function of the meaning of the parts (_function_ here is to be understood in its mathematical meaning). This principle was formulated by the German mathematician and logician Gottlob Frege, whose name is well known to all semanticists.

What's the use of the compositionality principle?

The main interest of this principle is to allow us to understand sentences we've
never heard before, compositionality will allow us to construct meaning as we hear or read a new sentence, by using composition of simpler fragments up to a complex sentence.

## The Type System in 60 Seconds

When we talk about functions, it's absolutely essential to define functions of _what_? And that's where types are to become necessary. In traditional math, we talk of functions of integers or reals, in semantics the basic types are entities or truth values:

- **Type e**: entities (John, Mary, that specific student)
- **Type t**: truth values (sentences that are true or false)
- **Type ⟨e,t⟩**: properties or predicates are functions that take an entity and return a truth value.

Let's look at an example: _sleep_ is a predicate that takes an entity (type e) and returns _true_ (type t) if and only if the entity sleeps

A quick note on the notation used: ⟨α,β⟩ means "function from type α to type β", below, we'll see types like ⟨⟨e,t⟩,t⟩ which may look weird at first, but if you take it step by step, you see this is a function, that takes a function from entity to truth value, i.e. ⟨e,t⟩, and returns a truth value (type t).

We'll make extensive use of this notation as we move on.

## One Complete Example: "Every Student Sleeps"

### The Challenge

"Every student" isn't type e (not a single entity). It can't directly combine with "sleeps" (type ⟨e,t⟩). So how does this work?

### The Solution: Generalized Quantifiers

"Every student" is type ⟨⟨e,t⟩,t⟩—a function that takes a property and returns true/false.

### Step-by-Step Derivation

**Lambda Notation Primer:**

We now need to introduce another notation extensively used in formal semantics that comes from lambda calculus. For a very good introduction to lambda calculus, see Rojas (2015).

The basic lambda expression: λx.student(x) means "the function that takes x and returns whether x is a student". The part before the dot, defines the variables, the part after the dot is the body of the function. In this case, x is the variable and the body of the function is student(x) which is true if and only if (frequently abbreviated to 'iff') x is a student.

Let's now derive (i.e. take each component of our sentence and replace it with the corresponding lambda expression and, using the compositionality principle, define the meaning of the sentence).

**Lexical entries:**

```text
[[every]] = λQ.λP. ∀x[Q(x) → P(x)]  — type ⟨⟨e,t⟩, ⟨⟨e,t⟩,t⟩⟩
[[student]] = λx.student(x)  — type ⟨e,t⟩
[[sleeps]] = λy.sleep(y)     — type ⟨e,t⟩
```

**Tree:**

```text
       TP
    /      \
   NP       VP
  /   \      |
 D     N'    V'
every  |     |
       N     V
    student  sleeps
```

**Composition:**

Combine "every" + "student":

```text
[[every]]([[student]]) = [λQ.λP. ∀x[Q(x) → P(x)]](λx.student(x))
                        = λP. ∀x[student(x) → P(x)]
```

- Notation reminder: double brackets like [[student]] mean "the meaning of student"
- Function application: \[\[every\]\]([[student]]) means that we apply the function **every** to the argument **student**
  - [[every]] = λQ.λP. ∀x[Q(x) → P(x)] — a function waiting for two arguments
  - First, we give it Q = λx.student(x)
  - After this application, we get λP. ∀x[student(x) → P(x)] — still waiting for P
- The substitution: When we apply λQ.(...) to λx.student(x), every occurrence of Q in the body gets replaced by student(x):
  - Before: ∀x[Q(x) → P(x)]
  - After: ∀x[student(x) → P(x)]
- What it means: We now have "a function that takes a property P and returns true iff every student has property P"

Then, we combine "every student" + "sleeps":

```text
[[every student sleeps]] = ∀x[student(x) → sleep(x)]
```

**Truth conditions:** true iff for all x, if x is a student, then x sleeps.

## What This Achieves

We've just scratched the surface of compositionality's power, you'll see it often in semantics, it allows for perfect precision when analysing a sentence, and also to cover infinite sentences with a finite set of rules.

I knew about lambda calculus because of my background, but I never thought that it could be useful to understand the meaning of sentences. I think lambda calculus is probably the most elegant and powerful concept in mathematics, its application is clear in computing and now in semantics. I didn't expect that!

## Conclusion

With this short post, we see how formal semantics helps treating meaning as a computable object and not just something we get from intuition. But we've only looked at a very simple sentence, it's not easy to say how things will unfold with more complex sentences with two quantifiers like "someone loves everyone". This will probably be for a future post.

## References and further reading

- Heim & Kratzer (1998) _Semantics in Generative Grammar_, Wiley Blackwell
- Portner (2005) _What is Meaning? Fundamentals of Formal Semantics_, Wiley Blackwell
- Rojas, Raul. “A Tutorial Introduction to the Lambda Calculus.” arXiv:1503.09060. Preprint, arXiv, March 28, 2015. <https://doi.org/10.48550/arXiv.1503.09060>.
