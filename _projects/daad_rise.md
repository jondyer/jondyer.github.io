---
layout: page
title: creative cognition
description: research engineering with cognitive systems in Germany
img: assets/img/publication_preview/comrat.png
importance: 2
category: academic
toc:
  sidebar: left
related_publications: comrat_article, ieee_conference
---

## Background

This page presents the work I focused on and produced during my time as a DAAD-RISE scholar at the Universität Bremen in Bremen, Germany. I was awarded
a scholarship to study and research with the [Cognitive Systems Group](https://www.cosy.informatik.uni-bremen.de/), focusing on computational measures of creativity and creative problem solving.

My research supervisor during this time was [Ana-Maria Olteteanu](https://www.linkedin.com/in/anamariaolteteanu/), who studied knowledge representations and processes
that can be applied to cognitively-inspired AI for creative problem-solving, especially in environments with incomplete knowledge.

### Remote Associates Test

The [Remote Associates Test](https://www.remote-associates-test.com/) (RAT) is a popular test amongst behavioral psychologists and researchers for testing and measuring creativity. It is assumed to measure a specific type of creativity, _convergent creativity_, which is (roughly) the ability to combine different pieces of stored information to find a single or restricted answer to a problem. This is by contrast to many other creativity tests, which are more geared towards measuring _divergent_ thinking, e.g. the Alternative Uses Test (Guilford, 1967).

The RAT is formatted as a series of three-word groups, representing cues. These are each linked to an unknown fourth word, which is the correct answer. Each cue typically forms a compound with the target word, as illustrated below.

| RAT item | Solution |
| --- | --- |
| cottage / swiss / cake | cheese |
| cream / skate / water | ice |
| show / life / row | boat |

<br>

___

## Projects

During this time I had a few primary projects related to the RAT:

### comRAT-C

The comRAT-C system was a computational solver for RAT queries, which used a [corpus of American English](http://corpus.byu.edu/coca/) to calculate the frequency of query and answer words co-occurring and from that the probability of any given word being the solution. It turns out that these metrics (frequency and probability) are correlated to human performance on the test. An example illustration of data representation by the solver is below. More details can be found in the publication (see References).

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/publication_preview/comrat.png" title="comRAT-C network" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Since this portion of the research was mostly complete by the time I arrived, my role for this system was small, involving performance improvements for the RAT solver. This entailed optimizing high-performance code in Java and improving data storage and access times. My primary contributions were in the next two projects.

___

### comRAT-G

Although the Remote Associates test has been very popular as a creativity test, as with many such tests it has been difficult to control for various factors (difficulty, frequency, etc) in the components of the test. The test is not typically standardized according to any measure, nor does it provide any norms or baselines.
Additionally, the set of questions available for the test is very small, coming mostly from a few original papers quite some time ago (Mednick & Mednick, 1971).

Consequently, we sought to  build up the existing pool of compound RAT items by generating new compound RAT queries. To do this we took advantage of the corpus and data structures already in place and inverted the RAT solver (comRAT-C) to look for queries rather than answers. This generative method also allowed control over variables such as frequency of co-occurrence and probability of finding an answer. Thus was born comRAT-G.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/comrat_g_table.png" title="comRAT-G example" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

Here $$w_{ans}$$ is the answer word and $$w_q$$ is a potential query word. The third column is the frequency of association between the query word $$w_q$$ and the answer word $$w_{ans}$$, while the fourth column represents the frequency between the query word and any word. Finally the fifth column is the probability of the answer given the specific query word $$w_q$$.

In all, we generated over 17 million potential noun-noun compound RAT queries which can be controlled for frequency and probability. Details are available in the published paper (see References).

___

### Adaptive Answer Strategies

Finally, I developed further ideas related to strategies of humans in answering RAT queries, and the differences between those strategies depending on the types of associations (semantic vs compound relations) the query words had with each other. This led to multiple conference presentations and further research by Ana-Maria and the Cognitive Systems Group (see References).

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/comrat_functional.png" title="RAT functional" class="img-fluid rounded z-depth-1" %}
    </div>
</div>

<br>

<br>
