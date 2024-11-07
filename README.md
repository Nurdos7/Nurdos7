import streamlit as st

def calculate_monthly_payment(loan_amount, annual_interest_rate=0.10, loan_term_years=5):
    monthly_interest_rate = annual_interest_rate / 12
    n = loan_term_years * 12
    monthly_payment = loan_amount * (monthly_interest_rate * (1 + monthly_interest_rate)  n) / ((1 + monthly_interest_rate)  n - 1)
    return monthly_payment

st.title("Несиені өтеу жоспарын есептеу")
loan_amount = st.number_input("Несиенің бастапқы сомасын енгізіңіз (теңге):", min_value=0.0)

if st.button("Есептеу"):
    monthly_payment = calculate_monthly_payment(loan_amount)
    st.write(f"Ай сайынғы төлем мөлшері: {monthly_payment:.2f} теңге")
