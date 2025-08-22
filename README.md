# Prashansa-message-
My streamlit  prashansa message 
import streamlit as st

def time(user_time):
    user_time = user_time.strip().lower()
    try:
        t, x = user_time.split()
        hour, minute = map(int, t.split(":"))
    except:
        return "Invalid format! Please enter like 6:16 am"

    m = 'Good Morning'
    a = 'Good Afternoon'
    e = 'Good Evening'
    n = 'Good Night'

    if x == "am":
        if 6 <= hour < 12:
            return m
        elif hour == 12 or (0 <= hour < 6):
            return n
        else:
            return "Invalid AM time"
    elif x == "pm":
        if (12 <= hour < 17) or hour == 12:
            return a
        elif 17 <= hour < 21:
            return e
        elif 21 <= hour < 12:
            return n
        else:
            return "Invalid PM time"
    else:
        return "Invalid input (must be am/pm)"

st.title("👋 Personalized Greeting App")

name = st.text_input("What's your name?")
user_time = st.text_input("Enter time (e.g. 6:16 am)")

if st.button("Submit"):
    if name:
        if name.lower() == "shambhavi":
            st.write(f"Hello, Shambhavi!\n{time(user_time)}\nYou're the sweetest person I have ever met.")
        elif name.lower() == "swati":
            st.write(f"Hey Swati!\n{time(user_time)}\nYou are really very kind\nHelpful with a clear heart..\nLove you.")
        elif name.lower() == "sneha":
            st.write(f"Hey Sneha!\n{time(user_time)}\nTum mujhe yeh batao koi itna selfless kaise ho sakta hai\nThink about yourself too bro!!")
        elif name.lower() == "vanshika":
            st.write(f"Hey Vanshika!\n{time(user_time)}\nHope so tumhara mood swing na ho rha ho\nBtw you're so pretty yaar")
        elif name.lower() == "ananya":
            st.write(f"Hey Ananya!\n{time(user_time)}\nTum na natural glow wali ladki ho\nBtw thank you mere liye itna krne ke liye")
        elif name.lower() == "amulya":
            st.write(f"Hi meri ghongi behen\n{time(user_time)}\nKuch nhi bas ye kehna tha ki\naise hi naye naye branded\nproducts liye krte raha kro..\nAacha lgta hai")
        else:
            st.write(f"Hello Miss\n{time(user_time)}\nHope you doing well")
    else:
        st.warning("Please enter your name.")
