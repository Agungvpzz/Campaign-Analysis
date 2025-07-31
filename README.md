> [!NOTE]
> If you encounter an error with the Jupyter Notebook on GitHub, please use the following links:
> <br>- [nbviewer: EDA](https://nbviewer.org/github/Agungvpzz/Campaign-Analysis/blob/main/Campaign%20Analysis.ipynb)
> <br>- [nbviewer: Modeling](https://nbviewer.org/github/Agungvpzz/Campaign-Analysis/blob/main/Campaign%20Analysis%20Modeling.ipynb)


# Campaign Analysis for Bank Marketing
## A. Introduction
<p align="justify">
  This report presents an in-depth analysis of bank marketing campaign data to better understand customer engagement and conversion patterns. Campaign analysis is essential for evaluating the effectiveness of outreach strategies and identifying which customer segments are most responsive to marketing efforts. By analyzing campaign outcomes, we aim to uncover actionable insights that can optimize future campaigns, improve targeting precision, and maximize return on marketing investment. This study leverages data-driven techniques to identify trends in customer response behavior, contributing to smarter decision-making and more impactful marketing initiatives. </p>

## B. Business Understanding


### 1. Business Goals
<p align="justify">
The primary business goal is to increase the effectiveness of marketing campaigns by identifying key factors that influence customer conversion. By understanding when, how, and to whom marketing messages should be delivered, the bank aims to optimize outreach efforts, minimize wasted resources, and maximize conversion rates, ultimately improving customer acquisition and retention.
</p>

### 2. Objective of this analysis
This analysis aims to explore the Portugal Bank marketing dataset to extract actionable insights regarding campaign performance. 
The focus is on:
- Understanding which customer attributes are linked to higher conversion.
- Identifying signs of campaign fatigue.
- Evaluating the timing and type of outreach to improve results.
- Providing data-driven recommendations for future campaigns.


### 3. Key Questions to Answer
The following key questions guide this analysis:
1. What is the overall distribution of conversions?
2. How do categorical and numerical features relate to conversion?
3. Do campaign conversion rates vary across economic and demographic factors?
4. Are longer calls more successful?
5. Does repeated contact increase conversions?
6. What is the optimal number of contacts before diminishing returns occur?
7. Which contact channels are most effective?
8. Are there specific days, weeks, or months with significantly higher conversion rates?


## C. Data Collection
The dataset can be accessed at the following link:<br>
https://www.kaggle.com/datasets/janiobachmann/bank-marketing-dataset?resource=download


## D. Exploratory Data Analysis

### 1. What is the overall distribution of conversions?
<div align=center>

  <img width="318" height="279" alt="image" src="https://github.com/user-attachments/assets/acc89ce4-bc35-49cc-9b35-b93537e7d81f" />
</div>


### 2. How do categorical and numerical features relate to conversion?
<div align=center>
  <img width="744" height="422" alt="image" src="https://github.com/user-attachments/assets/1d49e6b8-2c02-4919-8566-2b329f2d896a" />
  <img width="1056" height="512" alt="image" src="https://github.com/user-attachments/assets/aecf68e4-8b09-4806-8ad7-60aadb51e2f1" />
</div>

- Chi-square tests indicate a significant association between all categorical features and conversion outcomes
- The ‘month’ variable stands out with the highest χ² score of 1040, indicating a stronger association with conversion rates than other features.
- It is followed by variables such as ‘previous outcome’, ‘contact’, and ‘first campaign’, each with χ² scores exceeding 500, suggesting they also have a meaningful impact on conversion patterns.
<br><br>

<div align=center>
  <img width="1040" height="567" alt="image" src="https://github.com/user-attachments/assets/070d913b-0e20-4951-a2b2-0a8d76721ec7" />
</div>

- Mduration stands out with the highest statistical significance and the largest effect size (Rank-biserial correlation = 0.522), indicating that customers in the Deposit = True group had significantly longer call durations compared to those in the Deposit = False group.
- Other variables such as n_previous_campaign, balance, n_current_campaign, and day also show statistical significance, but with small effect sizes.
<br><br>

<div align=center>
  <img width="1104" height="472" alt="image" src="https://github.com/user-attachments/assets/fa8fd0e1-2b90-4de3-8f94-741d216bc8cb" />
</div>

- **Longer calls, higher conversions**: Longer call durations stand out with the highest positive correlation to conversion rate (0.45). It’s a clear signal, when prospects are genuinely curious, they stick around, ask questions, and engage meaningfully. Shorter calls often signal disinterest or early drop-off.
- **Echoes from the past**: Customers with more touchpoints from previous campaigns show a mild uptick in conversion likelihood (correlation 0.14). While not a strong effect, it suggests that past engagement might prime them for future decisions.
- **Too much contact, too little interest**: Oddly enough, heavy outreach during the current campaign seems counterproductive. With a slightly negative correlation of -0.13, it hints at possible oversaturation, where repeated contact might cause customers to tune out or resist the offer altogether.


## E. Customer Segment Analysis

### 3. Do campaign conversion rates vary across economic and demographic factors?

####  Economic Factors
<p align="center">  
  <img src="https://github.com/user-attachments/assets/008590ba-650b-42b8-9de1-6807503bd263"/>
  <img src="https://github.com/user-attachments/assets/46f01104-d2d8-4990-8c69-b709aa01bfdc"/>  
  <img src="https://github.com/user-attachments/assets/65f7ce8a-2c45-45d0-b183-9eae270e3452"/>
  <img width="1061" height="291" alt="image" src="https://github.com/user-attachments/assets/f1b6af6d-af71-481a-ac1f-1d52a4bcb42b" />
</p>

- Customers with no credit history (default = no), no personal loan, and no housing loan show the highest conversion rate at 60%, with a conversion count of 3,120, contributing to approximately 59% of total conversions.
- In contrast, customers with no credit history and no personal loan, but who do have a housing loan, show a lower conversion rate of 38%, nearly half the rate of those without a housing loan.
- Customers who end up subscribing to a term deposit generally have higher account balances, whether you're looking at the total, average, or median values.
  - However, the effect size is relatively small, so the difference isn't particularly strong.

####  Demographic Factors
<p align="center">
  <img width="697" height="148" alt="image" src="https://github.com/user-attachments/assets/9173773a-9b1e-4b46-ab46-b905eb15e9db" />
  <img width="1076" height="514" alt="image" src="https://github.com/user-attachments/assets/51038732-a14b-48de-bc81-d67c14117f6f" />
</p>

- Customers who are retired or students show the highest interest in term deposit subscriptions, with conversion rates of 66% and 75%, respectively. These segments likely value long-term financial stability and are more receptive to saving-oriented products.
- In contrast, blue-collar workers and entrepreneurs exhibit significantly lower conversion rates, both below 40%. This may reflect different financial priorities, liquidity concerns, or skepticism toward long-term commitments.


## F. Campaign Fatigue Analysis

### 4. Are longer calls more successful?
<p align="center">
  <img width="1094" height="369" alt="image" src="https://github.com/user-attachments/assets/cf32d362-5e26-4918-ae0e-20f5d4d66cf5" />
</p>

- At the 5-minute mark:
  - 84% of non-converting customers have already ended the call, effectively rejecting the campaign.
  - Manwhile, 42% of converting customers have also disconnected, indicating that a sizable portion of subscribers make quick, confident decisions.
- At the 15-minute mark:
  - 99% of non-converting customers have hung up, suggesting that nearly all rejection decisions are made by this point. It's safe to say that callers remaining after this threshold are highly likely to subscribe.
  - 90% of converting customers have also exited the call by now. The remaining 10%, still engaged beyond the 15-minute mark, represent strong potential for conversion.

**Call Duration: A Behavioral Filter for Conversion Likelihood**
- In the Bank Portugal campaign, call duration emerges as a valuable predictive signal. By analyzing when customers end calls, we observe distinct behavioral profiles:
  - Rejecters typically disengage early, often within the first few minutes, signaling low intent and minimal interest.
  - Subscribers, on the other hand, tend to stay on longer, engaging in more substantive conversations around the offer.
- These patterns indicate that call length isn't a persuasive force on its own, it’s a self-selection mechanism. Longer calls don’t drive conversions directly, but they reveal which customers are genuinely interested. By the 15-minute mark, nearly all non-converters have dropped off, leaving behind a high-intent segment with strong conversion potential.
- This makes call duration a powerful tool for lead scoring and agent prioritization, not as a tactic to stretch conversations, but as a signal to guide targeting decisions and optimize engagement strategy.

### 5. Does repeated contact increase conversions?
<p align="center">
  <img width="953" height="363" alt="image" src="https://github.com/user-attachments/assets/c58f1680-429e-4efa-964e-7e1388e06b69" />
< /p>

- The line plot indicates a significant increase in conversion rates with repeated contact attempts.
- The first contact alone yields a 48.42% conversion rate, while the remaining conversions result (51.58%) from follow-ups.
- While the first contact shows strong initial impact, the follow-up attempts play an equally critical role in boosting the overall conversion rate.
- The data underscores that sustained outreach significantly enhances campaign effectiveness.

### 6. What is the optimal number of contacts before diminishing returns occur?
<p align="center">
  <img width="1109" height="450" alt="image" src="https://github.com/user-attachments/assets/4dcdd1fe-a4da-4697-a664-101ae489249f" />
</p>

- The chart shows a strong improvement in conversion rates with repeated contact. From the 1st to 5th contact, conversion rates increase significantly, from 48.42% to 95.22%.
- This suggests that follow-up attempts are very effective initially.
- Beyond the 5th or 6th contact, additional outreach adds only marginal gains in conversion (e.g., from 95.22% at contact 5 to 99.11% at contact 10).
- The optimal number of contacts is 4 to 5. At this stage:
  - 95.22% of total conversions have already occurred.
  - Further contacts bring minimal incremental gain (only about 4% increase over the next 5 contacts). This indicates that continued effort beyond the 5th contact may not be cost-effective.
- Limiting the outreach to four contact attempts could reduce unnecessary follow-ups by 10,098 (amounting to 36% of total contacts). This presents a meaningful opportunity to optimize resource allocation without significantly compromising conversion performance.


## G. Contact Type Effectiveness

### 7. Which contact channels are most effective?
<p align="center">
  <img width="1110" height="283" alt="image" src="https://github.com/user-attachments/assets/d22a94da-8ac3-492a-b16a-9c83ad691c09" />
</p>

- Cellular contact shows the highest conversion rate at 54.3%, followed closely by telephone at 50.4%.
- In contrast, the unknown contact type yields the lowest conversion rate, just 22.6%.

<p align="center">  
  <img width="1075" height="278" alt="image" src="https://github.com/user-attachments/assets/fc49ef33-274d-428d-884f-dc20a281a0cb" />
</p>

- The stacked bar chart highlights a significant drop-off in conversion across all contact types: over 75% of contacts do not result in a customer subscription. On average, it takes 4 to 5 contact attempts to secure a single conversion.
- The 'unknown' contact type shows the greatest inefficiency. Of 6,442 outreach attempts, only 530 led to a subscription, a conversion rate of just 8.2%, well below the 10% threshold.
- This suggests a need to rethink resource allocation, especially toward poorly performing segments like the 'unknown' contact type. Streamlining contact efforts could help minimize waste and improve overall conversion efficiency.



## H. Optimizing Outreach Timing: One-Attempt Analysis
Under the "Optimizing Campaign Timing" section, we filter the dataset to include only records where the number of contacts equals one. This constraint allows us to precisely assess which specific contact date influences campaign effectiveness. When a customer has multiple contact attempts, the dataset does not indicate when earlier contacts occurred, making it impossible to isolate the impact of any single date.

### 8. Are there specific days, weeks, or months with significantly higher conversion rates?

#### a. Monthly Conversion
<p align="center">  
  <img width="689" height="321" alt="image" src="https://github.com/user-attachments/assets/d43613de-c4a6-4132-ab6f-93e7beabb273" />
</p>

**Chi-Squared Analysis Summary**
- Statistical testing reveals a significant association between monthly conversion patterns and conversion rate behavior.
- The Chi-squared value (551.46) highlights strong non-uniformity in monthly conversion outcomes.
- With a Cramér’s V of ~0.34, the relationship is moderately strong, offering meaningful behavioral and marketing implications.

**Campaign Volume vs. Conversion Efficiency**
- May saw the highest campaign volume but delivered the lowest conversion rate at 35%, indicating potential poor timing.
- In contrast, December had the lowest campaign volume yet achieved a 91% conversion rate, suggesting outstanding campaign precision and effectiveness.

**High-Performing Months**
- Alongside December, March (91%), September (83%), and October (82%) consistently demonstrated above-average conversion performance.
- These months may be considered strategic success windows, with higher conversion efficiency and potential for optimized outreach.

#### b. Weekly Conversion (No Statistically Significant Pattern)
<p align="center">  
  <img width="652" height="196" alt="image" src="https://github.com/user-attachments/assets/ca492a27-f38a-4388-8d40-082bfbfaa243" />
</p>

- Even though the result is statistically significant, the weekly effect is weak and likely has limited impact.

#### c. Day of Week Conversion (No Statistically Significant Pattern)
<p align="center">  
  <img width="693" height="201" alt="image" src="https://github.com/user-attachments/assets/f154ce51-483c-4f17-84d8-c47da6b886ae" />
</p>


#### d. Day of Month Conversion
<p align="center">  
  <img width="1092" height="195" alt="image" src="https://github.com/user-attachments/assets/7d9902b3-f5e7-4053-a5c0-3308d9cb29ca" />
</p>

**Conversion Behavior by Day of the Month**
- Statistical analysis reveals a significant association between conversion rates and calendar day, with p < 0.001 and a moderate effect size (Cramér’s V ≈ 0.21).
- This indicates that the day of the month has a meaningful impact on conversion outcomes, suggesting that campaign timing could be optimized at a daily granularity.

**High-Performing Days**
- Several days, 1, 3, 10, 22, 25, 27, and 71, consistently demonstrate elevated conversion rates near 70%, positioning them as high-opportunity dates for contact efforts.
- These days may warrant targeted scheduling to capitalize on stronger behavioral responses.

**Low-Performing Day**
- Day 19 stands out with the lowest conversion rate, highlighting a potential inefficiency in outreach timing on this date.


## I. Model Development

### Model Performance Summary
<p align="center">
  <img width="617" height="167" alt="image" src="https://github.com/user-attachments/assets/20bb62b4-c323-4aad-82b8-faf77f970eae" />
</p>

- The model performs very well on the training set and maintains strong performance on the test set, indicating good generalization.
- The performance on cross-validation (CV) is also close to test performance, suggesting that the model is stable and robust.
- There’s no major sign of overfitting, as the performance metrics are reasonably close across all datasets.


### Confusion Matrix
<p align="center">
  <img width="351" height="334" alt="image" src="https://github.com/user-attachments/assets/dfadcfa1-d0c9-42c8-9319-bb603466029d" />
</p>

Our model correctly classified 1948 out of 2233 cases.
- True Negatives (TN) = 996 => Model correctly predicted class 0 (no conversion).
- False Positives (FP) = 179 => Model predicted class 1 (conversion), but it was actually class 0.
- False Negatives (FN) = 106 => Model predicted class 0 (no conversion), but it was actually class 1.
- True Positives (TP) = 952 => Model correctly predicted class 1 (conversion).

### All Metrics Across Different Thresholds
<p align="center">
  <img width="1095" height="421" alt="image" src="https://github.com/user-attachments/assets/070e9a2e-000e-4bbd-8975-ed9b9251867c" />
</p>

- This threshold analysis plot provides a comprehensive view of how model performance metrics evolve as the decision threshold shifts from 0 to 1.
- By visualizing metrics like precision, recall, F1 score, and specificity across thresholds, we can better tailor our model's behavior to business priorities, whether minimizing false negatives or reducing false positives.
- It help us identify the optimal threshold that balances trade-offs between sensitivity and specificity, rather than relying solely on the default threshold of 0.5.


### ROC-AUC
<p align="center">
  <img width="706" height="424" alt="image" src="https://github.com/user-attachments/assets/b80ecfa3-dd41-42e4-9310-34714d0310b4" />
</p>

- The high ROC AUC scores suggest the model has excellent classification power.



## J. Conclusion
**1. What is the overall distribution of conversions?**
  - The data shows that the Portugal bank campaign achieved a conversion rate of nearly 50%, with 5,289 customers accepting the offer.

**2. How do categorical and numerical features relate to conversion?**
  - Chi-square tests indicate that all categorical features are significantly associated with conversion outcomes. Among them, six show a moderate association strength based on Cramér's V: months, previous_outcome, channel (contact_type), last_contact, first_campaign, and housing.
  - Mann–Whitney U test reveals that mduration (call duration in minutes) has the strongest positive relationship with conversion, with a large effect size based on the rank-biserial correlation. Several other numerical features also have statistically significant p-values, but their effect sizes are small.

**3. Do campaign conversion rates vary across economic and demographic factors?**
  - Demographics with minimal debt and housing obligations, as well as students and retirees, demonstrate the highest responsiveness to term deposit offers. Financial background and occupation appear to play key roles in influencing conversion likelihood.

**4. Are longer contact calls more successful?**
  - Call duration reflects conversion intent more than it drives it. Most non-converters hang up within 15 minutes, while converters either commit early or stay engaged beyond that point.
  - These timing patterns make call length a reliable indicator for lead scoring and agent prioritization, helping teams focus on high-intent callers without needing to prolong conversations.

**5. Does repeated contact increase conversions?**
  - Repeated contact clearly enhances conversion performance. While nearly half of conversions occur on the first attempt (48.42%), follow-ups account for the majority (51.58%), demonstrating that persistent outreach is just as crucial as initial engagement. This highlights the strategic value of multi-touch campaigns in maximizing overall effectiveness.

**6. What is the optimal number of contacts before diminishing returns occur?**
  - Most conversions happen within the first five contact attempts, over 95% of total successes. Additional outreach beyond this point yields only small gains (around 4%) but requires a large number of extra calls. By limiting follow-ups to 4–5 touches, the campaign could reduce unnecessary contact by 36%, saving time and resources without meaningfully sacrificing performance.

**7. Which contact channels are most effective?**
  - Cellular and telephone contacts work best, converting over half of customers. The ‘unknown’ contact type performs poorly, only 8% of attempts succeed. Since most conversions take 4–5 tries, focusing on proven channels and cutting back on low-performing ones can save time and improve results.

**8. Are there specific days, weeks, or months with significantly higher conversion rates?**
  - The data shows clear timing patterns in conversion rates across months and days, pointing to potentially high-yield outreach windows. However, since the dataset lacks detail on campaign design, employee involvement, or contact strategies, these trends should be interpreted with caution. Differences in team performance, messaging, or customer targeting could all play a role in the observed outcomes. Still, months like December, March, September, and October, and specific days such as the 1st, 3rd, 10th, and 25th, appear to align with higher success rates, suggesting useful benchmarks for future testing and optimization.


## K. Recommendations for Improving the Marketing Campaign
**1. Make the Most of the First Contact**
  - Nearly half of the successful sign-ups happen on the first call.
  - This means it’s critical to target the right people from the beginning. Use customer data and past results to prioritize the most likely responders right away.

**2. Follow Up, But Not Too Much**
  - People often need more than one nudge. In fact, over 50% of conversions happen after the first contact, especially by the 4th or 5th attempt.
  - But calling too many times after that brings little benefit and wastes time. Stop after 5 tries to save resources while keeping results strong.

**3. Pay Attention to Call Duration**
  - If someone stays longer on the phone, it usually means they’re curious or considering the offer.
  - On the flip side, short calls often signal rejection.
  - Follow up quickly with longer-call leads while reducing effort on those who hang up early.

**4. Focus on the Right Groups**
  - Retired people and students are more likely to accept the offer, probably because they’re less busy and more open to having a conversation.
  - Create custom messages and special strategies for these groups to improve results even further.

**5. Choose the Right Timing – But Test Before You Trust It**
  - The data shows that certain months (like March, September, December) and specific days (1st, 3rd, 10th, 25th) had better conversion rates than others.
  - However, the dataset does not reveal how each campaign was conducted, such as who made the call, the tone of the messaging, or which types of customers were contacted. These missing factors may have influenced conversions and should be taken into account when interpreting the results.
  - So while these timing patterns are interesting, they should be treated as starting points for A/B testing, not fixed rules.

**6. Use the Best Contact Channels**
  - Mobile and telephone calls are the most effective. They lead to over 50% of sign-ups.
  - Avoid or fix channels that show poor results (like the “unknown” type) to save effort and improve results.

**7. Score and Prioritize Your Leads**
  - Use what you know, like how long someone stays on the phone, their job, or whether they’ve said "yes" before, to rank leads by potential.
  - Focus your team’s time and budget on those with higher chances of converting.

**8. Avoid Being Too Pushy**
  - Be careful not to annoy potential customers with too many calls.
  - If someone clearly isn’t interested after a few contacts, let them go.
  - This not only protects your brand image, it also respects your audience’s time.
