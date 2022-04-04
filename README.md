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

Elasticsearch + Fluent-Bit + Kibana
опять же ELK стек справился бы с поставленными задачами, но для микросервисов лучше будет использовать лековесный Fluent-Bit
