# solid-meme
import turtle
import math

# Настройка экрана
screen = turtle.Screen()
screen.bgcolor("black")
screen.title("DOOM Черепаха")

# Создание черепахи
doom_turtle = turtle.Turtle()
doom_turtle.speed(0)
doom_turtle.hideturtle()

# Функция для рисования стилизованного глаза демона
def draw_eye(x, y, size, color):
    doom_turtle.penup()
    doom_turtle.goto(x, y)
    doom_turtle.pendown()
    
    doom_turtle.color(color)
    doom_turtle.begin_fill()
    doom_turtle.circle(size)
    doom_turtle.end_fill()
    
    # Зрачок
    doom_turtle.color("black")
    doom_turtle.begin_fill()
    doom_turtle.circle(size/2)
    doom_turtle.end_fill()

# Функция для рисования рогов
def draw_horn(x, y, length, angle):
    doom_turtle.penup()
    doom_turtle.goto(x, y)
    doom_turtle.pendown()
    doom_turtle.setheading(angle)
    
    doom_turtle.color("darkred")
    doom_turtle.width(10)
    doom_turtle.forward(length)
    
    # Добавляем текстуру к рогу
    for i in range(5):
        doom_turtle.right(20)
        doom_turtle.forward(length/10)
        doom_turtle.left(20)
        doom_turtle.forward(length/10)

# Основная функция рисования демона-черепахи
def draw_doom_turtle():
    # Голова
    doom_turtle.penup()
    doom_turtle.goto(0, -100)
    doom_turtle.pendown()
    doom_turtle.color("darkgreen")
    doom_turtle.begin_fill()
    doom_turtle.circle(100)
    doom_turtle.end_fill()
    
    # Рога
    draw_horn(-40, 50, 80, 60)
    draw_horn(40, 50, 80, 120)
    
    # Глаза
    draw_eye(-30, 0, 25, "red")
    draw_eye(30, 0, 25, "red")
    
    # Рот
    doom_turtle.penup()
    doom_turtle.goto(-40, -40)
    doom_turtle.pendown()
    doom_turtle.color("black")
    doom_turtle.width(5)
    doom_turtle.setheading(-45)
    doom_turtle.circle(40, 90)
    
    # Зубы
    for x in [-30, -15, 0, 15]:
        doom_turtle.penup()
        doom_turtle.goto(x, -60)
        doom_turtle.pendown()
        doom_turtle.setheading(90)
        doom_turtle.forward(15)
    
    # Панцирь с текстом DOOM
    doom_turtle.penup()
    doom_turtle.goto(0, -200)
    doom_turtle.pendown()
    doom_turtle.color("brown")
    doom_turtle.begin_fill()
    doom_turtle.circle(150)
    doom_turtle.end_fill()
    
    # Надпись DOOM на панцире
    doom_turtle.penup()
    doom_turtle.goto(-70, -120)
    doom_turtle.pendown()
    doom_turtle.color("red")
    doom_turtle.write("DOOM", font=("Arial", 30, "bold"))

# Рисуем демона-черепаху
draw_doom_turtle()

# Завершение
turtle.done()
