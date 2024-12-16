# АНАЛИЗ ДАННЫХ И ИСКУССТВЕННЫЙ ИНТЕЛЛЕКТ [in GameDev]
Отчет по лабораторной работе #1 выполнил(а):
- Опарин Роман Дмитриевич
- РИ230935
Отметка о выполнении заданий (заполняется студентом):

| Задание | Выполнение | Баллы |
| ------ | ------ | ------ |
| Задание 1 | * | 60 |
| Задание 2 | * | 20 |
| Задание 3 | # | 20 |

знак "*" - задание выполнено; знак "#" - задание не выполнено;

Работу проверили:
- к.т.н., доцент Денисов Д.В.
- к.э.н., доцент Панов М.А.
- ст. преп., Фадеев В.О.

## Цель работы
Научиться работать с балансировкой оружия в игре 

## Задание 1
### Расширьте варианты доступного оружия в игре.
Ход работы:
Решить какое оружие необходимо для расширения вариативности выбора в игре Save RTF и сбалансировать его, используя гугл таблицу

Для данной работы я выбрала копье, лук, арбалет, миномет и огнемет

Ссылка на заполненую по шаблону гугл таблицу
https://docs.google.com/spreadsheets/d/1lq3GiSmgXUiHdzcoyySLo766AmuDKQRnuJ-sompQDmA/edit?gid=0#gid=0

## Задание 2
### Визуализируйте параметры оружия в таблице. Постройте примеры для следующих математических величин:
- Среднеквадратическое отклонение (СКО)
- Разброс урона оружия
- Вариативность времени отклика игрока (реакция на события)

![d4fb2be8-c6ee-4fbd-aaa3-ceb0b92a7c6d](https://github.com/user-attachments/assets/4998665e-2750-49d0-bec1-b793b0ce3cb0)




## Задание 3
### визуализировать данные из google-таблицы с помощью Python 
```py

import matplotlib.pyplot as plt

# Данные
weapons = {
    "Плазмаган": {"damage": 6, "hits": [(2, 1), (3, 4), (1, -2), (4, 5), (5, 3)], "misses": [(1, 3), (3, 2), (0, 0), (4, 4), (3, 1)]},
    "Рокет Лаунчер": {"damage": 8, "hits": [(0, 0), (0, 0), (0, 0), (0, 0), (0, 0)], "misses": [(1, 2), (2, 7), (0, 4), (-1, 5), (-2, 1)]},
    "Нэилган": {"damage": 4, "hits": [(1, 0), (2, -1), (3, 2), (0, -3), (-1, 1)], "misses": [(1, -2), (2, 2), (0, 1), (3, -1), (-2, 0)]},
    "Кувалда": {"damage": 10, "hits": [(4, 4), (5, 5), (6, 6), (3, 3), (4, 2)], "misses": [(3, 4), (7, 8), (2, 3), (8, 5), (9, 4)]}
}

fig, axs = plt.subplots(2, 2, figsize=(10, 10))

# Визуализация
for ax, (weapon, data) in zip(axs.flat, weapons.items()):
    # Попадания
    x_hits = [hit[0] for hit in data["hits"]]
    y_hits = [hit[1] for hit in data["hits"]]
    ax.scatter(x_hits, y_hits, c='g', label='Попадания', marker='x')
    
    # Промахи
    x_misses = [miss[0] for miss in data["misses"]]
    y_misses = [miss[1] for miss in data["misses"]]
    ax.scatter(x_misses, y_misses, c='r', label='Промахи', marker='o')
    
    # Цель в центре
    ax.scatter(0, 0, c='b', label='Цель (0,0)', marker='*', s=100)
    
    # Установка границ
    ax.set_xlim(-10, 10)
    ax.set_ylim(-10, 10)

    ax.set_title(f"{weapon} (Урон: {data['damage']})")
    ax.set_xlabel("Координата X")
    ax.set_ylabel("Координата Y")
    ax.axhline(0, color='black', lw=0.5, ls='--')
    ax.axvline(0, color='black', lw=0.5, ls='--')
    ax.legend()

plt.tight_layout()
plt.show()
```

## Выводы

Я научился работать с балансом, но так и не понял как правильно строить диаграммы. 

| Plugin | README |
| ------ | ------ |
| Dropbox | [plugins/dropbox/README.md][PlDb] |
| GitHub | [plugins/github/README.md][PlGh] |
| Google Drive | [plugins/googledrive/README.md][PlGd] |
| OneDrive | [plugins/onedrive/README.md][PlOd] |
| Medium | [plugins/medium/README.md][PlMe] |
| Google Analytics | [plugins/googleanalytics/README.md][PlGa] |

## Powered by

**BigDigital Team: Denisov | Fadeev | Panov**
