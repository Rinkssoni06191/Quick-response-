Yeh raha updated code jo GK, Math aur Science ke prashn shaamil karta hai:

```
import tkinter as tk
from tkinter import messagebox
import random

class QuizApp:
    def __init__(self):
        self.window = (link unavailable)()
        self.window.title("Quiz App")
        self.window.geometry("400x300")

        self.questions = [
            {"question": "What is the capital of India?", "options": ["Delhi", "Mumbai", "Kolkata", "Chennai"], "answer": 0, "category": "GK"},
            {"question": "What is the largest planet in our solar system?", "options": ["Earth", "Saturn", "Jupiter", "Uranus"], "answer": 2, "category": "GK"},
            {"question": "Who is the author of the book 'To Kill a Mockingbird'?", "options": ["F. Scott Fitzgerald", "Harper Lee", "Jane Austen", "J.K. Rowling"], "answer": 1, "category": "GK"},
            {"question": "What is 2 + 2?", "options": ["3", "4", "5", "6"], "answer": 1, "category": "Math"},
            {"question": "What is 5 x 3?", "options": ["12", "15", "18", "20"], "answer": 1, "category": "Math"},
            {"question": "What is 7 - 2?", "options": ["3", "5", "9", "11"], "answer": 1, "category": "Math"},
            {"question": "What is the process by which plants make their own food?", "options": ["Respiration", "Photosynthesis", "Decomposition", "Fermentation"], "answer": 1, "category": "Science"},
            {"question": "What is the largest living structure on Earth?", "options": ["The Great Barrier Reef", "The Amazon Rainforest", "The Grand Canyon", "The Great Wall of China"], "answer": 0, "category": "Science"}
        ]

        self.current_question = 0
        self.score = 0

        self.question_label = tk.Label(self.window, text=self.questions[self.current_question]["question"], wraplength=400)
        self.question_label.pack()

        self.options_frame = tk.Frame(self.window)
        self.options_frame.pack()

        self.option_buttons = []
        for i, option in enumerate(self.questions[self.current_question]["options"]):
            button = tk.Button(self.options_frame, text=option, command=lambda i=i: self.check_answer(i))
            button.pack(side=tk.LEFT)
            self.option_buttons.append(button)

        self.next_button = tk.Button(self.window, text="Next", command=self.next_question)
        self.next_button.pack()

        self.score_label = tk.Label(self.window, text="Score: 0")
        self.score_label.pack()

    def check_answer(self, option):
        if option == self.questions[self.current_question]["answer"]:
            self.score += 1
            self.score_label['text'] = f"Score: {self.score}"
            messagebox.showinfo("Correct!", "Your answer is correct!")
        else:
            messagebox.showinfo("Incorrect!", "Your answer is incorrect.")

    def next_question(self):
        self.current_question += 1
        if self.current_question >= len(self.questions):
            self.window.quit()
        else:
            self.question_label['text'] = self.questions[self.current_question]["question"]
            for i, button in enumerate(self.option_buttons):
                button['text'] = self.questions[self.current_question]["options"][i]

    def run(self):
        self.window.mainloop()

if __name__ == "__main__":
    app = QuizApp()
    app.run()
```

Ab yeh code GK, Math aur Science ke prashn shaamil karta hai. Aap is code ko apne local machine par chala sakte hain aur quiz app ka upyog kar sakte hain.
