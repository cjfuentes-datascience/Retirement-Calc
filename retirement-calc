import streamlit as st

def calculate_years_to_reach_target(salary, contribution_rate, annual_raise, target_investment, average_return):
    current_savings = 0
    years = 0
    while current_savings < target_investment:
        annual_contribution = salary * (contribution_rate / 100)  # Convert to decimal
        current_savings += annual_contribution
        current_savings *= (1 + average_return)
        salary *= (1 + (annual_raise / 100))  # Convert to decimal
        years += 1
    return years

# Streamlit application layout
st.title('401(k) Investment Goal Calculator')

# User input
salary = st.number_input('Enter your annual salary:', min_value=0, value=62500)
contribution_rate = st.number_input('Enter the percentage of salary to contribute to 401(k):', 0, 100, 7)
annual_raise = st.number_input('Enter your expected annual salary raise percentage:', 0, 100, 3)
target_investment = st.number_input('Enter your target investment amount:', min_value=0, value=1000000)
average_return = 0.07  # Keep as decimal since it's a constant

# Calculate button
if st.button('Calculate'):
    years = calculate_years_to_reach_target(salary, contribution_rate, annual_raise, target_investment, average_return)
    st.write(f'Years needed to reach the target: {years}')

# Running the Streamlit app
# To run this app, use the following command in your terminal:
# streamlit run investment_calculator.py
