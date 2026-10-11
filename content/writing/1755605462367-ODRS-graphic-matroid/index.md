---
title: "Online dependent rounding schemes for graphic matroids"
date: 2025-08-19
draft: false
description: "a description"
tags: ["algorithms"]
aliases:
  - "/blog/1755605462367-odrs-graphic-matroid/"
disqus_url: "https://ngkan.me/blog/1755605462367-odrs-graphic-matroid/"
---

As parts of my semester project in the theory group at EPFL, I studied
how well we can round fractional values within matroid polytopes in an online 
fashion. There is a lack of understanding on the online version of this problem 
despite extensive researches in the literature on the offline version.

In this blog I will go through (on a high level) how I approached the problem,
under graphic matroid conditions.

## TL;DR

**Theorem**: There exist graphic matroid ODRSes with rounding ratio 
$\frac{2}{\sqrt{27}} \cdot \frac{1}{\sqrt{n}}$, where $n$ is the number of vertices in the graph.

This result is not tight and I believe that there would exist an algorithm with 
$O\left(\frac{1}{\log n}\right)$ rounding ratio.

## Problem definition

Formally, we are given a matroid $\mathcal{M} = (E, \mathcal{I})$, and a
polytope relaxation $P_\mathcal{\mathcal{M}}$, which is usually
$\textnormal{conv}(\left\lbrace 1_{\left[I\right]} | I \in \mathcal{I{}}\right\rbrace)$.
The elements of $E$ arrive one by one, and when an element $e$ arrives
with its associated fractional value $x_e$, the algorithm must decide
irrevocably whether to choose it or not. At all times, the set of
currently selected elements $I$ must satisfy $I \in \mathcal{I}$. The
objective of our algorithms is to pick each element $e$ with probability at
least $\alpha \cdot x_e$ for $\alpha \in [0, 1]$ as large as possible, in which
we call the maximal $\alpha$ the rounding ratio of the algorithm.

## Warm-ups

There exist ODRSes with $\alpha = 1$ for uniform matroids (why?).

I believe that efficient ODRSes for any kind of matroids depend on how well we 
can incorporate and manipulate a set of uniform-ODRSes into the algorithms.

## Contraction & merging uniform ODRS instances

Let there be an instance of uniform ODRS between any pair of vertices.
As an online edge arrive, we will handle it according to the ODRS instance corresponding
to that edge. If the corresponding ODRS choose it, then we will contract the edge,
as well as merging all the relevant ODRSes.

I managed to find a merging routine that guarantees a rounding ratio lower bound of 
$O\left(\frac{1}{\sqrt{n}}\right)$, however it uses almost 0 prior information 
of the graph beside the number of vertices.

A good idea to follow-up is to incorporate observations and claims of the form “with 
high probability, the number of X such that Y is bounded”.
