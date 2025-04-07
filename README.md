# growthmindset2nd
 import streamlit as st
import random

st.title("Number Guessing Game")
st.write("Guess the number between 1 and 100!")

if "number" not in st.session_state:
    st.session_state.number = random.randint(1, 100)

guess = st.number_input("Your guess:", 1, 100, step=1)

if st.button("Submit"):
    if guess == st.session_state.number:
        st.success("Correct! Starting a new game.")
        st.session_state.number = random.randint(1, 100)
    else:
        st.warning("Too low!" if guess < st.session_state.number else "Too high!")
