---
layout: post
title: "The geometry of syntax: Why tree structure matters"
date: 2025-11-10 16:00
categories: syntax
---

## Introduction

You've probably already met some syntax trees, but why do we draw trees when we could just use brackets, highlighting, underlining, or other markers to identify components and structure (with the ultimate goal to understand the meaning of the utterance)?

Today, we'll look at the insights we could get from a syntax tree (we will not learn to draw trees though). The information we get from a syntax tree is crucial for the analysis of a sentence and also later to analyse and understand its meaning. The relations we'll look at today are: dominance, precedence and c-command.

## Beyond Linear Order

### Why word order isn't enough

Here is an interesting example (despite looking basic at first sight): **I saw the man with the telescope**

Who had the telescope? The seer or the seen?

English, like many natural languages, is prone to structural ambiguities sometimes. What syntax trees allow us to do is to actually disambiguate the sentence and define clearly who's doing what to whom.

Here is the syntax tree for this sentence with a warning though: these diagrams follow the framework from chapter 3 of (Carnie 2021b), i.e. before the introduction to X-bar theory.

### The tree structure insight

  <div style="display: flex; justify-content: space-around; align-items: flex-end;">
    <div style="text-align: center;">
      <img src="{{ site.baseurl }}/assets/images/I-saw-the-man-with-the-telescope.png" alt="Syntax tree" width="400">
      <br><br><i>I used a telescope to see a man</i>
    </div>
    <div style="text-align: center;">
      <img src="{{ site.baseurl }}/assets/images/I-saw-the-man-with-the-telescope-2.png" alt="Syntax tree" width="400">
      <br><br><i>I saw a man who had a telescope</i>
    </div>
  </div>

  <div style="text-align: center;">
    <br><i>Images drawn by <a href="https://yohasebe.com/rsyntaxtree" target="_blank">Rsyntaxtree</a> by Yochiro Hasebe</i><br><br>
  </div>

What do these trees tell us about the syntax of this sentence?

It tells us that syntax is not primarily about highlighting components of a sentence in a linear way. Syntax is about making sense of a stream of words, it's about visualizing the hierarchical structure of the sentence so we can draw conclusions about the structural relations of the different components.

Here we have an example of an ambiguous sentence which has two distinct trees, each representing one possible interpretation.

## The Basic Structural Relations

In this part, we'll introduce some key definitions of concepts used to analyze trees: dominance, precedence and c-command. In (Carnie 2021b) the author gives more definitions not reproduced here.

### Dominance

Intuitively, dominance is a relation between two nodes in a tree, where you could draw a downward line between node A and node B, you then say that node A **dominates** node B.

Let's look at an example for a very simple tree:

```text
      A
    /   \
   B     C
        / \
       D   E
```

In this tree, there are several dominance relations:

- A dominates B, C, D and E
- B dominates no node
- C dominates D and E
- D dominates no node
- E dominates no node

Also note some other important definitions from this tree:

- A is the root node
- B, D and E are terminal nodes (they dominate no other node)
- A and C are both non-terminal nodes

### Precedence

Looking at the same simple tree, we can also define **precedence**.

Intuitively, we can think about precedence as the fact that one word appears before another one in a sentence; however, when we use trees, the definition is much more precise.

Before we define precedence, let's define **sister-precedence**:

- A sister-precedes B, if and only if both are dominated by the same node and A appears before B (from left to right)

Now, we can define **precedence** using this definition:

- Node A precedes node B if and only if neither A dominates B, nor B dominates A, and A (or some node dominating A) sister-precedes B (or some node dominating B)

In our sample tree:

- B sister-precedes and precedes C
- B precedes D
- B precedes E
- D sister-precedes and precedes E

**Note**: in syntax, it is customary to use feminine kinship terms mother, daughter and sister to mention relations between nodes.

### C-command (the crucial relation)

Now that we've looked at dominance and precedence definitions, we can move to probably the most important definition: c-command. C-command is neither pure dominance nor precedence. But if you're like me, as long as you've digested the previous definitions, c-command is relatively easy.

C-command is probably the most crucial relation of syntax and it's absolutely essential to grasp it fully. I highly recommend working through the exercises in Carnie's Syntax Workbook (Carnie 2021a) which includes answer keys.

Definition: a node c-commands its sisters and all nodes dominated by its sisters. A more formal, rigorously equivalent definition (Carnie, 2021b) is: node A c-commands node B if every node dominating A also dominates B and neither A nor B dominates the other, and A is different than B.

```text
      A
     /  \
    B    C
        /  \
       D     E
           /   \
          F     G
         /  \   | \
        H    I  J  K
            /  \
           L    M
```

In this sample tree:

- B c-commands all nodes, except A and B itself
- D c-commands all nodes, except A, B and C and D itself
- F c-commands G, J, K
- G c-commands F, H, I, L, M
- ...

C-command will allow us to define binding which is extremely important in understanding sentence structure.

## C-command in Action

### Binding phenomena

One of the key uses of c-command is in its ability to predict which pronouns and anaphors can refer to which nouns in a sentence. This does not seem like much but for languages like English and most romance languages (to cite a few examples) which make heavy use of pronouns this is essential to determine with precision the structure of a sentence.

This is what **binding** is about. Before we move on, we will define a few useful concepts:

- pronoun: an NP (Noun Phrase) that can (optionally) get its meaning from another word in the sentence
- anaphor: an NP that obligatorily gets its meaning from another NP in the sentence
- R-expression: an NP that gets its meaning by referring to an entity in the world (person, place, object, etc.)

So, what is **binding**?

Binding is the relation between two NPs in the sentence, where one is the **antecedent** (the NP referred to) and the other is the pronoun or anaphor that refer to it. When two NPs refer to the same entity, we co-index them by marking them with the same subscript number. Binding is a special kind of co-indexation where the antecedent c-commands the pronoun or anaphor.

But there are some principles to be respected otherwise the sentence will be ungrammatical:

- **Principle A**: an anaphor must be bound in its binding domain (i.e. the smallest clause containing it)
- **Principle B**: a pronoun must be free in its binding domain
- **Principle C**: an R-expression must be free

Let's see how each principle works (with examples):

#### Principle A - Anaphors must be locally bound

- "John₁ hurt himself₁ on the foot"
- Here, "John" (the antecedent, an R-expression) c-commands and binds "himself" (an anaphor, the co-index) within the same clause. This satisfies Principle A.

- \* "John₁ said Mary hurt himself₁"
- Here, "himself" is not bound within its local clause "Mary hurt himself". The antecedent "John" is too far away, this violates Principle A.

#### Principle B - Pronouns must be locally free

- \* "John₁ likes him₁"
- Here, the pronoun "him" is bound by "John" within the same clause. This violates Principle B (note that in this case, the sentence can have a different meaning where "him" refers to someone else, but not "John").

- "John₁ said Mary likes him₁"
- Here "him" can refer to John because they are in different clauses. The pronoun "him" is free in its local domain. This satisfies Principle B.

#### Principle C - R-expressions must always be free

- \* "He₁ hurt John₁"
- Here, the R-expression "John" is c-commanded by "he", creating a binding, this violates Principle C.

- "John₁ said he₁ was tired"
- Here, "John" c-commands "he" (not the other way around), so the R-expression "John" is free (not bound by anything). The pronoun "he" can
  refer back to "John" without violating any principle.

### Why this is surprising and beautiful

What surprised me is how an abstract geometric relation in a tree can predict concrete grammaticality judgments; this was an eye-opener for me. That reminded me of the competence/performance theme we saw in a previous post: how an abstract model (remember the i-language?) can really explain a concrete fact like our ability to understand (or not) language (the e-language).

## Making Sense of the Abstraction

I didn't really know what to expect when I embarked on this journey. I had some misconceptions about syntax being all about how words were ordered in a sentence, now I realize that it's not about word ordering but really about hierarchical structure. I had the impression that syntax trees were very abstract, but now I understand they are really helpful in understanding concrete facts about language. We are actually speaking in trees!

These trees reveal the underlying structure of the sentences we speak every day and their meaning. It means that language is not just the sequence of words we speak many times a day, language is much more structured than I initially thought.

## Conclusion

At first, tree structure seems like a new kind of notation, but it's much deeper than this, it encodes the deeper structure of language and shows the geometric space where syntax really happens (even though syntax could be seen as worthless without semantics which is the ultimate goal).

The next step in our journey is X-bar theory which pushed one step further by formalizing even more the tree structure with mandatory binary trees and even more systematic rules. I've always had the intuition that mathematics are the background language of nature and it's becoming more and more obvious to me, even in language!

## References and Further Reading

Carnie, Andrew (2021a) _The Syntax Workbook A Companion to Carnie's Syntax_, second edition, Wiley-Blackwell  
Carnie, Andrew (2021b) _Syntax A Generative Introduction_, fourth edition. Wiley-Blackwell
