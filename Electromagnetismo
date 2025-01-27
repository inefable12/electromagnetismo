import streamlit as st
import random

def generate_exercise():
    exercises = [
        {
            "question": "Una carga de {q} C está en un campo eléctrico de {e} N/C. ¿Cuál es la fuerza ejercida sobre la carga?",
            "data": lambda: (round(random.uniform(1, 10), 2), round(random.uniform(100, 500), 2)),
            "solution": lambda q, e: round(q * e, 2),
            "unit": "N"
        },
        {
            "question": "Una corriente de {i} A fluye por un conductor de {l} m dentro de un campo magnético de {b} T perpendicular al conductor. ¿Cuál es la fuerza magnética sobre el conductor?",
            "data": lambda: (round(random.uniform(0.5, 5), 2), round(random.uniform(1, 3), 2), round(random.uniform(0.1, 0.5), 2)),
            "solution": lambda i, l, b: round(i * l * b, 2),
            "unit": "N"
        },
        {
            "question": "Una bobina con {n} vueltas y un área de {a} m^2 se encuentra en un campo magnético de {b} T. Si el flujo magnético cambia en {t} segundos, ¿cuál es la fem inducida?",
            "data": lambda: (random.randint(10, 100), round(random.uniform(0.01, 0.1), 4), round(random.uniform(0.1, 1), 2), round(random.uniform(1, 5), 2)),
            "solution": lambda n, a, b, t: round((n * a * b) / t, 2),
            "unit": "V"
        }
    ]

    exercise = random.choice(exercises)
    values = exercise["data"]()
    question = exercise["question"].format(*values)
    solution = exercise["solution"](*values)
    return question, solution, exercise["unit"]

st.title("Ejercicios de Electromagnetismo")

st.write("Haz clic en el botón para generar un ejercicio aleatorio de electromagnetismo.")

if st.button("Generar Ejercicio"):
    question, solution, unit = generate_exercise()
    st.write(f"### Ejercicio: {question}")

    if st.button("Mostrar Respuesta"):
        st.write(f"**Respuesta:** {solution} {unit}")
