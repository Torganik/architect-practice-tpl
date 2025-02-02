# Матрица прослеживаемости требований

## Сервис парковки ParkApp

Архитектор: Гонтарик Виталий / Omicron Persei 8 Inc.
Дата: 10 октября 2023


| Дата | Автор | Что изменилось | 
| :-: | :-: | :-: |
| 10.10.2023| Гонтарик Виталий | Ограничения | 
| 12.10.2023| Гонтарик Виталий | Требования  | 

## 1. Ограничения

|Тип|ID|Описание|Группа источника ограничения|Источник ограничения|Статус|Комментарий|
|---|---|---|---|---|---|---|
|Сроки|С-01|Срок проекта ограничен 4-мя неделями и 5 часами в неделю|Заказчики|Сроки|Новый|Такой срок накладывает ограничение на выпуск MVP|
|Временные|С-02|Через 4 недели продукт должен быть введен в эксплуатацию|Заказчики|Сроки|Новый|Через 4 недели, приложение должно быть введено в эксплуатацию. Следует заложить ввод в эксплуатацию в основной срок|
|Договорные|С-03|Информирование сотрудников охраны|Конечные пользователи|Сотрудники охраны|Новый|Сотрудники охраны готовы принимать информацию о въезжающих автомобилях по эл.почте один раз в сутки. Требуется выяснить у руководства службы охраны, если у них есть возможность получать email, вероятно и есть возможность просмотра страницы с актуальными забронированными парковочными местами и номерами автомобилей.|
|Технологические|С-04|Веб-интерфейс.|Конечные пользователи|Конечные пользователи|Новый|Для пользователей всех уровней веб интерфес будет самым удобным способом взаимодействия с системой|
|Ресурсы|С-05|Количество парковочных мест ограничено, требуется ввести лимиты на пользование парковкой|Конечные пользователи|Конечные пользователи|Новый|Лимиты должны задаваться для всех пользователей на неделю.|
|Ресурсы|С-06|Некоторые парковочные места находятся под навесом, что делает их более привлекательными.|Конечные пользователи|Конечные пользователи|Новый|Чтобы исключить возможность фрода, парковочные места должны выдаваться случайно|
|Ресурсы|С-08|Информирование сотрудников о том, что на следующий день у них забронировано парковочное место.|Конечные пользователи|Конечные пользователи|Новый|Это нужно что бы снизить риск того, что сотрудник займет парковочное место и не воспользуется им.|
|Ресурсы|С-09|Возможные конфликты из за ошибочно занятого парковочного места|Конечные пользователи|Конечные пользователи|Новый|Если человек занял не свое парковочное место.В дополнение к ограничению С-03, сотрудники  охраны должны видеть не только номера автомобилей, которые въезжают на парковку,а так же номер парковочного места. В первую очередь для того что бы была возможность разрешить такой конфликт. Сотрудник охраны может сообщить место которое осталось свободным|
|Ресурсы|С-10|Сотрудник может забронировать только одно парковочное место за раз|Конечные пользователи|Заказчик|Новый||

> ***Комментарий к разделу "Ограничения"***  
> Ограничения сформированы исходя из потребности минимизировать риски которые могут возникать в процессе эксплуатации системы
> 


## 2. Функциональные требования

| Фича | ID | Описание | Приоритет | Группа источника требований | Источник требований | Статус | Комментарий |
| - | - | - | - | - | - | - | - |
|Окно авторизации пользователя|FR-01|Окно ввода Логина и пароля для пользователей парковки|Высокий|Безопасность|Техническая команда|Утвержденный||
|Окно регистрации офис менеджера|FR-02|Интерфейс для ввода секретного кода регистрации и создания нового пользователя с ролью модератора.|Высокий|Безопасность|Техническая команда|Утвержденный||
|Интерфейс для управления пользователями|FR-03|Интерфейс для создания, редактирования, удаления и ограничение доступа пользователей системы|Высокий|Безопасность|Техническая команда|Утвержденный||
|Интерфейс для редактирования плана парковки|FR-04|Интерфейс для загрузки плана парковки, который будет отображен пользователям|Высокий|Конечные пользователи|Пользователи|Утвержденный||
|Интерфейс для управления парковочными местами|FR-05|Управление парковочными местам. Установка номера парковочного места|Высокий|Конечные пользователи|Пользователи|Утвержденный||
|Главный интерфейс пользователя|FR-06|Окно для отображения плана парковки и списка доступных парковочных мест для бронирования|Высокий|Конечные пользователи|Пользователи|Утвержденный||
|Окно бронирования парковочного места|FR-07|Окно в котром у пользователя есть возможность установки номера автомобиля и подтверждение бронирования|Высокий|Конечные пользователи|Пользователи|Утвержденный||
|Интерфейс для редактирования информации о пользователе|FR-08|имя, фамилия,email для оповещения, установка номера автомобиля по умолчанию|Средний|Конечные пользователи|Пользователи|Рассмотренный||
|Система учета баллов парковки пользователей.|FR-09|Лимит на неделю, списание при использовании брони, возврат баллов в случае отмены брони больше чем за сутки|Высокий|Бизнес-аналитики|Заказчик|Утвержденный||
|Автоматическая система рассылки эл. писем |FR-10|Система отвечающая за рассылку эл писем.|Высокий|Партнеры третьих сторон|Сотрудники охраны|Утвержденный||
|Интерфейс управления системой автоматической рассылки эл. писем|FR-11|Настройка рассылки, редактирования шаблонов электронных писем|Низкий|Партнеры третьих сторон|Пользователи|Рассмотренный|Приоритет низкий, т.к. на первое время нет сильной необходимости редактировать шаблон рассылки|

## 3. Нефункциональные требования

|Атрибут качества|ID|Описание|Приоритет|Группа источника требований|Источник требований|Статус|Комментарий|
|---|---|---|---|---|---|---|---|
|Производительность|NFR-01|Время реакции системы для 95% действий пользователей не должно превышать 2 секунды|Желательно|Конечные пользователи|Пользователь|Новый||
|Безопасность|NFR-02|Наличие системы аутентификация.В идеале интегрировать ее с уже существующей системой.|Желательно|Конечные пользователи|Пользователь|Новый|Устновлен средний приорите т.к в системе отсутсвуют чувствительные персональные данные|
|Доступность|NFR-03|Система должна быть доступна в любое время дня|Желательно|Конечные пользователи|Пользователь|Новый||
|Модифицируемость|NFR-04|Система должна быть гибкой в настройке для возможности подключения новых клиентов|Высокий|Бизнес-аналитики|Заказчик|Новый||
|Безопасность|NFR-05|Наличие системы авторизацияя. В системе существуют разные роли пользователй, требуется разделять доступ к информации.|Обязательно.|Конечные пользователи|Пользователь|Новый||



---

## 4. Приложение к документу
> Здесь вы можете описывать обозначения, которые вы ввели для себя в этом документе.

> [!NOTE]
>  Если вам требуется дополнить перечень статусов, групп иcточника, приоритетов и пр. вы можете вносить изменения в таблицах в этом разделе

#### Статус
|Название|Комментарий|
|---|---|
|Новый|Требование только что было добавлено и еще не было рассмотрено или на него не было отреагировано.|
|Рассмотренный|Требование было рассмотрено, но еще не было утверждено или отклонено.|
|Утвержденный|Требование было оценено и принято к реализации.|
|Отклоненный|Требование было рассмотрено и признано не необходимым или неосуществимым.|
|В процессе|В настоящее время ведутся работы, связанные с этим требованием.|
|Реализованный|Требование было выполнено в системе или проекте.|
|Устаревший|Требование когда-то было актуальным, но больше не применяется из-за изменений в объеме проекта, целях или других факторах.|
|Приостановленный|Любые действия по требованию приостановлены, возможно, из-за зависимостей, ожидания решений или по другим причинам.|
|Дубликат|Обнаружено, что требование является повторением другого уже учтенного требования.|

#### Группа источников требований/ограничений
|Название|Комментарий|
|---|---|
|Конечные пользователи|Это требования, полученные непосредственно от людей, которые будут использовать систему или продукт.|
|Бизнес-аналитики|Иногда бизнес-аналитики определяют и предлагают требования на основе своего понимания и анализа бизнес-потребностей.|
|Техническая команда|Требования, которые исходят от разработчиков, тестировщиков или других членов технической команды на основе технических ограничений или возможностей.|
|Юридический отдел/Требования регуляторов|Требования, которые возникают из-за юридических или регуляторных обязательств.|
|Маркетинговые исследования|Требования, полученные из маркетинговых исследований, анализа конкурентов или опросов обратной связи с клиентами.|
|Партнеры третьих сторон|Требования, исходящие от внешних партнеров или поставщиков, участвующих в проекте.|
|Операционные команды/Команды поддержки|Требования от команд, которые занимаются эксплуатацией, обслуживанием или поддержкой, с акцентом на такие аспекты, как удобство устранения неполадок, обслуживание и т. д.|
|Безопасность|Требования, которые фокусируются на аспектах безопасности, обеспечивая защиту системы или продукта от угроз.|

#### Тип ограничения
|Название|Комментарий|
|---|---|
|Сроки|Это сроки, которым должны соответствовать проекты или задачи.|
|Бюджет|Это относится к финансовым ограничениям проекта или задачи.|
|Границы проекта|Они определяют границы того, что будет и не будет включено в проект.|
|Ресурсы|Ограничения, связанные с доступными людьми, оборудованием или материалами.|
|Юридические и регуляторные|Законы или правила, которым необходимо следовать.|
|Технологические|Ограничения, связанные с технологией, используемой в проекте.|
|Экологические|Ограничения или требования, связанные с экологическим воздействием.|
|Географические|Ограничения, связанные с местоположением, которые могут влиять на логистику, доставку или выполнение задач.|
|Договорные|Они возникают из обязательных соглашений или договоров, которые диктуют определенные условия, условия или этапы, которые должны быть выполнены.|

#### Приоритет
|Название|Комментарий|
|---|---|
|Обязательно|Критично для проекта. Не подлежащие обсуждению требования, которые должны быть выполнены.|
|Желательно|Важные и ценные требования. Не критичны, но очень желательны для успеха проекта.|
|Возможно|Желательно, но не обязательно. Функции или требования, которые можно отложить без существенного воздействия на немедленный результат проекта.|
|Не будет (на этот раз)|Учтено, но не запланировано для текущей поставки. Может быть рассмотрено в будущих фазах или релизах.|

#### Атрибуты качества
|Название|Комментарий|
|---|---|
|Производительность|Касается отзывчивости системы.|
|Масштабируемость|Способность системы справляться с увеличенными нагрузками или расширять свои обработчике возможности.|
|Доступность|Пропорция времени, когда система функционирует и работает.|
|Надежность|Как часто система выходит из строя и сколько времени требуется, чтобы восстановиться после этих сбоев.|
|Удобство использования|Касается удобства и интуитивности системы для пользователя.|
|Обслуживаемость|Насколько легко определить и устранить проблемы в системе.|
|Переносимость|Легкость, с которой система может быть перенесена из одной среды в другую.|
|Безопасность|Защита информации и данных, обеспечивая невозможность доступа к ней неавторизованными пользователями.|
|Устойчивость|Способность системы адекватно реагировать и восстанавливаться после сбоев.|
|Гибкость|Насколько легко систему можно модифицировать для учета изменяющихся требований.|
|Интерация|Способность системы работать и обмениваться данными с другими системами.|
|Модифицируемость|Стоимость и легкость внесения изменений в систему.|
|Тестируемость|Легкость, с которой можно проверить функциональность системы, чтобы убедиться, что она работает правильно.|
|Восстанавливаемость|Способность системы восстанавливать работу и восстанавливать данные после сбоя.|
