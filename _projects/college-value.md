---
layout: page
title: value of college
description: Data analysis comparing cost-effectiveness of a college education using College Scorecard data
img: assets/img/dsbd_1/cmu_logo.png
importance: 3
category: academic
toc:
  sidebar: left
---

As part of our course _Data Science and Big Data_ with [Raja Sooriamurthi](https://scholars.cmu.edu/4669-raja-sooriamurthi/teaching), my partner and I performed an analysis of the value of a college education. Key takeaways (and a brief video presentation by Shikha) are below, or you can view the full report on [Github](https://github.com/jondyer/dsbd/blob/master/projects/project1/project_1_report_final.ipynb).

<div class="row mt-3">
    <div class="col-sm mt-3 mt-md-0 embed-responsive embed-responsive-16by9">
        {% include video.html path="https://www.youtube.com/embed/aybZ3MBRhCE" class="embed-responsive-item rounded z-depth-1" controls=true %}
    </div>
</div>

<br>

## Background

As students at Carnegie Mellon University--a high-cost institution--we wanted to know if our future earnings potential is worth the trouble to get into an expensive, elite university like ours. Using the [College Scorecard data](https://collegescorecard.ed.gov/data/) from the U.S. Department of Education, we explored the question: **Is college (specifically CMU) worth the expense?**

A preliminary exploration showed a trend of high tuition fees corresponding with high post-graduation earnings. Additionally, earnings seem to show a negative correlation with the percentage of Pell grant recipients at a school, which is a proxy for the number of low-income students at a school.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_earnings_vs_tuition.png" title="earnings vs tuition" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_earnings_vs_pell.png" title="earnings vs percent" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>
<div class="caption">
    Higher incomes are correlated with higher tuition fees. The highest earners seem to come from the schools with the lowest percentage of Pell grant recipients.
</div>

To dig into this question further, we viewed it through the lens of a typical student's college journey, which generally comprises 4 parts:

1. Admissions
2. Tuition
3. Debt
4. Earnings

Fortunately the College Scorecard dataset has an abundance of data on all of these areas, covering a span of more than two decades. Takeaways for each of these questions follow.

<br>

## 1. Admissions

When comparing admissions data with other schools and earnings, a few points become obvious:

* CMU is much more selective than the average school
* CMU is _less selective_ than many other elite schools
* Top schools have become _more_ selective over time
* Higher earning colleges tend to be more selective

Especially noteworthy is that CMU manages to obtain some of the highest earnings outcomes as well as an admission rate that is double or even triple some other elite colleges. (I would like to see this scaled by number of applicants and overall school capacity; a very high admission rate is not that impressive if no one applies to your school.)

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_admissions_1.png" title="cmu vs non-cmu admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_admissions_2.png" title="top 25 admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_admissions_3.png" title="earnings vs admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

<br>

## 2. Tuition

Here we find some more interesting numbers:

* CMU has not only been one of the more expensive schools to attend, but its tuition fees have gone up much faster than most other schools (especially public schools).
* Despite the increase in tuition, average family income for a student has more or less kept pace.
* Colleges with higher earnings tend to be more expensive; there are obviously a lot of other factors here, since the ability to afford an expensive school **likely indicates other privileges** that would translate to higher earnings as well.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_tuition_1.png" title="cmu vs non-cmu admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_tuition_2.png" title="top 25 admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_tuition_3.png" title="earnings vs admissions" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

<br>

## 3. Debt

The story here is common knowledge: student debt on average has doubled in the last 20 years, with default rates spiking in the years after the Great Recession.
CMU student debt is especially high, although loan default rates were apparently unaffected. This could be thanks to high family income (support from home) and also the high earnings for CMU grads enabling those students to pay off their debt.

The most notable insight here was the discrepancy between CMU and other top universities when it comes to borrowing rates and median family income:

* CMU had very high borrowing rates compared to other top schools
* CMU had very high median family income compared to many other top schools

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_debt_1.png" title="borrowing rates" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_debt_2.png" title="median family income" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

This was surprising, since we had supposed that perhaps Ivy League colleges were simply attended by wealthier students who could afford not to take a federal loan. But the family income data disputed this theory, instead indicating that CMU is not nearly as accessible to low-income students as other top schools. What would explain this difference?

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        Some searching on the web gave us the answer: "No-Loan Colleges". This is a newer commitment among many top universities which seeks to combat rising student debt by awarding <b>extra grant-based aid</b> without pushing students towards federal loans first.
    </div>
    <div class="col-sm mt-3 mt-md-0">
        <a href="https://thescholarshipsystem.com/blog-for-students-families/a-complete-list-of-no-loan-colleges-and-what-it-means-to-your-student/">
            {% include figure.html path="assets/img/dsbd_1/dsbd_1_debt_no_loan.png" title="no-loan schools" class="img-fluid rounded z-depth-1" %}
        </a>
    </div>
</div>

<br>

## 4. Earnings

Finally we can look at earnings over time for CMU graduates. Here we see clearly what has been indicated already in previous sections: CMU has much higher earnings outcomes than average, and it looks set to continue that way.

<div class="row justify-content-sm-center">
    <div class="col-sm mt-3 mt-md-0">
        {% include figure.html path="assets/img/dsbd_1/dsbd_1_earnings.png" title="CMU earnings over time" class="img-fluid rounded z-depth-1" zoomable=true %}
    </div>
</div>

<br>

## Findings

Our original question was: **Will we get a return on our investment for coming to CMU?**

The answer seems clear:

* CMU rewards its graduates with much higher earnings than average, seemingly enough to compensate for the very high tuition and debt that comes with it.
* CMU has relatively high admissions rates compared to many other top schools.

Access to low-income students does _not_ look so excellent for CMU:

* Compared with other elite schools, CMU tends to attract students with higher family incomes (possibly because of the next point).
* Compared with other elite schools, CMU seems to be lagging in two areas:
  * Providing financial aid to students generally
  * Being accessible to low-income students and populations

This analysis should be useful to anyone interested in attending CMU, their parents, administrators, and anyone concerned with the quality and value of CMU's education. In particular, we hope it will respond to the concerns of our primary audience: _current or former students who have wondered if their sacrifice was worth it_. We hope we have reassured you that, in fact, **it was**.