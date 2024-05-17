import turtle
import random

window = turtle.Screen()
window.bgcolor("black")
window.setup(width=400, height=400)

border = turtle.Turtle()
border.penup()
border.goto(-100, -100)
border.pendown()
border.pensize(1)
for _ in range(4):
    border.forward(200)
    border.left(90)
border.hideturtle()

arrow = turtle.Turtle()
arrow.shape()
arrow.penup()
arrow.speed(0)
arrow.goto(0, 0)
arrow.dx = 3
arrow.dy = 2

available_colors = ["red", "blue", "yellow", "purple", "orange", "green", "pink", "brown", "gray"]

def move_arrow():
    x, y = arrow.xcor(), arrow.ycor()

    if x + arrow.dx > 100 or x + arrow.dx < -100:
        arrow.dx *= -1
        arrow.color(random.choice(available_colors))

    if y + arrow.dy > 100 or y + arrow.dy < -100:
        arrow.dy *= -1
        arrow.color(random.choice(available_colors))

    arrow.setx(x + arrow.dx)
    arrow.sety(y + arrow.dy)

    window.ontimer(move_arrow, 10)

move_arrow()

turtle.mainloop()

