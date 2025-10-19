# MathLib Geometry

Библиотека для вычисления площадей геометрических фигур.


## 📋Требования

- Python >= 3.7


## Установка

```bash
    pip install math-lib-geometry-maksim
```

## 🚀Быстрый старт

```python
from math_lib import Triangle, Circle, calculate_area

# Создание фигур
triangle = Triangle(3, 4, 5)
circle = Circle(2)

# Вычисление площадей
print(f"Площадь треугольника: {triangle.area()}")  # 6.0
print(f"Площадь круга: {circle.area():.2f}")       # 12.57

# Проверка прямоугольности треугольника
print(f"Треугольник прямоугольный: {triangle.is_right_triangle()}")  # True
```

## 📚Примеры использования

### Базовые операции

```python
from math_lib import Triangle, Circle

# Работа с треугольниками
triangle1 = Triangle(3, 4, 5)
print(f"Площадь: {triangle1.area()}")                    # 6.0
print(f"Валиден: {triangle1.is_valid()}")               # True
print(f"Прямоугольный: {triangle1.is_right_triangle()}") # True

# Работа с окружностями
circle1 = Circle(5)
print(f"Площадь: {circle1.area():.2f}")    # 78.54
print(f"Валидна: {circle1.is_valid()}")    # True

# Обработка невалидных фигур
try:
    invalid_triangle = Triangle(1, 1, 3)
except ValueError as e:
    print(f"Ошибка: {e}")  # Invalid triangle sides
```

### Округление результатов

```python
from math_lib import Triangle, Circle

triangle = Triangle(2, 3, 4)
circle = Circle(1.5)

# Округление до разного количества знаков
print(f"Площадь треугольника: {triangle.area(decimals=2)}")  # 2.90
print(f"Площадь круга: {circle.area(decimals=3)}")           # 7.069
```

### Полиморфная работа с фигурами

```python
from math_lib import Triangle, Circle, calculate_area, ShapeFactory

# Коллекция разных фигур
shapes = [
    Triangle(3, 4, 5),
    Circle(2),
    Triangle(5, 12, 13),
    Circle(1.5)
]

# Вычисление площадей без знания конкретных типов
total_area = 0
for shape in shapes:
    area = calculate_area(shape)
    total_area += area
    print(f"{type(shape).__name__}: {area}")

print(f"Общая площадь: {total_area:.2f}")
```

### Использование фабрики

```python
from math_lib import ShapeFactory, calculate_area

# Динамическое создание фигур
shape1 = ShapeFactory.create_shape("circle", 5)      # Круг радиусом 5
shape2 = ShapeFactory.create_shape("triangle", 3, 4, 5)  # Треугольник 3-4-5

# Полиморфные вычисления
area1 = calculate_area(shape1, decimals=2)  # 78.54
area2 = calculate_area(shape2, decimals=1)  # 6.0

print(f"Площадь круга: {area1}")
print(f"Площадь треугольника: {area2}")
```

## 👨‍💻 Автор

Губенин Максим

- Email: maksimgubenin@mail.ru
- GitHub: https://github.com/Maksim-Gubenin
- PyPI: https://pypi.org/project/math-lib-geometry-maksim/

