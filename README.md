# Call_Center_Analysis
A comprehensive analysis of call center performance driven by data, focusing on agent productivity, call outcomes, and customer satisfaction metrics. This project leverages Power BI to deliver insights for enhancing call management, minimizing missed and abandoned calls, and optimizing staffing strategies to improve customer service.

## Call Analysis
![image](https://github.com/user-attachments/assets/7b54ac33-14f5-4406-ab2b-4a033db9aec7)


## Agent Analysis
![image](https://github.com/user-attachments/assets/978bc38e-b15d-4a19-a7c4-f19f7a7f0708)


## Background
Call centers are crucial for maintaining customer relationships, but managing agent performance, call efficiency, and customer satisfaction can be challenging without data insights. As call volumes and customer demands grow, a data-driven approach is essential for identifying inefficiencies and making informed decisions. This project uses data analysis to uncover actionable insights that enhance call handling, improve agent productivity, and boost customer satisfaction.

## Project Objectives
- Assess agent performance by analyzing call resolution rates, speed of answering, and customer satisfaction.
- Understand customer behavior patterns such as call volume by time and day.
- Identify key trends in different call topics and resolution success.
- Provide recommendations to improve call center efficiency and customer satisfaction.

## Technical Stacks
- **Data Visualization Tool**: Power BI
- **Data Source**: CSV containing YouTube channel data

## Data Understanding
The dataset contains 5000 call conversations and consists of the following features:
- **Call ID**: Unique identifier for each call.
- **Agent**: The name of the agent handling the call.
- **Date and Time**: The date and time when the call was received.
- **Topic**: The nature of the call (e.g., Technical Support, Payment, Contract-related).
- **Answered**: Whether the call was answered.
- **Resolved**: Whether the call was successfully resolved.
- **Speed of Answer (seconds)**: Time taken by the agent to answer the call.
- **Average Talk Duration**: The average duration of the conversation.
- **Satisfaction Rating**: Customer satisfaction rating out of 5.

## Data Preprocessing
- **Remove Empty Columns and Rows**: Identify and remove any empty columns and rows.
- **Remove Duplicates**: Deduplication of data to avoid redundancy.
- **Rename Columns**: Ensure appropriate names are used for better analysis.
- **Change Data Types**: Ensure columns have appropriate data types (e.g., dates, numbers, text).
- **Handle null values**: Replaced null values with “Not Available”
- **Standardize Values**: Replaced and formatted values to maintain data consistency.

## Data Modelling
- Data Formatting
- Generate Hierarchies
- DAX

## DAX
### Calculated Measures
- Average Satisfaction Rating = AVERAGE('Call Conversation'[Satisfaction rating])
- Avg Speed of Answer = AVERAGE('Call Conversation'[Speed of answer (sec)])
- Max Rating = MAX('Call Conversation'[Satisfaction rating])
- Target = 4.5
- Total Calls = count('Call Conversation'[Call Id])
- Total Calls Abandoned = CALCULATE(COUNT('Call Conversation'[Answered]), 'Call Conversation'[Answered]="No")
- Total Calls Answered = CALCULATE(COUNT('Call Conversation'[Answered]), 'Call Conversation'[Answered]="Yes")
- Total Calls Resolved = CALCULATE(COUNT('Call Conversation'[Resolved]), 'Call Conversation'[Resolved]="Yes")

### Calculated Columns
  - Hour = hour('Call Conversation'[Call Time])

## Report Visualization
### Agent Analysis
#### Total Agents
  - The call center operates with 8 agents. Performance variations are noticeable among these agents.

#### Most Issues Resolved
  - Jim is the top performer in terms of the number of issues resolved, indicating high efficiency. This suggests that Jim might have either handled easier queries or possesses strong problem-solving skills.

#### Most Calls Missed
  - Diane has missed the most calls, which is concerning because missed calls impact both customer satisfaction and overall operational efficiency. A deeper investigation into why Diane is missing so many calls       could provide insights for improvements.

#### Highest Satisfaction Rating
  - Martha has the highest average satisfaction rating of 3.47, indicating that the quality of her service is perceived positively by customers. However, the average satisfaction score across all agents (3.40)        shows room for improvement overall.

#### Quickest to Answer
  - Becky is the fastest to answer calls, with an average speed of 65.33 seconds. This is a strong metric, as faster response times are generally correlated with higher customer satisfaction. However, Becky’s         satisfaction rating (3.37) is lower than Martha’s, suggesting speed isn’t the only factor affecting customer satisfaction.

#### Count of Issues Resolved
  - The bar chart shows the number of resolved and unresolved issues for each agent. Jim (485 resolved) and Diane (452 resolved) handled a high volume of calls, but Diane’s high missed calls and unresolved            issues are a concern. Greg (455 resolved) and Martha (461 resolved) also show good performance in resolving issues, but Greg has room for improvement in terms of satisfaction ratings.

#### Average Speed of Answer by Agent
  - The trend chart indicates that while Becky and Stewart are quicker to answer, agents like Joe and Martha take significantly longer (above 68 seconds). A balance between speed and quality of service is             needed, as speed alone doesn’t necessarily lead to high customer satisfaction.

#### Average Satisfaction Rating by Agent
  - Satisfaction scores range from 3.33 (Joe) to 3.47 (Martha). While no agent has an extremely high score, the small differences suggest that improving service quality slightly across the board could have a          noticeable effect on overall satisfaction.

### Call Analysis
#### Total Calls, Answered Calls, Resolved Calls
  -  The call center handled 5,000 calls, out of which 946 calls were abandoned (18.92% abandonment rate). This is relatively high and could indicate long wait times or insufficient staffing. Of the 4,054             answered calls, only 72.92% were resolved, showing room for improving resolution rates.
  
#### Total Calls by Weekday
  - Calls peak on Mondays (770) and Saturdays (768), with the lowest volume on Wednesdays (675). This trend indicates that staffing should be optimized to handle the higher volumes on these days, particularly on weekends when support needs may rise.

#### Total Calls by Topic
  - The most common call topics are Streaming (1,022 calls), Technical Support (1,019 calls), and Payment Related (1,007 calls). This indicates a high demand for technical and service-related support. Contract and administrative support are also significant but slightly less frequent.

#### Total Calls by Month
  - There is a declining trend in the total number of calls from January (1,772) to March (1,612). This may suggest seasonality or that some issues were resolved after the new year, reducing call volumes. A more     detailed investigation into this decline could reveal underlying reasons (e.g., improved self-service options, reduced service issues).

#### Total Calls by Hour
  - The number of calls is consistently high between 9 AM and 5 PM, with the peak hour being around 9 AM (547 calls). Only 14 calls are received after 6 PM, suggesting that after-hours support may not be a critical requirement. However, staffing should be focused on the 9 AM to 5 PM window, particularly in the mornings.

#### Resolved Calls
  - The resolution rate is under 75%, meaning over 25% of calls are either unresolved or abandoned. This indicates a need for improvements in training or system efficiency to increase this rate.

#### Average Satisfaction Rating
  - The average satisfaction rating shows that the call center’s service is generally rated as satisfactory but not exceptional.

## Agent Analysis Recommendations
- **Reduce Missed Calls** : Investigate Diane’s high missed calls and adjust her workload or provide technical support to improve performance.
- **Balance Speed and Quality** : Becky is fast but could improve satisfaction. Focus on delivering quality service alongside speed.
- **Improve Customer Satisfaction** : Increase satisfaction scores through regular feedback, training, and best practices from top performers like Martha.
- **Enhance Call Resolution Skills** : Provide training to agents like Greg and Stewart to boost problem-solving and resolution rates.
- **Support Slower Agents** : Offer training or tools to agents with slower response times to balance speed and service quality.

## Call Analysis Recommendations
- **Optimize Peak-Time Staffing** : Adjust staffing during peak hours (9 AM - 5 PM, especially Monday and Saturday) to reduce missed and abandoned calls.
- **Improve Call Resolution** : Focus training on common issues (technical support and streaming) to resolve more calls on the first interaction.
- **Reduce Call Abandonment** : Implement callback options and investigate long wait times to reduce abandoned calls.
- **Expand Self-Service Options** : Offer more online resources for frequent issues (streaming and technical support) to lower call volume.
- **Monitor Monthly Call Trends** : Regularly assess seasonal call fluctuations to optimize resources and staffing.

## Future Scope
- Perform further sentiment analysis on customer feedback to identify specific areas for improvement.
- Implement predictive modeling to forecast call volume and optimize staffing during peak times.
- Explore the impact of different call topics on resolution success and customer satisfaction.

