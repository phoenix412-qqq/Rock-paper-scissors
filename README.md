

# Создаем главное окно
window = tk.Tk()
window.title("Камень, ножницы, бумага")

# Устанавливаем размер окна
window.geometry("800x800") 

# Задаем фон окна
window.configure(bg="#4D4D4D") # Темно-серый фон

# Запрещаем изменение размера окна
window.resizable(False, False) 

# Инициализируем счет
user_score = 0
comp_score = 0

# Создаем метки
user_label = tk.Label(window, text="Выберите:", font=("Arial", 16), bg="#4D4D4D", fg="#FFFFFF") # Прозрачный фон
user_label.pack(pady=10)

# Создаем фрейм для кнопок
button_frame = tk.Frame(window, bg="#4D4D4D") 
button_frame.pack(pady=10)

# Создаем кнопки для выбора (увеличенный размер)
rock_button = tk.Button(button_frame, text="Камень", command=lambda: get_user_choice("камень"), width=15, height=3, bg="#1E90FF", fg="#4D4D4D")
rock_button.pack(side="left", padx=10)

paper_button = tk.Button(button_frame, text="Бумага", command=lambda: get_user_choice("бумага"), width=15, height=3, bg="#1E90FF", fg="#4D4D4D")
paper_button.pack(side="left", padx=10)

scissors_button = tk.Button(button_frame, text="Ножницы", command=lambda: get_user_choice("ножницы"), width=15, height=3, bg="#1E90FF", fg="#4D4D4D")
scissors_button.pack(side="left", padx=10)

# Создаем метки для вывода результатов
comp_label = tk.Label(window, text="", font=("Arial", 35), bg="#4D4D4D", fg="#FFFFFF") # Прозрачный фон
comp_label.pack(pady=10)

result_label = tk.Label(window, text="", font=("Arial", 35), bg="#4D4D4D", fg="#FFFFFF") # Прозрачный фон
result_label.pack(pady=10)

# Создаем метку для отображения счета
score_label = tk.Label(window, text=f"Счет: Вы - {user_score}, Компьютер - {comp_score}", font=("Arial", 14), bg="#4D4D4D", fg="#FFFFFF") # Прозрачный фон
score_label.pack(pady=5)

# Создаем кнопку для определения победителя
play_button = tk.Button(window, text="Играть🧱✂📃", command=determine_winner, width=25, height=6, bg="#FFFAF0", fg="#4D4D4D") 
play_button.pack(pady=10)

# Запускаем главное окно
window.mainloop()
