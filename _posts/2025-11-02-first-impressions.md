---
layout: post
title: "First impressions"
date: 2025-11-02 14:00:00 +0100
categories: linguistics syntax
---

## How I started my journey

Coming from an engineering and business background, I'm approaching linguistics as a complete outsider with fresh eyes and hopefully an intellectual rigor borrowed from other domains.

So, I recently started my journey in theoretical linguistics with syntax, the main book I use is "Syntax: a generative introduction (fourth edition)" by Andrew Carnie. I started with this book for two reasons:

1. Syntax seems to be a good entry point into the field as it provides the tools to analyse the structure of language (e.g. trees)
2. Carnie's book came as a frequently recommended textbook

I've just finished chapter 4, here are the first chapters (as a reminder for you, reader):

1. Generative Grammar
2. Parts of Speech
3. Constituency, Trees, and Rules
4. Structural Relations

As I read, I go through almost all General Problem Sets in the book and some of the Challenge Problem Sets (I try to read them all at least).

In parallel to Carnie, I started 2 weeks ago to follow the [MIT course 24.900 Introduction to linguistics](https://ocw.mit.edu/courses/24-900-introduction-to-linguistics-spring-2022/) by Prof. Norvin W. Richards and I must say I like it very much (I'm about to start lecture 13). Each lecture lasts about 1 hr and the videos (except for lecture 7) are available together with the slides. Prof. Richards has a very accessible learning style. These lectures cover the full spectrum of linguistics: morphology, phonetics, phonology, syntax, semantics and more. Richards' lectures on phonology and phonetics helped me understand why syntactical representations and phonological forms need to interface. A great introduction before engaging with Carnie's depth on syntax.

Here are the key topics I've discovered and that are absolutely essential if you want to dive into theoretical linguistics.

## Theoretical foundations

Before diving in, we need to ask the foundational question: what is language in the generative framework?

Chomsky distinguishes between _i-language_ (internal language) and _e-language_ (external language). Internal language is about the mental grammar, the cognitive system in the brain that generates linguistic expression. External language refers to the observable linguistic behaviour.

This distinction is methodologically crucial. Generative grammar studies **i-language** and not **e-language**. Our goal is to model the system that makes language possible. That particularly resonates with me as I started my career in the computational modelling field (applied to chemical engineering) and the parallel really speaks to me. The distinction between _i-language_ and _e-language_ leads to another key distinction that we'll review below: competence vs. performance.

## Generative grammar?

When I started I didn't know much about grammar beyond the rules I learned at school (and by the way, this is called **prescriptive** grammar and is not of much interest for professional linguists who spend their time studying **descriptive** grammar, i.e. how people are actually using the language and not much about how they should use the language). This distinction is fundamental, children acquire language without explicit rules or instructions, which suggests they're able to extract patterns from the input they get, and that's precisely what generative grammar aims at modelling.

So, what is **generative** grammar?

It's the set of rules that we (mostly unconsciously) use to **generate** sentences as we speak, write or sign (for sign languages are also full fledged languages). The role of syntacticians (and semanticists and other professional linguists) is to uncover those rules to make them explicit and it's no easy feat.
Generative grammar is all about algorithms, some kind of a formal system that can **generate** all (and only) the grammatical sentences of a language.

This makes generative grammar a cognitive science, it's not just about cataloguing sentences or prescriptive rules, the goal is to theorise about the computational mechanisms that take place in the user's brains (the **i-language**).

## Competence and performance

The other concepts that I discovered is the difference between **competence** and **performance**:

- **competence**: what we know about our language
- **performance**: refers to the actual language produced and heard with all its quirks

Let me borrow an example from Carnie (Chapter 1, page 13), consider the sentence:

\#"Cotton shirts are made from comes from India"

What is your first reaction? Is it grammatical? What's the meaning?

At first, as I had, you probably have difficulty to understand the meaning (performance) but once you understand, for example by adding "that" at the right place and the sentence becomes #"Cotton that shirts are made from comes from India" you fully understand and realise that the sentence is perfectly grammatical.

Linguists use a special notation to mark sentences:

- **\*** (asterisk): ungrammatical
- **#** (hash): grammatical but semantically anomalous
- **?** (question mark): marginally acceptable

This difference means that we need to study the underlying system that generates grammatical sentences and we cannot stay at the surface level (i.e. the performance). But how do we access competence when we have only access to performance? The challenge lies here, and grammaticality judgments will reveal as a powerful tool. This competence/performance distinction shapes how we study grammaticality, we're interested by how people actually produce the language they use, what mental grammar they use.
Grammaticality judgments become the primary data, but there remains a methodological puzzle: these judgments themselves are products of the system we're trying to model, using grammar to study grammar. This must be handled very carefully through special protocols and methods.
That leads us to the next key concept.

## Grammaticality

Much of syntactic work revolves around the grammaticality of sentences, and this is absolutely fascinating how intuitively we know if a sentence is grammatical or not (and this is even more impressing when studies are made with young children). Let's have a look at Noam Chomsky's famous example sentence "Colorless green ideas sleep furiously", I was immediately able to recognise this sentence as grammatical (proper word order, proper agreement), but my semantic processing system can't interpret properly "colorless green" or "sleep furiously".

But how can we really be sure that the sentence is grammatical? What are the tools we can use? That's for the next post where we'll see tools like constituency tests.

## Conclusion

The concepts we've covered today: **i-language**, **e-language**, **competence**, **performance**, **grammaticality** are not just preliminaries, they are foundational concepts, and tools we will explore in future posts (trees, movement, binding).

In the next post, we'll cover constituency tests, syntactic trees, structural relations.
