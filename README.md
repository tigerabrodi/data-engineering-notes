# Introduction

Data engineering is like being a master organizer for digital information. It involves taking a lot of raw, unsorted data and turning it into organized, useful information. This process is important because it makes the data easy to understand and ready for use in various applications, from business decision-making to powering smart technologies.

Data engineers build systems to do this efficiently. They ensure the data is safe, well-managed and neatly organized.

Think of them as the experts who turn a chaotic pile of data into a well-ordered library, where everything is easy to find and use for analysis or in advanced technologies like machine learning.

# Core Data Sets

In data engineering, a core data set is like a detailed record of all the actions and transactions that occur within a company's applications.

1. **User-Friendly Design**: Core data sets are organized to be easily understandable, even for those with less technical expertise. This involves clear naming conventions and structuring the data so it's straightforward to use for analysis.

2. **Tracking Changes Over Time**: These data sets are designed to record how information changes. For example, if a customer changes their address, the data set keeps both the new and the old address, marking the time of change. This way, one can see historical data trends and changes.

3. **Integration from Multiple Sources**: Data engineers combine data from various sources into a core data set. They use unique identifiers to link different pieces of information, making it easier to merge and analyze data from diverse systems. This integration allows for comprehensive analysis across multiple aspects of the business without complex and error-prone manual linking.

# ETL/ELT

In data engineering, a big part of the job is about moving data from one place to another, like transporting goods from a warehouse to a store. This is done through something called data pipelines, which can be of two main types: Extract, Transform, Load (ETL) and Extract, Load, Transform (ELT).

1. **Extract (E)**: This is the first step where data engineers collect data from different sources. These sources can be anything like a website's data, customer information systems, or even social media statistics. The idea is to gather all this raw data so it can be organized and made useful.

2. **Transform (T)**: Once the data is collected, it needs to be cleaned and organized. This could mean changing the format of dates so they're all the same, removing duplicate information, or grouping related data together. This step makes sure that the data is consistent and ready for analysis.

3. **Load (L)**: The final step is to put this organized data into a place where it can be accessed and used, like a data warehouse. This is like stocking the shelves of a store with products ready for customers (in this case, data analysts and scientists) to use.

Sometimes, the order of these steps might change (that's where ELT comes in), but the goal remains the same.

## When to use ELT?

This approach is becoming more popular because it allows for more flexibility in the data analysis process. For example, if a company wants to analyze data from a new source, they can simply add it to the data warehouse and then transform it later. This saves time and effort, as the data doesn't need to be transformed until it's actually needed.

You can transform the data as needed for different purposes without having to preprocess it each time.

ELT is often preferred for real-time data processing. Since the transformation occurs after loading, it allows for quicker access to the latest data.

It's easier now with modern data warehouses that can handle large amounts of data and have the computing power to transform it quickly. This means that the data can be transformed in the warehouse itself, rather than having to do it before loading it in.

# OLTP

Online Transaction Processing (OLTP) is like a cashier at a store. It's designed to handle lots of individual, small transactions quickly and efficiently. Each transaction is like a customer buying a single item. OLTP systems are great for this because they're built to be fast and reliable for each small transaction. Examples include processing a payment or updating a customer's address.

# OLAP

Online Analytical Processing (OLAP) is like a manager analyzing the store's sales data at the end of the month. It's designed for analyzing and querying large amounts of data. OLAP systems are used for complex calculations, data discovery, and providing insights from large datasets. They're not about speed per transaction but about deep analysis over a broader range of data.

# OLTP vs OLAP

1. **OLTP Data Modeling Issues for Analytics**: In OLTP, data models are great for single transactions but not for analytics. When data analysts want to find specific information, they often have to link (or "join") many small pieces of data together. This is like having to open many drawers to find all the parts of one product. Also, these models aren't the best for analyzing huge amounts of data (like billions of rows) because they're too detailed and structured in a complex way.

2. **OLAP Data Modeling Solutions**: Data engineering steps in to transform these detailed OLTP data models into something more suitable for analytics. This involves:
   - **Tracking Historical Data**: Like keeping a record of all price changes of a product over time.
   - **Improving Analytical Performance**: Making sure that analyzing large sets of data is fast and efficient.
   - **Simplifying Data Models**: Changing the complex OLTP model into a simpler format that's easier for analysis. This might involve organizing the data into fewer, larger categories, which is easier to work with for big-picture analysis.

**Common OLAP Data Models**: The simplified data models often used in OLAP are called snowflake, star, activity, or OBT schemas. These models are like taking a complex puzzle and rearranging it so that it's easier to see the whole picture at once.

# Data Integrity checks

1. **Null Checks**: These are used to see how much of the data in a column is missing (null). If there's too much missing data, it could be a sign of a problem.

2. **Anomaly Checks**: These checks look for unusual changes in the data. For example, if a table suddenly has a lot more rows than usual, it might indicate an issue.

3. **Category Checks**: These ensure that data in specific fields makes sense. For instance, a field for U.S. states should only contain valid state names. If something else shows up, it's flagged as an error.

4. **Uniqueness Check**: This is important to prevent duplicate data. When combining data from different sources, it's crucial to ensure that the same information isn't counted twice.

5. **Aggregate Checks**: These checks are about the big picture – they look at overall totals and counts to make sure nothing major is missing or incorrectly added after all the data processing is done.

# Batch Processing and Streaming

**Batch Processing**: This is like setting up a regular schedule for handling data. Imagine a bus that leaves every hour or once a day, carrying all the data collected up to that point. In batch processing, data is collected over a period (an hour, a day, etc.) and then processed all at once according to a set schedule. It's useful when real-time data updating isn't critical. For example, if you only need daily reports on sales data, batch processing is efficient and straightforward.

**Streaming**: This is like a continuous flow of data, similar to a live broadcast. In streaming, data is processed immediately as it arrives. It’s like having a continuous conveyor belt that constantly brings in and processes data. This method is essential for situations where you need to react to data in real-time, like monitoring live user interactions on a website. Streaming is more complex and requires more resources but provides up-to-the-minute data processing.

**Choosing Between Them**: The decision on whether to use batch processing or streaming depends on your needs. If your data doesn't need to be up-to-the-minute and is used for periodic reports, batch processing is suitable. But if you require immediate data analysis, like for instant decision-making or real-time user interaction, streaming is the way to go. It's all about how quickly you need to process and use your data.
