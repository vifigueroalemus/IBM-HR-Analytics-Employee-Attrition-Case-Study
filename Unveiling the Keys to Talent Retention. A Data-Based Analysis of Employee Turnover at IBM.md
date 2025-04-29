# Unveiling the Keys to Talent Retention: A Data-Based Analysis of Employee Turnover at IBM

Author: Vicente Figueroa Lemus

## 1. Introduction

One of my main drivers as a Psychologist specialized in People Analytics is to explore how data can illuminate and optimize the complex dynamics of organizations, not by chance or in an unknown manner: but by glimpsing and shedding light on the relationships between people; seeking connections between emotional and social factors with their effects on job performance, or on the different aspects that involve work (turnover, absenteeism, engagement, overtime, cost reduction, leaves, etc.).

In particular, talent management and employee retention have become central focuses of my professional interest. In today's competitive business environment, the ability to attract and, above all, retain valuable employees is more critical than ever. The costs associated with employee turnover are significant and go far beyond the direct expenses of Recruitment, Selection, and Training. High turnover also implies the loss of valuable organizational, cultural, and social knowledge, decreased team morale, and disruption of work cohesion and productivity. In fact, it is estimated that the cost of replacing an employee can amount to up to twice their annual salary, which underscores the importance of addressing retention as a fundamental strategic priority for any organization. Identifying the factors that drive employees to seek opportunities outside the company is the crucial first step to developing and implementing effective retention strategies.

To dive deeper into these dynamics, I decided to conduct an exploratory analysis using Excel, Power BI, and pandas (Python library), working with the public Kaggle dataset "IBM HR Analytics Employee Attrition & Performance." This dataset is widely used in the People Analytics community and offers a rich source of information to investigate the factors that influence an employee's decision to stay with or leave an organization. The fundamental purpose of this article is to present the key findings derived from my comprehensive analysis of this dataset, with a specific focus on unraveling the factors that have the most significant impact on employee turnover. To conduct this analysis, I used Excel as my primary tool, leveraging its capacity for in-depth analysis and clear visualization of results. The graphs and tables resulting from this analysis have been compiled into a comprehensive visualization report, accessible through a link on GitHub. This project represents a direct connection to my professional aspirations in the field of Organizational Development. It is natural, therefore, that I seek to autonomously conduct as much research as possible, where I can independently and experimentally test my data analysis aptitudes and through experience, grow and learn. OD professionals rely on the ability to analyze data to conduct comprehensive organizational assessments, identify significant trends, and ultimately formulate recommendations based on solid evidence.

## 2. Understanding the Dataset and Analytical Approach

The "IBM HR Analytics Employee Attrition & Performance" dataset offers a detailed view of various aspects related to employees, including demographic data such as age and gender, factors intrinsic to the job such as role, department, and level of job satisfaction, as well as elements related to the employee experience such as tenure with the company, distance from home, and participation in training programs. The dataset consists of 35 columns (variables) and more than 1500 rows. This richness of variables allows for a multifaceted analysis of the factors that may influence an employee's decision to leave the organization. My analytical approach focused on using Excel to conduct a comprehensive analysis of this data. The process began with cleaning and preparing the dataset, addressing any inconsistencies or missing values to ensure the integrity of the results.

*The way I did it was as follows:*


```
import pandas as pd
df = pd.read_csv("HR_Data.csv")
df = df.drop_duplicates()
df["JobSatisfaction"] = df["JobSatisfaction"].clip(0, 4)  # Corrects values outside the range
```


Subsequently, I conducted an exploratory data analysis to identify initial patterns and possible relationships between the different variables. A central aspect of my analysis was the identification of correlations between various employee attributes (variables) and turnover, seeking to determine which factors showed a stronger association with the likelihood of an employee leaving the company.

To visualize these key findings in a clear and accessible way, I used Excel's charting and pivot table capabilities, as well as Power BI. The primary objective of this analytical approach was to discover actionable insights that could provide organizations with a deeper understanding of the factors contributing to employee turnover, thus enabling them to develop more effective strategies to mitigate this phenomenon. The complete visualization report, containing the detailed charts and tables generated during this process, is available on my GitHub repository.

## 3. Key Findings on Employee Turnover

##### 3.1 The Impact of Job Satisfaction:

The data analysis reveals a clear relationship between levels of job satisfaction and employee turnover rates. Employees who reported lower levels of satisfaction with their job showed a significantly higher probability of leaving the company. This finding is natural and underscores the common-sense thinking of giving fundamental importance to job satisfaction as a factor that directly influences an employee's decision to remain with an organization in the long term. On the other hand, I also sought to independently investigate what the literature says about this; in this sense, research conducted by McKinsey (2023) also emphasizes the need for employees to feel valued in their work environment, which is intrinsically linked to their level of satisfaction. There is therefore a strong negative correlation between job satisfaction and employee turnover. When employees do not feel satisfied with various aspects of their employment, such as their responsibilities, work environment, growth opportunities, or relationships with subordinates, they are more prone to seek opportunities in other organizations where they perceive greater fulfillment and well-being. This dynamic aligns with the general understanding that lack of job satisfaction is one of the most common reasons why employees decide to leave their positions. Consequently, organizations should prioritize implementing concrete initiatives aimed at improving this aspect, an important part of the worker's life. These initiatives could include optimizing the work environment to foster collaboration and support, providing clear and attractive opportunities for professional development and growth within the company.

*Table 1: Turnover Rates by Level of Job Satisfaction*

|                         |                  |                            |                    |
| ----------------------- | ---------------- | -------------------------- | ------------------ |
| Job Satisfaction Level  | Number of Employees | Number of Employees Who Left | Turnover Rate (%) |
| 1                       | 284              | 65                         | 22.8              |
| 2                       | 270              | 45                         | 16.6              |
| 3                       | 446              | 74                         | 16.5              |
| 4                       | 470              | 53                         | 11.3              |

##### 3.2 The Role of Work-Life Balance:

The analysis also revealed a significant connection between employees' perception of the balance between their work and personal lives and their turnover rates. Employees who indicated having difficulties achieving a healthy balance between their professional and personal responsibilities showed a greater propensity to leave the company. This finding highlights the growing importance that employees place on the ability to effectively integrate their work and personal lives. In the same vein, McKinsey has also noted that a significant imbalance between work and personal life is a key determining factor in employee turnover decisions (2023). It is for this reason that, based on this research, it can be conclusively said that the balance between work and personal life (or rather, the **imbalance** between work and personal life) constitutes a considerable risk factor for turnover within a company.

Let's explain this last point with the research findings. Employees who feel that their work demands excessively invade their personal and family time are more likely to experience burnout and stress, which in turn can lead them to: 1) seek employment opportunities that offer a better balance between their personal and work life 2) perform worse within the company 3) lose the sense of their work 4) feel frustrated, overwhelmed, depressed, and anxious.

##### 3.3 The Influence of Department and Job Role:

A tremendously interesting aspect was to investigate the different turnover rates among different departments and job roles. These interesting suspicions later turned into valuable findings in the sense that significant variations in the turnover rate were found depending on both the Department to which the worker belonged, as well as their Job Role and monthly salary. For example, it was observed that certain departments, such as Sales and Research and Development, and specific roles, such as Sales Representative and Laboratory Technician, tended to exhibit higher turnover rates compared to other segments of the organization. This finding underscores that employee turnover is not a uniform phenomenon that affects the entire company equally, but can be concentrated in particular areas or roles.

In this sense, understanding which specific areas of the business are experiencing a greater loss of employees is crucial to effectively focus retention efforts, directing resources and interventions where they are most needed and their impact is greatest. The reasons behind these differences in turnover rates could be related to challenges or specific stressors inherent to certain roles or departments. For example, sales roles often involve high pressures and demanding objectives, which could contribute to higher turnover. Similarly, certain departments might have work cultures or team dynamics that influence satisfaction and, therefore, the retention of their employees. Consequently, it is recommended that companies develop customized retention initiatives adapted to the departments and job roles that show higher turnover rates. This specific approach can be more effective than implementing generic retention strategies at the organizational level.

The most important point in relation to this section is not to treat onboarding, employee lifecycle, and retention strategies in a uniform, simplistic, and reductionist manner. It is important to seek the most interesting data, make the most appropriate correlations, and based on these, draw the most pertinent and acute conclusions. If a department with a significantly higher turnover rate than others is detected, then investigate. That is, conduct interviews, ask questions, analyze culture, climate, compensation, tasks, etc., and based on this, design personalized strategies to alleviate existing deficiencies. Be acute and strategic.

*Table 2: Turnover Rates by Department*

|                            |                     |                            |                    |
| -------------------------- | ------------------- | -------------------------- | ------------------ |
| Department                 | Number of Employees | Number of Employees Who Left | Turnover Rate (%) |
| Research and Development   | 961                 | 133                        | 13.8              |
| Sales                      | 446                 | 92                         | 20.6              |
| Human Resources            | 63                  | 12                         | 19.0              |

##### 3.4 The Impact of Tenure and Experience:

The analysis of the relationship between employee tenure (total years of work within the company) and turnover revealed interesting patterns. It was observed that turnover rates tend to be higher among employees who have less tenure in the organization or who are in the initial stages of their professional careers. In fact, turnover during the first year of employment is particularly high. This finding suggests that employees who are relatively new to the company may be more likely to leave if their initial expectations are not met or if they do not perceive a clear path toward growth and professional development within the organization. Along the same lines, McKinsey & Company (2023) has also highlighted that professional development opportunities have a significant impact on employee retention. Consequently, organizations should pay special attention to creating onboarding programs that (truly) help new employees integrate into the company culture, understand their roles and responsibilities, and establish realistic expectations about their future within the company. In the same vein and even more sensitive: it is crucial to provide clear and accessible pathways for professional development, including opportunities for training, mentorship, and advancement within the company.

By investing in the growth of their employees, organizations can significantly improve retention, especially among those who are at the beginning of their careers.

##### 3.5 Other Contributing Factors:

Finally, I want to mention other extremely important factors that were not mentioned in any of the previous sections. For example, a correlation was found between a lower average monthly income and higher turnover rates. This underscores the importance of competitive compensation as a key factor in retaining talent. Employees who feel they are not being fairly compensated for their work are more likely to seek opportunities in other organizations that offer better benefits, especially salary-related ones.

Other factors, such as distance from home, frequency of business trips, and time dedicated to training also showed influence on turnover rates. These findings suggest that an employee's decision to leave a company is usually influenced by multiple factors, all related to work either intrinsically or extrinsically. It is for this reason that, to effectively address them, companies must adopt a holistic strategy and vision of the employee experience, considering a wide variety of determining factors. In this sense, a comprehensive approach to employee retention should include strategies that address job satisfaction, work-life balance, professional development opportunities, compensation, etc.

## 4. Connecting the Findings with Organizational Development

The findings derived from this analysis of employee turnover at IBM have a direct connection and relevance to the field of Organizational Development. The detailed understanding of the "who, when, and why" of employee turnover provides a solid foundation to inform OD interventions designed to strengthen talent retention and promote more robust organizational health. These findings can be strategically used to develop specific initiatives aimed at increasing employee engagement, directly addressing the factors that have been identified as drivers of turnover. Additionally, the information obtained from this analysis can guide the design and refinement of more effective onboarding and training programs, ensuring that new employees successfully integrate into the organization and are involved and have a clear sense from the start. It is relevant to mention the possibility of improvement in performance management processes and the implementation of more constructive and regular feedback systems, which can benefit from these insights, contributing to a greater sense of recognition and development among employees.

Fostering a work environment that is perceived as positive and supportive is another key OD objective that directly aligns with reducing turnover, as employees who feel valued and supported are less likely to seek employment elsewhere.

In essence, this analysis underscores the fundamental role of data-driven decision-making to achieve more effective organizational development. Skills in data analysis have become a core competency for OD professionals, giving them the ability to accurately diagnose organizational problems and measure the real impact of implemented interventions. This is because by thoroughly understanding the data underlying employee turnover, OD professionals can develop more specific and effective solutions, which in turn leads to improvement in both talent retention and the overall performance of the company.

## 5. Conclusion
#### A Commitment to Data-Driven Talent Management

In summary, the analysis conducted has revealed several key factors that significantly influence an employee's decision to leave an organization. Among these, job satisfaction and work-life balance emerge as critical drivers, with a strong negative correlation with turnover rates. Additionally, significant variations in turnover were observed among different departments and job roles, suggesting the need for more specific and personalized retention strategies. On the other hand, employee tenure and experience also play an important role, with potentially higher turnover rates among newer employees and among those who do not perceive growth opportunities within the company.

Finally, other factors such as compensation, distance from home, and business travel also showed an effect on the decision to leave an organization. This analysis underscores the intrinsic value of using data analysis to gain a deep understanding of complex organizational challenges such as employee turnover. As a People Analyst, I must be honest and say that each investigation and project means an opportunity to learn something new, to grow, act autonomously, and train myself as a professional. To leave the stamped work and grow on my own.

*Table 3: Main Determining Factors of Employee Turnover (Summary)*

|                           |                                                                   |                                                                                                                                     |
| ------------------------- | ----------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Determining Factor        | Key Insight                                                       | Possible OD Intervention                                                                                                            |
| Job Satisfaction          | Lower satisfaction is associated with higher turnover.            | Implement satisfaction surveys, address areas for improvement, enhance the work environment and growth opportunities.               |
| Work/Life Balance         | Imbalance is associated with higher turnover.                     | Promote flexible work policies, ensure manageable workloads, foster a culture that respects personal time.                          |
| Department/Job Role       | Turnover rates vary significantly between departments and roles.  | Develop customized retention initiatives for departments and roles with high turnover rates, addressing their specific needs.       |
| Tenure/Experience         | Higher turnover at the beginning of career or without growth opportunities. | Focus on effective onboarding programs, provide clear pathways for professional development and advancement opportunities within the company. |
| Compensation              | Lower income can correlate with higher turnover.                  | Review and compare compensation with market standards, ensure fair and competitive remuneration to retain valuable talent.         |

Annex:

https://www.mckinsey.com/capabilities/people-and-organizational-performance/how-we-help-clients?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/featured-insights/mckinsey-explainers/what-is-talent-management?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/capabilities/people-and-organizational-performance/our-insights/five-fifty-the-data-talent-link?source=post_page-----78989e52c31b---------------------------------------

https://www.mckinsey.com/capabilities/quantumblack/our-insights/using-people-analytics-to-drive-business-performance-a-case-study?source=post_page-----78989e52c31b---------------------------------------#/

https://www.kaggle.com/datasets/pavansubhasht/ibm-hr-analytics-attrition-dataset?source=post_page-----78989e52c31b---------------------------------------

https://github.com/vifigueroalemus/IBM-HR-Analytics-Employee-Attrition-Case-Study/blob/main/IBM%20HR%20Analytics%20Project.%20Visualizations.pdf
