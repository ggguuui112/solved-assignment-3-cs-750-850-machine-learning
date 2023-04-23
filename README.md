Download Link: https://assignmentchef.com/product/solved-assignment-3-cs-750-850-machine-learning
<br>
<span style="font-size: 2.61792em; letter-spacing: -1px; font-family: -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Oxygen-Sans, Ubuntu, Cantarell, 'Helvetica Neue', sans-serif;">Problem 1 [25%]</span>

Suppose that I collected data for a group of machine learning students from last year. For each student, I have a feature <em>X</em><sub>1 </sub>= hours studied for the class every week, <em>X</em><sub>2 </sub>= overall GPA, and <em>Y </em>= whether the student receives an A. We fit a logistic regression model and produce estimated coefficients, <em>β</em><sup>ˆ</sup><sub>0 </sub>= <em>−</em>6<em>,β</em><sup>ˆ</sup><sub>1 </sub>= <em>−</em>0<em>.</em>1<em>,β</em><sup>ˆ</sup><sub>2 </sub>= 1<em>.</em>0.

<ol>

 <li>Estimate the probability of getting an A for a student who studies for 40<em>h </em>and has an undergrad GPA of 2<em>.</em>0</li>

 <li>By how much would the student in part 1 need to improve their GPA or adjust time studied to have a 90% chance of getting an A in the class? Is that likely?</li>

</ol>

<h1>Problem 2 [25%]</h1>

Consider a classification problem with two classes T (true) and F (false). Then, suppose that you have the following four prediction models:

<ul>

 <li><strong>T</strong>: The classifier predicts T for each instance (always)</li>

 <li><strong>F</strong>: The classifier predicts F for each instance (always)</li>

 <li><strong>C</strong>: The classifier predicts the <em>correct </em>label always (100% accuracy)</li>

 <li><strong>W</strong>: The classifier predicts the <em>wrong </em>label always (0% accuracy)</li>

</ul>

You also have a test set with 60% instances labeled T and 40% instances labeled F. Now, compute the following statistics for each one of your algorithms:

<table width="327">

 <tbody>

  <tr>

   <td width="119">Statistic</td>

   <td width="55">Cls. <em>T</em></td>

   <td width="54">Cls. <em>F</em></td>

   <td width="55">Cls. <em>C</em></td>

   <td width="43">Cls. <em>W</em></td>

  </tr>

  <tr>

   <td width="119">recalltrue positive rate false positive rate true negative rate specificity precision</td>

   <td width="55"> </td>

   <td width="54"> </td>

   <td width="55"> </td>

   <td width="43"> </td>

  </tr>

 </tbody>

</table>

Some of the rows above may be the same.

<h1>Problem O2 [30%]</h1>

This problem can be substituted for Problem 2 above, for up to 5 points extra credit. The better score from problems 2 and O2 will be considered.

Solve Exercise <em>3.4 </em>in [Bishop, C. M. (2006). Pattern Recognition and Machine Learning].

1

<h1>Problem 3 [25%]</h1>

In this problem, you will derive the bias-variance decomposition of MSE as described in Eq. (2.7) in ISL. Let <em>f </em>be the true model, <em>f</em><sup>ˆ </sup>be the estimated model. Consider fixed instance <em>x</em><sub>0 </sub>with the label <em>y</em><sub>0 </sub>= <em>f</em>(<em>x</em><sub>0</sub>). For simplicity, assume that Var[] = 0, in which case the decomposition becomes:

                                      <sup>2</sup>

<em>− f</em>

E<sup>h</sup>(<em>y</em><sub>0                      </sub><sup>ˆ</sup>(<em>x</em><sub>0</sub>))<sup>2</sup><sup>i </sup>= Var[<em>f</em><sup>ˆ</sup>(<em>x</em><sub>0</sub>)]+<sub></sub>E[<em>f</em>(<em>x</em><sub>0</sub>) <em>− f</em><sup>ˆ</sup>(<em>x</em><sub>0</sub>)]<sub> </sub><em>.</em>

{z            }

|              {z               }                 Variance      Bias test MSE Prove that this equality holds.

<em>Hints</em>:

<ol>

 <li>You may find the following decomposition of variance helpful:</li>

 <li>This link could be useful: <a href="https://en.wikipedia.org/wiki/Variance#Basic_properties">https://en.wikipedia.org/wiki/Variance#Basic_properties</a></li>

</ol>

<h1>Problem 4 [25%]</h1>

Please help me. I wrote the following code that computes the MSE, bias, and variance for a test point.

<table width="632">

 <tbody>

  <tr>

   <td width="632"><strong>set.seed</strong>(1984) population &lt;- <strong>data.frame</strong>(year=<strong>seq</strong>(1790,1970,10),pop=<strong>c</strong>(uspop)) population.train &lt;- population[1<strong>:</strong><strong>nrow</strong>(population) <strong>– </strong>1,] population.test &lt;- population[<strong>nrow</strong>(population),]E &lt;- <strong>c</strong>() <em># prediction errors of the different models </em><strong>for</strong>(i <strong>in </strong>1<strong>:</strong>10){ pop.lm &lt;- <strong>lm</strong>(pop <strong>~ </strong>year, data = dplyr<strong>::</strong><strong>sample_n</strong>(population.train, 8)) e &lt;- <strong>predict</strong>(pop.lm, population.test) <strong>– </strong>population.test<strong>$</strong>pop E &lt;- <strong>c</strong>(E,e)} <strong>cat</strong>(glue<strong>::</strong><strong>glue</strong>(“MSE:          {mean(E^2)}
”, “Bias^2:                  {mean(E)^2}
”,“Var:                             {var(E)}
”,“Bias^2+Var: {mean(E)^2 + var(E)}”))</td>

  </tr>

 </tbody>

</table>

## MSE:                           2869.61343086216

## Bias^2:                       2681.61281912074

## Var:                             208.889568601581

## Bias^2+Var: 2890.50238772232

I expected that the MSE would be equal to Biasˆ2 + Variance, but that does not seem to be the case. The MSE is 2402<em>.</em>515 and Biasˆ2 + Variance is 2428<em>.</em>706. Was my assumption wrong or is there a bug in my code? Is it a problem that I am computing the expectation only over 10 trials?

<em>Hint</em>: If you are using Python and need help with this problem, please come to see me (Marek).


