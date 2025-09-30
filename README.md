# assist-ecom-sdk

Assist SDK + Demo App

Полный исходный код и актуальная версия проекта доступны в публичном репозитории компании Assist:  
[github.com/assist-group/assist-mcommerce-sdk-android-new](https://github.com/assist-group/assist-mcommerce-sdk-android-new)  
Вся интеллектуальная собственность исходного кода принадлежит компании Assist.

**Q: Почему в этом репозитории нет кода?**  
A: Код принадлежит компании. Этот репозиторий - ссылка на оригинальный open-source проект с кратким описанием моей роли и решений.  
**Q: Как проверить мой вклад?**  
A: История коммитов доступна в оригинальном репозитории. Фильтр по автору:  
[github.com/assist-group/assist-mcommerce-sdk-android-new/commits?author=tbelousov](https://github.com/assist-group/assist-mcommerce-sdk-android-new/commits?author=tbelousov)

**Задача**  
Разработать Android SDK и демо-приложение для приёма оплат через платёжный агрегатор Assist с поддержкой web-платежей и токенизированных платёжных методов (Google Pay, Samsung Pay, Mir Pay)  

**Роль**  
Ведущий разработчик/архитектор (end-to-end)  

**Технологии**  
Kotlin, Coroutines, Retrofit, OkHttp, Dagger2, Room, WebView, Google Pay API, Samsung Pay SDK, Mir Pay

## Архитектура

- SDK-слой:  
**Engine (фасад)**: оркестрация сценариев (регистрация устройства, web-платёж, платёж токеном, получение результата, хранилище)  
**API**: Retrofit с комбинированным конвертером (XML/JSON)  
**Storage**: Room (AssistOrder), DAO с upsert и маппингом в доменную модель  
**UI-модуль (внутренний)**: WebViewActivity для web-флоу, PayActivity для intent-based флоу

- Demo app:  
MainActivity для запуска сценариев, Result/Storage экраны  
Обёртки для Google Pay / Samsung Pay / Mir Pay (только получение токена в тестовом окружении)

- Безопасность:  
Токены платёжных систем не логируются, приватные ключи для Mir Pay - исключительно на бэкенде мерчанта

---

## Результат

SDK используется клиентами Assist для интеграции приёма платежей на Android‑устройствах. Проект поддерживается и развивается как открытый исходный код.
