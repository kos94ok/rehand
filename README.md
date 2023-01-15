# Онлайн-сервис для распознавания русских рукописных текстов

Сайт - [rehand.ru](https://rehand.ru)

## Работа с API

### Shell (curl):

```sh
export HOST=https://rehand.ru
export API_KEY=your_api_key
export PATH_TO_FILE=/home/user/test.jpg

curl -X POST \
    -F "file=@$PATH_TO_FILE" \
    -H "Authorization: $API_KEY" \
    $HOST/api/v1/upload
```

### Python (requests):

```py
HOST = "https://rehand.ru"
API_KEY = "your_api_key"
PATH_TO_FILE = "/home/user/test.jpg"
FILE_NAME = "test.png"

requests.post(
    f"{HOST}/api/v1/upload",
    files={
        "file": (FILE_NAME, open(PATH_TO_FILE, "rb"))
    },
    headers={"Authorization": API_KEY}
)
```

### Формат ответа:

```json
{
    "output_image": "Изображение",
    "output_text": "Выходной текст",
    "status": "success",
    "text": "Files uploaded"
}
```
