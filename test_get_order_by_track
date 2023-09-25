import data
import configuration
import requests


# Запрос_создание заказа
def post_create_new_order():
    return requests.post(configuration.URL_SERVICE + configuration.CREATE_ORDER_PATH,
                         json=data.order_body,
                         headers=data.headers)


# Сохраняем_номер_трека_заказа
def save_track_num():
    resp_track_num = post_create_new_order()
    return resp_track_num.json()["track"]


# Проверем код ответа
def test_get_order_by_track():
    t = save_track_num()
    resp_order = requests.get(configuration.URL_SERVICE + configuration.GET_ORDER_BY_TRACK_PATH + str(t))
    assert resp_order.status_code == 200
