# PROJECT_IMPACT_LENSE
Reflecting on political campaigns via Facebook &amp; Instagram Ads in the light of the upcoming super election year 2024
In the complex realm of German politics, the strategic integration of Instagram and Facebook has emerged as a powerful catalyst for political campaigns. Leveraging the widespread popularity of these social media platforms, political entities in Germany have harnessed the visual appeal of Instagram and the expansive reach of Facebook to engage with a diverse and tech-savvy electorate.

These platforms serve as dynamic canvases for political messaging, enabling parties and candidates to communicate their ideologies, connect with constituents on a personal level, and navigate the intricate landscape of public opinion. The strategic use of these social media channels might have significantly influenced voter outreach and public perception, reshaping the dynamics of political communication in the country.

This analysis served the purpose of leveraging campaign data from 2019 until 2023 for the 6 main German parties. In that regard, we extracted the Meta campaigns as CSV files from the CDU_CSU, SPD, GRÜNE, FDP, AfD, LINKE. We had already assumed that the spending and strategies vary from a party compared to the others - for example, SPD and CDU have the biggest budgets, as they pay on average 400-500 euros per ad, compared to an average of 100-200 euros per post on social media for the others.

More specifically, we wanted to drive more awareness to the public, and dove into:

- A qualitative analysis: where are they advertising, how are the ads geographically distributed per State, what is the ad spend?
- A segment analysis or sentiment analysis: determination of the purpose of the posts through clusters (using e.g google API, chat GPT, hugging face). Can we find out how often a word or another is being used, or build a word cloud?

### Hypothesis 💪

- HYPOTHESE 1
    - Volume of paid social media ads on Instagram and Facebook significantly increased shortly before elections. **#timing**
- HYPOTHESE 2
    - Ads with copy (text body) that trigger human emotions perform better. We therefore assume that parties engaging in rather polemic political communication also perform better in terms of ROI **#sentiment**
- HYPOTHESE 3
    - While parties in the center have a more balanced messaging, parties on the edges of the political spectrum tend to have a rather polarizing ad content (leaning towards more extreme positions) **#topical**
- HYPOTHESE 4

Populist parties are better positioned in social media (have a competitive advantage) #algorithm

**#systemic**

### **Tools 🧰**

- Meta Library: social media datasets
- Google Sheets: quick data overview and translation
- Google Docs: documentation
- Github: save the colab notebooks
- Visual Studio Code:
- Google Colab: Machine Learning testing, Data cleaning, plotting
- Google BigQuery: Data cleaning, joins, storage
- Looker: visualization, dashboard

### Conclusions **🎯**

1. Money matters but so do other factors such as fresh content
2. Polarising content wins
3. DIE LINKE and theAfD have the biggest bang for the buck
