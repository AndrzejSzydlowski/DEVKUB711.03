# Домашнее задание к занятию "11.03 Микросервисы: подходы"

## Задача 1: Обеспечить разработку

Я бы предложил связку Gitlab и Docker Compose , т.к. она как мне кажется всеобъемлюща и максимально соответствует приведенным требованиям
Gitlab сам по себе облачен, но можно его поставить и на свой сервер, имеет встроенный гит, можно создавать репозитории под каждый сервис,
можно использовать триггеры разных видов, для разных конвейерных лент, его подсистема registries хранит набор docker-образов, gitlab хранит ключи в credentials inventory
все docker образы можно взять из docker compose.  и насколько я понял Gitlab runner агенты дадут возможность параллельного запуска сборок и тестов.

## Задача 2: Логи

Для сбора логов я бы предложил более легковесное решение чем filebeat а именно fluent-bit (соответсвует первым трём требованиям) и Grafana loki для пользовательского
 интерфейса (соответствует остальным последним трём требованиям)

## Задача 3: Мониторинг

Многие предлагают использовать Zabbix т.к. на него не надо накручивать дашборды,  они есть в самом заббиксе, но пишут что для Кубернетса лучше Прометеус, он отлично подходит для динамических систем, автоматически находит необходимые таргеты и ставит на мониторинг. Опыта мониторинга Кубера у меня сейчас нет, поэтому склонен доверять тому что пишут, так что  мой выбор:
Прометеус + Графана
