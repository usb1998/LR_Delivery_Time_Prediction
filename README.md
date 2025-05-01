# LR Delivery Time Prediction
## Description
This project focuses on predicting delivery times for orders placed through Porter, a logistics platform. The analysis utilizes a dataset with features such as restaurant location, order details, delivery partner availability, and delivery distance. The project encompasses data preprocessing, feature engineering, exploratory data analysis (EDA), and the development of machine learning models, primarily a Random Forest Regressor, to predict delivery times. The objective is to enhance operational efficiency and customer satisfaction by identifying key factors influencing delivery duration.
The repository includes a detailed report (Delivery_Time_Prediction_Report.pdf) and a Jupyter notebook (LR_Delivery_Time_Estimation_Starter.ipynb) that document the entire data pipeline, model building process, and insights derived from the analysis.
Installation
To set up the project environment and run the code, follow these steps:
# Clone the repository
git clone https://github.com/usb1998/LR_Delivery_Time_Prediction.git

# Navigate to the project directory
cd LR_Delivery_Time_Prediction

# Create a virtual environment (optional but recommended)
python -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate

# Install required dependencies
pip install -r requirements.txt

Requirements
The project requires the following Python libraries, which can be installed via the requirements.txt file:

pandas
numpy
matplotlib
seaborn
scikit-learn
statsmodels
scipy

To generate the requirements.txt file, you can run:
pip freeze > requirements.txt

Usage

Data: Place the dataset (porter_data_1.csv) in the project directory. The dataset should include columns such as market_id, created_at, actual_delivery_time, store_primary_category, order_protocol, total_items, subtotal, num_distinct_items, min_item_price, max_item_price, total_onshift_dashers, total_busy_dashers, total_outstanding_orders, and distance.

Running the Notebook:

Open the Jupyter notebook LR_Delivery_Time_Estimation_Starter.ipynb:jupyter notebook LR_Delivery_Time_Estimation_Starter.ipynb


Execute the cells sequentially to perform data loading, preprocessing, EDA, model training, and evaluation.


Viewing the Report:

The Delivery_Time_Prediction_Report.pdf contains a comprehensive analysis, including visualizations, model performance metrics, and key insights.


Model Training:

The notebook trains a Random Forest Regressor with Recursive Feature Elimination (RFE) to select the most important features.
Key features identified include distance, total_outstanding_orders, and total_onshift_dashers.


Output:

The notebook generates visualizations (e.g., histograms, scatter plots, correlation matrices) and model performance metrics (e.g., Mean Squared Error, Root Mean Squared Error).
Residual plots and feature importance analyses are included to diagnose model performance.



Project Structure
LR_Delivery_Time_Prediction/
│
├── Delivery_Time_Prediction_Report.pdf  # Detailed report with analysis and insights
├── LR_Delivery_Time_Estimation_Starter.ipynb  # Jupyter notebook with code and explanations
├── porter_data_1.csv  # Dataset (not included in repo; add your own)
├── requirements.txt  # List of required Python libraries
└── README.md  # This file

Key Insights

Distance is the most significant predictor of delivery time, with longer distances strongly associated with increased delivery duration.
Delivery partner availability (e.g., total_onshift_dashers, total_busy_dashers) has a subtle impact, suggesting that optimizing partner allocation could reduce delays.
Temporal features (e.g., order_hour, isWeekend) reveal peak periods, useful for scheduling.
Multicollinearity between total_busy_dashers and total_onshift_dashers suggests potential feature reduction or regularization.
The Random Forest model outperforms Linear Regression and Decision Tree models, achieving a Root Mean Squared Error (RMSE) of approximately 1.92 minutes with 8 selected features.

Contributing
Contributions are welcome! To contribute:

Fork the repository.
Create a feature branch (git checkout -b feature/YourFeature).
Commit your changes (git commit -m 'Add YourFeature').
Push to the branch (git push origin feature/YourFeature).
Open a pull request.

Please ensure your code follows the project's coding style and includes appropriate documentation.
License
This project is licensed under the MIT License. See the LICENSE file for details.
Contact
For questions or feedback, please contact:

Umair Sultan Birajdar
Email: umairbirajdar18@gmail.com
GitHub: usb1998

Project Link: https://github.com/usb1998/LR_Delivery_Time_Prediction
