# vk-bot
from random import randrange

import vk_api
from vk_api.longpoll import VkLongPoll, VkEventType

import psycopg2
conn = psycopg2.connect(database="diplom", user="postgres", password="veronika")

token  = input ('Token:vk1.a.oyOMS9Mia8-1d9wzx4iaiL5ScyydRM4ZITb4n9tylutAyVSwQPj79P5mLUviOI6DGA8zKgl3LqaFeo58vWzIRnsaNl1pC8V3lqffNdnJGxqi2-v7TrQKtumdf6BqWN_PKXe6olRjna4KCrmjOv2XJnDoddi7tlZsutoRnusCE0holZYTGWbJ_BimKUOwEeGduNXwj9tzQRtwOskw3Meajw ')

vk = vk_api.VkApi(token=token)
longpoll = VkLongPoll(vk)

        with conn.cursor() as cur:
            cur.execute("CREATE TABLE user(id SERIAL PRIMARY KEY,"
                        "age INTEGER,"
                        "gender VARCHAR,"
                        "city VARCHAR,"
                        "family_status VARCHAR)");

        with conn.cursor() as cur:
            cur.execute(
                "INSERT INTO user (age, gender, city, family_status)
            VALUES('{age}', '{gender}', '{city}', '{family_status}')");
            conn.close()


def user (user_id, message):
    vk.method('messages.send', {'user_id: id ', 'message': message, 'random_id': randrange (10 ** 7),})


for event in longpoll.listen():
    if event.type == VkEventType.MESSAGE_NEW:

        if event.to_me:
            request = event.text

            if request == "привет":
                write_msg(event.user_id, f"Хай, {event.user_id}")
            elif request == "пока":
                write_msg(event.user_id, "Пока((")
            else:
                write_msg(event.user_id, "Не поняла вашего ответа...");

 def get_photos_id(self, user_id):
                    url = 'https://api.vk.com/method/photos.getAll'
                    params = {'access_token': user_token,
                              'type': 'album',
                              'owner_id': user_id,
                              'extended': 1,
                              'count': 25,
                              'v': '5.131'}
                    resp = requests.get(url, params=params)
                    dict_photos = dict()
                    resp_json = resp.json()
                    try:
                        dict_1 = resp_json['response']
                        list_1 = dict_1['items']
                        for i in list_1:
                            photo_id = str(i.get('id'))
                            i_likes = i.get('likes')
                            if i_likes.get('count'):
                                likes = i_likes.get('count')
                                dict_photos[likes] = photo_id
                        list_of_ids = sorted(dict_photos.items(), reverse=True)
                        return list_of_ids
                    except KeyError:
                        self.write_msg(user_id, 'Ошибка получения токена');

    ef
    get_photo_1(self, user_id):
    list = self.get_photos_id(user_id)
    count = 0
    for i in list:
        count += 1
        1 == == 1:
        return i[1]


def get_photo_2(self, user_id):
    list = self.()
    count = 0
    for i in list:
        count += 1
        2 == == 2:
        return i[1]


def get_photo_3(self, user_id):
    list = self.()
    count = 0
    for i in list:
        count += 1
        3 == == 3:
        return i[1]

 bot = VKBot()
