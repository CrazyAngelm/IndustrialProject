# Rhasspy Intents

Voice commands stored in a `sentence.ini` whose "sections" are intents and "values" are sentence templates.

`sentences.ini` contents:

```
[True]
да:True{answer!bool}

[False]
нет:False{answer!bool}

[GetTime]
\[скажи] (сколько | какое | который) [сейчас] (времени | время | час)

[SetTimer]
(установи | поставь | запусти | начни): таймер [на] (1..12){hour} (час | часа | часов)
(установи | поставь | запусти | начни): таймер [на] (1..12){hour} (час | часа | часов) [и] (1..59){minute} (минуту | минуты | минут)
(установи | поставь | запусти | начни): таймер [на] (одну:1 | 2..59){minute} (минуту | минуты | минут)
(установи | поставь | запусти | начни): таймер [на] (одну:1 | 2..59){minute} (минуту | минуты | минут) [и] (1..59){second} (секунду | секунды | секунд)
(установи | поставь | запусти | начни): таймер [на] (одну:1 | 2..59){second} (секунду | секунды | секунд)

[GetTimer]
сколько [осталось] [до окончания | до конца | на] (таймера | таймере)

[EndTimer]
(останови | выключи | отмени) таймер

```

## Intent JSON

Here is the list of JSON responses to current intents.

## [True]

```
{
    "entities": [
        {
            "end": 4,
            "entity": "answer",
            "raw_end": 2,
            "raw_start": 0,
            "raw_value": "да",
            "start": 0,
            "value": true,
            "value_details": {
                "kind": "Number",
                "value": true
            }
        }
    ],
    "intent": {
        "confidence": 1,
        "name": "True"
    },
    "raw_text": "да",
    "raw_tokens": [
        "да"
    ],
    "slots": {
        "answer": true
    },
    "text": "True",
    "tokens": [
        "True"
    ],
    "wakeword_id": "default"
}
```

## [False]

```
{
    "entities": [
        {
            "end": 5,
            "entity": "answer",
            "raw_end": 3,
            "raw_start": 0,
            "raw_value": "нет",
            "start": 0,
            "value": false,
            "value_details": {
                "kind": "Number",
                "value": false
            }
        }
    ],
    "intent": {
        "confidence": 1,
        "name": "False"
    },
    "raw_text": "нет",
    "raw_tokens": [
        "нет"
    ],
    "slots": {
        "answer": false
    },
    "text": "False",
    "tokens": [
        "False"
    ],
    "wakeword_id": "default"
}
```

## [GetTime]

```
{
    "intent": {
        "name": "GetTime",
        "confidence": 1
    },
    "entities": [],
    "slots": {},
    "text": "сколько времени",
    "raw_text": "сколько времени",
    "tokens": [
        "сколько",
        "времени"
    ],
    "raw_tokens": [
        "сколько",
        "времени"
    ],
    "wakeword_id": "default",
    "siteId": "default",
    "sessionId": "default-default-4a96813f-ac7f-4023-b57d-e5c41d2dfada",
    "customData": "default",
    "wakewordId": "default",
    "lang": null
}
```

## [SetTimer]

```
{
    "entities": [
        {
            "end": 11,
            "entity": "minute",
            "raw_end": 22,
            "raw_start": 18,
            "raw_value": "одну",
            "start": 10,
            "value": "1",
            "value_details": {
                "kind": "Unknown",
                "value": "1"
            }
        },
        {
            "end": 21,
            "entity": "second",
            "raw_end": 38,
            "raw_start": 30,
            "raw_value": "тридцать",
            "start": 19,
            "value": 30,
            "value_details": {
                "kind": "Number",
                "value": 30
            }
        }
    ],
    "intent": {
        "confidence": 1,
        "name": "SetTimer"
    },
    "raw_text": "поставь таймер на одну минуту тридцать секунд",
    "raw_tokens": [
        "поставь",
        "таймер",
        "на",
        "одну",
        "минуту",
        "тридцать",
        "секунд"
    ],
    "slots": {
        "minute": "1",
        "second": 30
    },
    "text": "таймер на 1 минуту 30 секунд",
    "tokens": [
        "таймер",
        "на",
        "1",
        "минуту",
        "30",
        "секунд"
    ],
    "wakeword_id": "default"
}
```

## [GetTimer]

```
{
    "entities": [],
    "intent": {
        "confidence": 1,
        "name": "GetTimer"
    },
    "raw_text": "сколько осталось до конца таймера",
    "raw_tokens": [
        "сколько",
        "осталось",
        "до",
        "конца",
        "таймера"
    ],
    "slots": {},
    "text": "сколько осталось до конца таймера",
    "tokens": [
        "сколько",
        "осталось",
        "до",
        "конца",
        "таймера"
    ],
    "wakeword_id": "default"
}
```

## [EndTimer]

```
{
    "entities": [],
    "intent": {
        "confidence": 1,
        "name": "EndTimer"
    },
    "raw_text": "выключи таймер",
    "raw_tokens": [
        "выключи",
        "таймер"
    ],
    "slots": {},
    "text": "выключи таймер",
    "tokens": [
        "выключи",
        "таймер"
    ],
    "wakeword_id": "default"
}
```