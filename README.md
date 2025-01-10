import streamlit as st
import pandas as pd

# Load data unsur (misalnya dari file CSV)
df = pd.read_csv('data/elements.csv')

# Fungsi untuk mencari unsur berdasarkan simbol
def search_element(symbol):
    return df[df['symbol'] == symbol]

# Judul aplikasi
st.title("Tabel Periodik Sederhana")

# Input untuk mencari unsur
symbol = st.text_input("Masukkan simbol unsur:")

# Tampilkan hasil pencarian
if symbol:
    result = search_element(symbol)
    if not result.empty:
        st.write(result)
    else:
        st.write("Unsur tidak ditemukan.")
