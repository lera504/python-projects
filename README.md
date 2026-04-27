# python-projects
Мои проекты на Python в рамках курса "Кода будущего"
def anagramm():
  while True:
    word1 = input().upper()
    word2 = input().upper()
    word3 = input().upper()
    if len({word1, word2, word3}) == 3:
      d1 = {letter: word1.count(letter) for letter in word1}
      d2 = {letter: word2.count(letter) for letter in word2}
      d3 = {letter: word3.count(letter) for letter in word3}
      print('Супер' if d1 == d2 == d3 else 'Не пытайся обмануть')
    else:
      print('Не пытайся обмануть')
    print('1 - Сыграть еще раз 2 - Главное меню')
    a = int(input())
    if a == 2:
      break

def scrabl():
  dict_letter = {
      "АВЕИНОРСТ":1,
      "ДКЛМПУ":2,
      "БГЁЬЯ":3,
      "ЙЫ":4,
      "ЖЗХЦЧ":5,
      "ШЭЮ":8,
      "ФЩЪ":10
      }
  while True:
    text = input().upper()
    lst_score = [v for letter in text for k, v in dict_letter.items() if letter in k]
    print(sum(lst_score))
    print('1 - Сыграть еще раз 2 - Главное меню')
    a = int(input())
    if a == 2:
      break

def unique():
  while True:
    n = set(input().lower())
    if len(n) > 15:
      print('Победа')
    else:
      print(f'Не хватило {16 - len(n)}')
    print('1 - Сыграть еще раз 2 - Главное меню')
    a = int(input())
    if a == 2:
      break


people = {
    1: ['Иван', {'фантастика','комикс','детектив', 'роман'}], 
    2: ['Марина', {'комикс', 'фэнтези',  'детектив', 'комедия'}], 
    3: ['Тим', {'фантастика', 'ужасы', 'детектив', 'драма'}], 
    4: ['Никита', {'фэнтези', 'комедия', 'мистика', 'комикс'}], 
    5: ['Владимир', {'комикс', 'роман', 'комедия', 'драма'}]
    }
user_name = input().capitalize()
my_interests = set(input().lower().split())
while True:
  print("1 - Найти друга 2 - Играть 3 - Выйти")
  answer = int(input())
  if answer == 1:
    for k, v in people.items():
      name = v[0]
      person_interests = v[1]
      all_interests = my_interests | person_interests
      common_interests = my_interests & person_interests
      proc = round(len(common_interests) / len(all_interests) * 100)
      if proc > 15:
        print(name, proc)
        print(person_interests - my_interests)
  elif answer == 2:
    print("1 - Скрабл 2 - Уникальные буквы 3 - Анаграммы")
    user_answer = int(input())
    if user_answer == 1:
      scrabl()
    elif user_answer == 2:
      unique()
    elif user_answer == 3:
      anagramm()
  elif answer == 3:
    break
