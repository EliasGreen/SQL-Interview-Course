![image](https://github.com/user-attachments/assets/844a1b6b-01d3-4683-bcf7-ba28b1b88ebf)

## [1] Ищем нужные данные?

Давайте сделать небольшой recap (=резюме) того, что мы научились делать
- создаем таблички
- и выбираем из них либо все столбцы, либо конкретные столбцы

Сейчас же мы помоговорим о второй части измерения (ибо о столбцах уже поговорили) 

Мы говорим о строках

Точнее о том, как выбирать конкретные строчки по конкретным критериях 

Например, мы любим только шоколадные конфеты, поэтмоу мы хотим выбрать не все, а только вот такие конфеты 

Но ... сначала снимем свои оковы от онлайн редактора и будем работать там, где работают настоящие аналитики - в Dbeaver 


## [2] Dbeaver (в простонародии - бобер)

![image](https://github.com/user-attachments/assets/eb196cc2-e086-449b-8533-6cff26648879)


Че делаем:
1. Скачивай Dbeaver https://dbeaver.io/download/ (это бесплатно, не боись, вирусов тоже нет
2. При первом заходе в “бобра” - увидишь предложение установить тестовую базу данных - смело устанавливай (она будет на SQLite, но для задачи - этого более, чем хватит)

![image](https://github.com/user-attachments/assets/5932452a-0910-404b-9245-770f54fdcbd3)

## [3] Готовимся к поиску нужных данных

Теперь создадим заново нашу табличку и наполнил ее нужными данными

```
CREATE TABLE Characters (
    CharacterID INTEGER PRIMARY KEY AUTOINCREMENT,
    Name VARCHAR(100) NOT NULL,
    Species VARCHAR(50),
    Gender VARCHAR(20),
    OriginPlanetID INT,
    Status VARCHAR(20) CHECK (Status IN ('Alive', 'Dead', 'Unknown')),
    UNIQUE (Name)
);
```

И вот этими строчками вставим трех персонажей в табличку

```
-- Insert data into Characters table
INSERT INTO Characters (Name, Species, Gender, OriginPlanetID, Status) VALUES
('Rick Sanchez', 'Human', 'Male', 1, 'Alive'),
('Morty Smith', 'Human', 'Male', 1, 'Alive'),
('Summer Smith', 'Human', 'Female', 1, 'Alive');
```

Вот этой строчкой выберем теперь все данные из уже созданной и заполненной таблички

```
SELECT *
FROM Characters
```

![image](https://github.com/user-attachments/assets/d92d78f1-a4ab-4f9a-88a7-4909b98e42f2)

