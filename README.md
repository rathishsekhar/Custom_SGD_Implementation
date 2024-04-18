# Custom_SGD_Implementation README

Project Name: Custom SGD Implementation - Implement SGD Classifier with Logloss and L2 regularization Using SGD without using sklearn

# Table of Contents
1. Overview
2. Prerequisites
3. Project Structure
4. Data
5. Input
6. Model
7. Setup
8. Usage
9. Results
10. Limitations
11. Ethical Considerations
12. Contributing
13. License

# Overview

This project is part of the author's custom series where the author attempts to implement typical machine learning libraries which are used in day to day machine learning tasks. The current project is centered around the implementation of a custom Stoichastic Gradient Descent(SGD) classifier algorithm with logloss and L2 regularization.

The aim is to gain a deeper understanding of SGD classifier algorithm and how it works behind the scenes, particularly when compared to the widely used `scikit-learn` models i.e. the sklearn.linear_model.SGDClassifier library. We aim to strengthen our understanding of the following aspects:

1. Define logloss with L2 regularization functions for SGD classifier mathematically (refer to the README.md document)
2. Write the code for the SGD classifier and train the randomly generated data. 
3. Compare the results with sklearn.linear_modle.SGDClassifier. 

By undertaking this project, we aim to enhance our knowledge of internal workings of the algorithms so as to contribute to our proficiency in machine learning and data science.

# Prerequisites

Python 3.6 or later preferably
Jupyter Notebook
Libraries listed in requirements.txt

# Project Structure

The project structure is organized as follows: \
├──data \
├── notebooks \
│─├── CustomSGD.ipynb \
│─├── README.md
├── README.md \
├── requirements.txt \
└── LICENSE \


# Data

No external data is used. A custom classification dataset is generated using sklearn.datasets.make_classification function. The users are free to experiment with different sets of data by adjusting various arguments 
A gentle reminder that the author takes data privacy and security seriously and handle all data requests with utmost care and compliance with relevant regulations.

# Input
No external input data is used as the custom data is generated as required within the file. 

# Model
1. Stoichastic Gradient Descent Classifier


# Setup

1. Clone this repository to your local machine:
git clone https://github.com/yourusername/Custom_SGD_Implementation.git

2. Navigate to the project directory:
cd Custom_SGD_Implementation

3. Install the required Python packages:
pip3 install -r requirements.txt

# Usage

For exploring the tasks, refer to the jupyter notebook - notebooks/CountVectorizer.ipynb

# Ethical Considerations


This project strictly adheres to ethical guidelines and practices:

1. **No User Data Used:** We want to emphasize that no user data has been used in the development or testing of this project. We are committed to safeguarding user privacy and ensuring that any data used is anonymized and ethically sourced.

2. **For Learning Purposes:** This project is created solely for educational purposes. Our primary goal is to provide a resource for learning and understanding the inner workings of SGD Classifier. We encourage responsible and ethical use of this knowledge in real-world applications.

3. **Transparency:** We are dedicated to transparency in our project's goals and functionality. We encourage open discussion and feedback to ensure that our project aligns with ethical best practices.

We welcome collaboration and contributions from the community to help improve this project's ethical stance and effectiveness.

# Results

The project achieved the following results: 
1. Various functions contributing to the SGD classifier have been defined and well-written.
2. Logistic regression has been implemented using randomly generated classification data.
3. The custom implementation has been compared with SGDClassifier from scikit-learn library, ensuring that their weights and intercepts are as close as possible, with differences typically in the order of 10^-2.

# Limitations
Here are the key limitations so far identified with the project. By providing the limitations, we want to provide valuable insights: 
1. **Data Quality**: The project relies on randomly generated data for demonstration purposes. Users are therefroe encourated to replace this data with their own to obtain the results. The quality or the results will depend on the input data provided.

2. **Scalability**: The code has been optimized for small to medium-sized datasets. When working with significantly larger datasets, users may encounter performnce bottlenects and therefore, scalling the project would require additional code optimization and resource allocation. 

3. **No Guarantees of Futrue Development**: The extent of future development is dependant on the availability of the time. 

4. **Dependency on third party libraires**: The project evaluation is dependant on the sklearn's module. Users should keep up to date and possibly modify the code as these libraries change. 

5. **Lack of official supoprt and official documentation**: This project is a practice project and therefore the documentation may be outdated or sometimes may lack all the information. In this case please feel free to send an email to the above mentioned email(refer data section).  Also, there is no official supprot provided for this project. 

# Ethical Considerations
1. **No user identifiable data** is used in this project.
2. **Usage**: This project is for educational purposes both for the author and its users to understand various concepts surrounding the SGD Classifier. Hence, no part of the code is to be used for any other purposes without adherance to ethical and legal guidelines of the general software development community. 

# Maintainance and Updates

This project is a result of continuous learning and improvement. As the author is in a learning stage, updates to the code and documentation will be made whenever time permits.

We take pride in maintaining a comprehensive README.md document to provide users and contributors with clear instructions and insights into the project. Our goal is to make it as accessible and informative as possible.

At present, there are no further enhancements planned for the project, but the author considers implementing SGD classification with L1 regularization in the future.

Your feedback, suggestions, and contributions are highly valued. If you have ideas, encounter issues, or want to collaborate, please don't hesitate to reach out. Together, we can continue to improve and refine this project.

# Contributions
Contributions to this project are welcome. To contribute:

Fork the repository.
Create a new branch for your feature: git checkout -b feature-name
Make your changes and commit them: git commit -m 'Add feature-name'
Push to your branch: git push origin feature-name
Create a pull request.

# License

This project is licensed under the MIT License. Feel free to use and modify the code as needed.

Feel free to adapt this README template to your specific data science project. It provides a clear structure and information for users and collaborators to understand and contribute to your project effectively