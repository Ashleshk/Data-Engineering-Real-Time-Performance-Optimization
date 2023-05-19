### Data-Engineering: 

# Real-Time Performance Optimization for Manufacturing Company

Real-Time Performance Optimization Project with complete streaming data pipeline including acquisition, storage, enrichment, analysis and visualization

- **Credit**: Special thanks to **AWS** & **Thoughtworks** to conduct "Data-Driven Everything(D2E) Workshop in Chicago". Thank you all for this amazing workshop.

- **Source**: [AWS Catalog Workshop](https://catalog.workshops.aws/event/dashboard/en-US/workshop#data-strategy:-real-time-performance-optimization)

### Project Objective 

AnyCompany Manufacturing is looking to become a world class manufacturing company. To achieve this all machines within the factory should operate at a 85% or higher Overall Operating Efficiency to be considered world class. AnyCompany manufacturing has found that they are are close to this operating target but suspect there are operators of the machine that need improvement.

You as Analyst need to investigate this and work backwards to solve the problem of having a low operational effectiveness efficiency. You will ultimately build a real-time data pipeline resulting in machine insights and visualizations for factory effectiveness.

### AWS Services used
- Amazon Simple Storage Service
- AWS Glue
- Amazon Kinesis
- AWS Lambda
- Amazon Simple Notification Service (SNS)
- Amazon QuickSight
- AWS Identity and Access Management
- AWS Redshift Serverless
- Amazon Sagemaker

### Proposed Solution

![Architecture diagram](https://github.com/Ashleshk/Data-Engineering-Real-Time-Performance-Optimization-for-Manufacturing-Company/blob/main/Solution%20Architecture.png)


### Question & Insight

1. **Question - How can we visualize the operating parameters for each machine in the factory?** 

**Answer** : Yes, By selecting any data point in the Line Chart, say LO1, Machine 5, this value of the line field for data point is applied as a filter to the box plot visual operated during this time period with wider parameter settings. 
    - We also see that the median settings during the time period for Machine 5 were drastically different from the other machines.


2. **Question - Which Machine was most Defective, which operator was responsible?**

**Answer** : **Line 1 Machine 5** was most defective among others for frequent period of time.
    - John Doe worked mostly on this machine and Overall, he was responsible for many more defects (count: **4681.46**) than his colleagues. concluded from machine view below.
    - Based on this, **We can recommended that John receives more training to reduce the overall amount of defects**.


### Data preparation 

![Data prepartion](https://github.com/Ashleshk/Data-Engineering-Real-Time-Performance-Optimization-for-Manufacturing-Company/blob/main/Data%20Preparation.png)


### Visualization 

1. **Factory View Dashboard**
![Factory View Dashboard](https://github.com/Ashleshk/Data-Engineering-Real-Time-Performance-Optimization-for-Manufacturing-Company/blob/main/Factory%20View.png)

2. **Machine View Dashboard**

![Machine View Dashboard](https://github.com/Ashleshk/Data-Engineering-Real-Time-Performance-Optimization-for-Manufacturing-Company/blob/main/Machine%20View.png)