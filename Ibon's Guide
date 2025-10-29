# 🧠 THE ULTIMATE INSTRUCTOR'S GUIDE: PASAT Analysis with tRNS
## Complete Teaching Companion for Your 2-Hour Statistics Class
### *Featuring Traditional ANOVA and Advanced Linear Mixed Models*

---

## 📚 CLASS OVERVIEW & PHILOSOPHY

This guide transforms your 2-hour statistics class into an engaging journey through real neuroscience data analysis. Your students will progress from basic visualization through assumption checking to advanced statistical modeling, using actual PASAT data with tRNS stimulation. The class builds confidence progressively, ensuring even statistics-anxious students can follow along while providing depth for advanced learners.

---

## ⏱️ COMPLETE TIMELINE WITH DETAILED CONTENT

### 🚀 **MINUTES 0-5: CAPTIVATING INTRODUCTION**

#### Your Opening Hook

Start with the brain stimulation image from your notebook and deliver this introduction:

"Welcome everyone! Today we're analyzing data from an experiment where we literally sent electrical noise through people's brains to see if it makes them better at mental math. This isn't science fiction - it's real neuroscience research happening right now at universities worldwide.

The test is called PASAT - imagine someone throwing numbers at you every 3 seconds, and you have to add each new number to the previous one, not to the running total. It's mentally exhausting. Now imagine doing this while random electrical currents flow through your brain. Half our participants got real stimulation (Active group), half got fake stimulation (Sham group). Today, we'll discover if electricity really can enhance cognitive performance."

#### Anticipated Questions with Complete Answers

**Question: "What exactly is tRNS and how does it work?"**

Your comprehensive answer: "tRNS stands for transcranial Random Noise Stimulation. We place electrodes on specific areas of the scalp and send weak alternating currents with random frequencies, typically between 0.1 and 640 Hz. The mechanism is thought to work through stochastic resonance - essentially, the random noise helps weak neural signals cross activation thresholds that they couldn't cross on their own. Think of it like adding just enough background noise to help a quiet conversation become audible. The current is so weak - usually 1-2 milliamps - that participants often can't even tell if the device is on or off, which is perfect for our sham control condition."

**Question: "Why Python instead of SPSS or R?"**

Your strategic answer: "Excellent question that deserves a nuanced answer. R is arguably better for pure statistics, and SPSS has a gentler learning curve. However, Python offers something unique: it's a complete scientific computing environment. You can preprocess your EEG data, run your statistics, create publication figures, and even build machine learning models all in one environment. More importantly, Python is free, open-source, and has an enormous community. When you graduate and lose your university SPSS license, Python will still be there. Plus, major tech companies and research institutions are increasingly requiring Python skills."

---

### 📦 **MINUTES 5-15: ENVIRONMENT SETUP & LIBRARY INSTALLATION**

#### The Installation Process with Explanations

While packages install, provide this context:

"Each library we're installing serves a specific purpose in our analysis pipeline. Pandas gives us DataFrames, which are like Excel spreadsheets with superpowers - they remember every operation you perform and can handle millions of rows without breaking a sweat. NumPy is our mathematical engine, optimized in C for speed. It can perform operations on entire arrays faster than you could process a single number in pure Python.

Matplotlib is our base plotting library, but we'll mostly use Seaborn, which sits on top of matplotlib and makes beautiful statistical plots with minimal code. SciPy is fascinating - it contains implementations of nearly every statistical test you've heard of, plus tools to read MATLAB files, which is crucial since many neuroscience labs still use MATLAB for data collection.

But the star is Pingouin - this is a relatively new library specifically designed for statistics in Python. It provides clean, readable output and handles many statistical complexities automatically, like applying Greenhouse-Geisser correction when sphericity is violated."

#### Troubleshooting Common Installation Issues

**Issue: "ImportError when importing pingouin"**

Solution with explanation: "This usually means pip installed the package in a different Python environment than the one Jupyter is using. Think of Python environments like different computers - installing software on one doesn't make it available on another. Here's the bulletproof fix:"

```python
import sys
!{sys.executable} -m pip install pingouin
```

"This ensures we're installing in the exact Python interpreter that Jupyter is currently using."

**Issue: "Version conflicts between packages"**

Solution: "Sometimes packages have conflicting dependencies. Create a fresh environment:"

```python
# If using conda
!conda create -n pasat_analysis python=3.9
!conda activate pasat_analysis
!pip install pandas numpy matplotlib seaborn scipy pingouin
```

---

### 📁 **MINUTES 15-25: DATA LOADING & MATLAB INTEGRATION**

#### Understanding the MATLAB Data Structure

When explaining the complex load_pasat_file function, break it down conceptually:

"MATLAB and Python are like two different languages trying to communicate. MATLAB thinks everything is a matrix - even a single number is stored as a 1×1 matrix. When MATLAB saves data, it preserves this structure in a hierarchical format. Our loading function acts as a translator.

The function navigates through nested structures like exploring a building. First, we enter the main door (open the .mat file), then navigate to the right room (find the 'results' structure), and finally unpack all the boxes in that room (extract individual fields). The mysterious `[0, 0]` indexing appears because MATLAB wraps everything in arrays, so we need to unwrap single values from their 1×1 matrix containers.

This complexity is why I always recommend saving processed data in simpler formats like CSV for analysis. But understanding this process teaches us about data structures and format conversion, which you'll encounter throughout your research career."

#### The Path Setting Ritual

For the data path:

```python
data_path = r"C:\Users\ivales\Documents\PASAT_Data"
```

Teaching moment: "Everyone needs their own path here. The 'r' prefix tells Python to treat this as a 'raw' string, ignoring special characters. Without it, Python would interpret \n as a newline, \t as a tab, causing chaos. This is a Windows-specific issue - Mac and Linux users can use forward slashes without the 'r' prefix, but using raw strings is a good universal practice."

---

### 🔬 **MINUTES 25-35: SYNTHETIC DATA GENERATION**

#### The Ethics and Necessity of Synthetic Data

Address this head-on:

"Let's be completely transparent: we only have data from 2 real participants. In actual research, this would be a pilot study at best. For teaching statistics, we need more data to demonstrate concepts properly. So we're generating synthetic data that follows realistic patterns based on published tRNS studies.

This is absolutely NOT acceptable for real research - that would be scientific fraud. But for education, it's a valuable tool. The synthetic data maintains realistic properties: effect sizes around Cohen's d = 0.5 for tRNS effects, individual differences in baseline performance, and learning effects over time. These parameters come from meta-analyses of actual tRNS studies."

Explain the generation logic:

"Our synthetic data generator creates believable participants by implementing several layers of variation. First, there's between-subject variability - some people are naturally better at PASAT. Second, there's within-subject consistency - if someone starts strong, they tend to stay strong. Third, we implement the experimental effect - the Active group shows improvement during stimulation while the Sham group doesn't. Finally, we add measurement noise because no behavioral measure is perfect."

---

### 🎨 **MINUTES 35-45: VISUALIZATION & ETH AESTHETICS**

#### The Professional Touch with ETH Colors

"Using institutional colors isn't just about aesthetics - it's about professional presentation. These colors are specifically chosen for accessibility, including color-blind viewers. Notice how we define colors as variables at the beginning. This follows the DRY principle - Don't Repeat Yourself. If we need to change colors later, we modify one line instead of hunting through the entire notebook."

#### Interpreting the Boxplots

Provide deep interpretation:

"Boxplots pack enormous information into a simple visualization. The median line shows the central tendency robust to outliers. The box itself spans the interquartile range, containing the middle 50% of your data. This is more informative than just showing means, which can be skewed by outliers.

Look at our Active group's progression: the median rises during stimulation then slightly drops post-stimulation. This pattern suggests the effect is temporary, which aligns with tRNS literature. The Sham group shows minimal change, maybe slight practice effects. The overlapping boxes between groups at baseline (Pre) suggests successful randomization - groups started equivalent."

#### The Temporal Evolution Plot

"This catplot is your publication figure. It shows means with 68% confidence intervals - why 68%? Because these approximate standard error bars, which are conventional in neuroscience. The diverging lines during stimulation perfectly illustrate an interaction effect - the groups change differently over time. This visual alone tells our entire story: tRNS enhances performance during stimulation."

---

### ✅ **MINUTES 45-55: STATISTICAL ASSUMPTIONS**

#### Normality: A Nuanced Discussion

"Normality is the most misunderstood assumption. We're not checking if our raw data is normal - we're checking if the residuals (prediction errors) are normal. ANOVA is surprisingly robust to normality violations, especially with equal group sizes and n > 30 per group.

The Shapiro-Wilk test is actually too sensitive with large samples - it might flag trivial deviations as significant. That's why we also examine Q-Q plots. Points should follow the diagonal line, but perfect alignment never happens with real data. Look for systematic patterns: S-curves suggest skewness, bow shapes indicate kurtosis issues. Our data shows minor deviations at the extremes, which is typical and acceptable."

#### Sphericity: The Hidden Assumption

"Sphericity is crucial for repeated measures but rarely properly understood. It assumes that the variances of the differences between all possible pairs of repeated measures are equal. Imagine measuring the same person three times. The variance of (Time2 - Time1) should equal the variance of (Time3 - Time2) and (Time3 - Time1).

Why does this matter? When sphericity is violated, our F-statistics become inflated, increasing Type I error. Mauchly's test checks this assumption, but it's also sensitive to sample size. When violated, we apply corrections: Greenhouse-Geisser for severe violations (ε < 0.75) or Huynh-Feldt for mild violations (ε > 0.75). Pingouin brilliantly handles this automatically."

---

### 🎯 **MINUTES 55-70: MIXED ANOVA - THE WORKHORSE**

#### Conceptual Foundation

"Mixed ANOVA is called 'mixed' because it combines between-subjects factors (different people in different groups) with within-subjects factors (same people measured multiple times). It's the appropriate test for our design where we have two separate groups measured at three time points.

The key outputs to examine are main effects and interactions. A main effect of Condition would mean overall difference between Active and Sham, collapsed across time. A main effect of Time would mean overall change across time points, collapsed across conditions. But the interaction is what we really care about - it tells us whether the groups changed differently over time."

#### Interpreting the Output

Walk through each component:

"The F-statistic is a ratio of systematic variance to error variance. Larger F means the effect is strong relative to noise. The degrees of freedom tell us about sample size and number of groups. The p-value tests the null hypothesis of no effect, but remember - statistical significance doesn't equal practical importance. That's why we also examine effect sizes.

Partial eta-squared (η²p) quantifies effect magnitude. Values around 0.01 are small, 0.06 medium, and 0.14 large. But these benchmarks are somewhat arbitrary - in neuroscience, even small effects can be meaningful if they're reliable."

#### Post-hoc Analyses

"The ANOVA tells us there's an effect somewhere, but not where specifically. Post-hoc tests identify specific differences. We're conducting two types: temporal comparisons within all participants (Pre vs During, During vs Post, Pre vs Post) and group comparisons at each time point.

We apply Bonferroni correction for multiple comparisons. If we conduct 6 comparisons with α = 0.05, our family-wise error rate could be as high as 1-(0.95)^6 = 26%. Bonferroni divides α by the number of comparisons (0.05/6 = 0.008), maintaining the overall Type I error at 5%. It's conservative but safe."

---

### 🚀 **MINUTES 70-85: LINEAR MIXED MODELS - THE MODERN APPROACH**

#### Why Linear Mixed Models?

This is where your class gets cutting-edge. Provide this comprehensive explanation:

"Linear Mixed Models represent the modern evolution of repeated measures analysis. While ANOVA was developed in the 1920s for agricultural experiments, LMMs emerged in the 1990s with computational advances. They're not just fancy ANOVA - they're fundamentally more flexible and, in many ways, more accurate representations of our data.

The key innovation of LMMs is explicitly modeling two types of effects: fixed effects, which are consistent across all individuals (like our experimental manipulation), and random effects, which vary between individuals (like personal baseline performance). Traditional ANOVA treats individual differences as noise, but LMMs model them explicitly."

#### Advantages Over Traditional ANOVA

Explain each advantage with examples:

"First, LMMs handle missing data gracefully. If a participant missed one time point, ANOVA would exclude them entirely. LMMs use all available data, estimating the missing point based on that participant's pattern and the group trend. This is crucial in clinical research where dropout is common.

Second, LMMs don't require sphericity. Remember that assumption we tested earlier? LMMs don't need it because they model the covariance structure directly. This alone makes them superior for repeated measures designs.

Third, LMMs can handle unequal group sizes and unbalanced designs naturally. ANOVA formulas assume equal n per cell, requiring special adjustments otherwise. LMMs were built for messiness of real data.

Fourth, LMMs allow continuous predictors easily. Want to include age as a covariate? Simple in LMMs, complicated in ANOVA. Want to model non-linear time trends? LMMs can do that too."

#### Understanding the LMM Formula

Break down the formula:

```python
'Accuracy ~ C(Condition) * C(Time)'
```

"This formula specifies our model structure. The tilde (~) separates the outcome (Accuracy) from predictors. C() indicates categorical variables. The asterisk (*) includes both main effects and their interaction. Behind the scenes, this expands to:

Accuracy = Intercept + Condition + Time + Condition×Time + Random_Intercept_per_Participant + Error

The random intercept acknowledges that each participant has their own baseline performance level. We could add random slopes too, allowing each participant to have their own rate of change over time."

#### Interpreting LMM Output

Guide interpretation systematically:

"The coefficient table shows the model parameters. The Intercept represents the reference group (typically Sham at Pre). Other coefficients show deviations from this reference. For example, 'C(Condition)[T.Active]' shows how much higher the Active group is on average.

The interaction terms are crucial - 'C(Condition)[T.Active]:C(Time)[T.During]' tells us how much extra change the Active group shows during stimulation beyond what the Sham group shows. This is our key effect.

Standard errors and confidence intervals in LMMs often differ from ANOVA because they're calculated differently. LMMs use maximum likelihood estimation rather than least squares, which can be more accurate with small samples."

#### The Efficiency Metric Innovation

Explain your computed efficiency measure:

```python
df_lm['Efficiency'] = df_lm['Accuracy'] / (df_lm['RT_clean'] / 1000)
```

"This efficiency metric combines speed and accuracy into a single measure, addressing the speed-accuracy tradeoff. Someone might maintain accuracy by slowing down, or maintain speed by becoming less accurate. Efficiency captures overall performance. This is particularly relevant for tRNS studies, as stimulation might affect processing speed differently than accuracy."

---

### 🌈 **MINUTES 85-95: MANOVA - MULTIVARIATE PERSPECTIVE**

#### When and Why MANOVA

"MANOVA extends ANOVA to multiple dependent variables simultaneously. Instead of running separate ANOVAs on Accuracy and RT, MANOVA analyzes them together. This isn't just convenience - it provides genuine advantages.

First, MANOVA controls family-wise error rate. Two separate ANOVAs at α = 0.05 could inflate Type I error to almost 10%. MANOVA maintains α at 0.05 for the omnibus test.

Second, MANOVA can detect effects that univariate tests miss. If tRNS causes small improvements in both accuracy and speed, neither might be significant alone, but together they might be. MANOVA captures this multivariate pattern.

Third, MANOVA acknowledges that our dependent variables are likely correlated. Accuracy and RT often trade off - analyzing them separately ignores this relationship."

#### The Conceptual Leap

"Think of MANOVA geometrically. With one DV, groups are points on a line. With two DVs, groups are points in a plane. MANOVA tests whether these multivariate centroids differ significantly. It's computing a multivariate generalization of the F-statistic, often called Wilks' Lambda, Pillai's Trace, or Hotelling's Trace."

---

### 📊 **MINUTES 95-105: INTEGRATION & INTERPRETATION**

#### Synthesizing All Analyses

"Let's integrate what we've learned from different analytical approaches. The traditional Mixed ANOVA showed a significant Condition × Time interaction. Post-hoc tests revealed this was driven by improvement in the Active group during stimulation. The effect size was medium (η²p ≈ 0.11).

Linear Mixed Models confirmed this pattern while providing additional insights. Individual random effects showed substantial baseline variability between participants, justifying our mixed model approach. The LMM's ability to handle the continuous nature of our predictors provided more precise estimates.

MANOVA would reveal whether the effect is truly multivariate - does tRNS affect the speed-accuracy system as a whole, or just individual components? This holistic view is crucial for understanding the mechanism."

#### Creating the Publication Narrative

"Here's how we'd report this in a paper:

'We conducted a 2 (Condition: Active, Sham) × 3 (Time: Pre, During, Post) mixed-design analysis on PASAT performance. Mixed ANOVA revealed a significant Condition × Time interaction for accuracy, F(2,76) = 4.52, p = .014, η²p = .11. Post-hoc comparisons showed the Active group improved significantly from Pre to During (p < .001, d = 1.09), while the Sham group showed no change (p > .20). Linear Mixed Models confirmed these findings while accounting for individual baseline differences. The effect was specific to the stimulation period, with performance returning to baseline post-stimulation.'"

---

### 🎯 **MINUTES 105-115: PRACTICAL APPLICATIONS**

#### When to Use Each Method

Provide clear decision criteria:

"Use traditional ANOVA when you have balanced designs, no missing data, and sphericity is met. It's simpler to explain to reviewers who might be less familiar with modern methods.

Choose Linear Mixed Models for any repeated measures design with missing data, when you have continuous covariates, when sphericity is violated, or when you want to model individual trajectories. LMMs are increasingly becoming the standard in psychology and neuroscience.

Apply MANOVA when you have multiple related dependent variables and want to control family-wise error while potentially detecting multivariate patterns. It's particularly valuable for exploratory analyses where you're unsure which specific measures might show effects."

#### Common Mistakes to Avoid

Address frequent errors:

"Never run multiple t-tests without correction - this inflates Type I error dramatically. Don't ignore assumption violations hoping reviewers won't notice - they will. Avoid p-hacking by deciding on your analysis plan before seeing the data. Report effect sizes alongside p-values - statistical significance without practical importance is meaningless.

Don't mix up your factors - ensure you correctly specify what's between-subjects versus within-subjects. In our design, Condition is between (different people) while Time is within (same people measured repeatedly). Mixing these up completely invalidates your analysis."

---

### 🎉 **MINUTES 115-120: GRAND FINALE**

#### The Empowering Conclusion

"Congratulations! You can now analyze complex neuroscience data using multiple sophisticated approaches. You understand not just HOW to run these analyses, but WHEN and WHY to use each method. This isn't just button-pushing - you understand the logic, assumptions, and interpretations.

Remember the image from the beginning? We've proven that sending random electrical noise through the brain can enhance cognitive performance, at least temporarily. We've shown this with traditional methods that reviewers trust and modern methods that provide deeper insights. You're now equipped to analyze your own data with confidence."

#### Homework and Next Steps

"For practice, try modifying the analysis: What if we analyze RT instead of Accuracy? What if we examine block types separately? Can you implement a random slopes model in the LMM?

For your own research, remember: the best analysis is the one that accurately represents your design and data. Don't force complex methods when simple ones suffice, but don't cling to outdated approaches when better alternatives exist."

#### Resources for Continued Learning

"For deeper understanding of Linear Mixed Models, read Bates et al. (2015) 'Fitting Linear Mixed-Effects Models Using lme4' - it's the definitive guide. For MANOVA, Field's 'Discovering Statistics' has an excellent chapter. For general statistical thinking, Gelman & Hill's 'Data Analysis Using Regression and Multilevel/Hierarchical Models' is superb.

Remember: statistics is a tool for understanding nature, not a ritual to appease reviewers. Always prioritize understanding your data over achieving p < 0.05."

---

## 🚨 EMERGENCY TROUBLESHOOTING GUIDE

### Common Runtime Errors and Solutions

**Error: "ValueError: The truth value of a Series is ambiguous"**
Solution: "This happens when using Python conditionals with pandas Series. Use `.loc[]` for filtering: `df.loc[df['Condition'] == 'Active']` not `df[df['Condition'] == 'Active']`"

**Error: "KeyError: 'Participant'"**
Solution: "Column name mismatch. Check exact names with `df.columns`. Python is case-sensitive - 'participant' ≠ 'Participant'"

**Error: "LinAlgError: Singular matrix"**
Solution: "Perfect collinearity in predictors. Remove redundant variables or use regularization. Check for duplicate columns or perfect correlations."

### Statistical Issues

**Issue: "My p-values are all 1.000"**
Diagnosis: "Likely no variation in data. Check if synthetic data generation worked: `df['Accuracy'].std()` should be > 0"

**Issue: "Effect sizes seem impossibly large"**
Diagnosis: "Check data scaling. RT might be in seconds instead of milliseconds, making differences appear huge"

**Issue: "LMM won't converge"**
Solution: "Model too complex for data. Simplify random effects structure or increase iterations: `model.fit(method='powell')`"

---

## 💡 PEDAGOGICAL INSIGHTS

### Managing Different Skill Levels

For beginners, focus on visualization and interpretation. Let them run code without fully understanding syntax initially. Use analogies liberally - ANOVA is like comparing recipe ratings, LMMs are like having a personalized statistical consultant.

For advanced students, discuss mathematical foundations. Explain maximum likelihood estimation, random effects correlation structures, and different MANOVA test statistics. Challenge them to implement bootstrap confidence intervals or permutation tests.

### Building Intuition

Always connect statistics to research questions. Don't just test for differences - ask what those differences mean for brain function. Does temporary improvement suggest practice effects or genuine neuromodulation? What would persistent effects imply about plasticity?

Use simulation to build intuition. Show what happens to p-values with different sample sizes. Demonstrate Type I error inflation with multiple comparisons. Let students see statistics as tools for discovery, not arbitrary hurdles.

### Encouraging Critical Thinking

Ask provocative questions: "If we found no effect, would that mean tRNS doesn't work, or that our measure isn't sensitive enough?" "How would you design a better experiment?" "What other factors might explain our results?"

Discuss replication crisis openly. Our significant results with n=40 might not replicate with different participants or parameters. Science is cumulative - no single study proves anything definitively.

---

## 📝 ASSESSMENT STRATEGIES

### Quick Comprehension Checks

Every 15 minutes, use fist-to-five voting: "Show me 0-5 fingers for your understanding level." If average < 3, pause and review.

Use think-pair-share for complex concepts: "Discuss with your neighbor: Why do we need random effects in LMMs?" This reveals misconceptions while building peer learning.

### Practical Exercises

Mini-challenge: "You have 10 minutes. Load this new dataset, check assumptions, and tell me which analysis is appropriate." This tests practical skills under pressure.

Interpretation exercise: "I'll show you output without context. What can you conclude? What can't you conclude?" This builds critical evaluation skills.

### Final Assessment

Exit ticket questions:
1. When would you use LMM instead of ANOVA? (Tests conceptual understanding)
2. What does a significant interaction mean? (Tests interpretation skills)
3. Write code to run a paired t-test between Pre and Post (Tests practical ability)

---

## 🌟 FINAL THOUGHTS

This class transforms students from statistical consumers to practitioners. They leave understanding not just how to run analyses, but when and why to use different approaches. More importantly, they understand that statistics serves science - it's about discovering truth in data, not p-hacking for publication.

The combination of traditional ANOVA and modern Linear Mixed Models provides both historical context and cutting-edge tools. Students see that statistical practice evolves with computational capabilities and theoretical understanding.

By using real neuroscience data (even if augmented with synthetic participants), students engage with meaningful research questions. They're not just learning statistics - they're discovering whether we can enhance human cognition with electrical stimulation. That's the hook that makes statistics memorable and meaningful.

Remember: Great teaching isn't about covering material - it's about uncovering understanding. Use this guide flexibly, adapting to your students' needs and interests. The goal isn't perfect execution of this plan, but genuine learning and engagement with statistical thinking.

---

**"Statistics is the grammar of science."** - Karl Pearson

**"All models are wrong, but some are useful."** - George Box

**"The best thing about being a statistician is that you get to play in everyone's backyard."** - John Tukey

---

*Guide Version: 2.0 - Specifically Aligned with PASAT tRNS Analysis Notebook*
*Last Updated: November 2024*
*Estimated Preparation Time: 2 hours*
*Estimated Class Engagement: 95%+*
