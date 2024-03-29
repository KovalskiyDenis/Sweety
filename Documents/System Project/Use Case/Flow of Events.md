# Поток событий
---

# Содержание
1 [Актёры](#actors)  
2 [Варианты использования](#use_case)  
2.1 [Войти в приложение](#sign_in_to_the_app)  
2.2 [Зарегистрироваться](#register)  
2.3 [Войти под своим аккаунтом](#log_in_to_your_account)  
2.4 [Выйти из учетной записи](#logout)  
2.5 [Настроить приложение](#settings)  
2.6 [Изменить тему приложения](#change_theme)  
2.7 [Редактировать аккаунт](#edit_profile)  
2.8 [Изменить информацию о себе](#change_info_about_yourself)  
2.9 [Изменить аватар](#change_avatar)  
2.10 [Просмотр списка переписок](#view_messenges)  
2.11 [Действие со списком контактов](#contacts)  
2.12 [Удалить контакт](#remove_ontact)  
2.13 [Добавить контакт](#add_contact)  
2.14 [Написать сообщение](#write_message)  
2.15 [Обновить информацию о пользователе](#update_info)

<a name="actors"/>

# 1 Актёры

| Актёр | Описание |    
|:---|:---|    
| Пользователь | Человек, использующий систему |      
| Зарегистрированный пользователь | Пользователь, который зарегистрировался в приложении |   
| Сервер | Центр обратобки, хранение, распространения информации. Весь обмен информацией проходит через сервер |   

<a name="use_case"/>

# 2 Варианты использования

<a name="sign_in_to_the_app"/>

## 2.1 Войти в приложение

**Описание.** Вариант использования "Войти в приложение" позволяет пользователю войти в приложение.  
**Основной поток.**
1. Вариант использования начинается, когда пользователь запускает приложение;
2. Приложение отображает возможные дальнейшие действия: [войти под своим аккаунтом](#log_in_to_your_account), [зарегистрироваться](#register);
3. Пользователь выбирает необходимое ему действие;
4. Выполняется вариант использования, связанный с выбранным действием;
5. Вариант использования завершается.

<a name="register"/>

## 2.2 Зарегистрироваться

**Описание.** Вариант использования "Зарегистрироваться" позволяет пользователю создать свою учётную запись в приложении.  
**Предусловия.** Пользователь выбрал способ "Зарегистрироваться" для входа в приложение.  
**Основной поток.**
1. Приложение отображает окно регистрации, в котором запрашивает у пользователя ввод имени и парол;
2. Пользователь вводит своё имя;
3. Приложение проверят введённое имя на совпадение и именами уже зарегистрированных пользователей. Если совпадение выявлено, выполняется альтернативный поток А1;
4. Пользователь вводит пароль;  
5. Приложение создает файл профиля пользователя;
6. Приложение скрывает окно регистрации и переводит в окно редактирования профиля;
7. Вариант использования завершается.

**Альтернативный поток А1.**
1. Приложение сообщает пользователю, что пользователь с таким именем уже существует;
2. Возврат к п.2 основного потока.

**Дополнительная информация.** Пользователь имеет возможность отменить действие до подтверждения ввода имени. В случае отмены выполняется альтернативный поток А2.

**Альтернативный поток А2.**
1. Приложение возвращает пользователя на окно входа в приложение;
2. Вариант использования завершается досрочно.

<a name="log_in_to_your_account"/>

## 2.3 Войти под своим аккаунтом

**Описание.** Вариант использования "Войти под своим аккаунтом" позволяет пользователю войти в учётную запись.  
**Предусловия.** Пользователь выбрал действие "Войти" на окне входа в приложение.  
**Основной поток.**
1. Приложение отображает окно входа в учётную запись;
2. Пользователь вводит имя и пароль;
3. Приложение проверяет, существует ли пользователь с таким именем и паролем;  
4. Приложение переводит пользователя на окно его профиля. В случае, если не было найдено пользователя с указанными именем и паролем, выполняется альтернатипный поток А3;  
5. Вариант использования завершается.

**Альтернативный поток А3.**
1. Приложение сообщает пользователю о неправильно введенных данных;
2. Возврат к п. 2 основного потока.

**Дополнительная информация.** Пользователь имеет возможность отменить действие до подтверждения выбора имени. В случае отмены выполняется альтернативный поток А4.

**Альтернативный поток А4.**
1. Приложение скрывает окно регистрации;
2. Вариант использования завершается досрочно.

<a name="logout"/>

## 2.4 Выйти из учетной записи

**Описание.** Вариант использования "Выйти из учётной записи" позволяет вошедшему в свой аккаунт пользователю выйти из учётной записи.  
**Предусловия.** Пользователь зарегистрирован в приложении и вошёл в него под своим аккаунтом.   
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь выбирает пункт меню "Выйти из учётной записи" на главном окне приложения;
2. Приложение скрывает главное окно приложения;
3. Приложение отображает окно входа в приложение;
4. Вариант использования завершается.

<a name="settings"/>

## 2.5 Настроить приложение

**Описание.** Вариант использования "Настроить приложение" позволяет вошедшему в свой аккаунт пользователю настроить приложение.  
**Предусловия.** Пользователь зарегистрирован в приложении и вошёл в него под своим аккаунтом.   
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь выбирает пункт меню "Настроить";
2. Приложение скрывает главное окно приложения;
3. Приложение отображает окно настроек;  
4. Пользователь производит изменение настроек приложения;  
5. Приложение изменяет содержание файла настроек приложения;   
4. Вариант использования завершается.

<a name="change_theme"/>

## 2.6 Изменить тему приложения

**Описание.** Вариант использования "Изменить тему приложения" позволяет пользователю изменить внешний вид приложения.  
**Предусловия.** Пользователь зарегистрирован в приложении и вошёл в него под своим аккаунтом.  
**Основной поток.**  
1. Вариант использования начинается, когда зарегистрированный пользователь выбирает пункт меню "Изменить тему приложения" в окне настроек;  
2. Приложение предлогает пользователю возможные темы;  
3. Пользователь выбирает одну из предложенных тем;
4. Приложение изменяет внешний вид и редактирует файл настроек приложения;  
5. Вариант использования завершается. 

<a name="edit_profile"/>

## 2.7 Редактировать аккаунт

**Описание.** Вариант использования "Редактировать аккаунт" позволяет зарегистрированному пользователю настроить профиль.  
**Предусловия.** Пользователь зарегистрирован в приложении и вошёл в него.  
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь нажимает кнопку "Редактировать" в окне профиля;
2. Приложение отображает окно настроек профиля, в котором возможны действия:[изменить информацию о себе](#change_info_about_yourself) , [изменить аватар](#change_avatar), сохранить настройки;
3. Если пользователь выбирает один из первых двух вариантов, выполняется соответствующий вариант использования;
4. Пользователь выбирает пункт "Сохранить";
5. Приложение сохраняет новые настройки профиля в файл; 
6. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность отменить действие до выбора пункта "Сохранить".  

<a name="change_info_about_yourself"/>

## 2.8 Изменить информацию о себе

**Описание.** Вариант использования "Изменить информацию о себе" позволяет зарегистрированному пользователю отредактировать информацию о себе.  
**Предусловия.** Пользователь зарегистрирован в приложении и вошёл в него.  
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь нажимает кнопку "Редактировать" в окне профиля;
2. Приложение отображает окно настроек профиля, в котором возможны действия:[изменить информацию о себе](#change_info_about_yourself) , [изменить аватар](#change_avatar), сохранить настройки;
3. Пользователь редактирует поле "О себе";
4. Пользователь выбирает пункт "Сохранить";
5. Приложение сохраняет новые настройки профиля в файл; 
6. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность отменить действие до выбора пункта "Сохранить".

<a name="change_avatar"/>

## 2.9 Изменить аватар

**Описание.** Вариант использования "Изменить аватар" позволяет зарегистрированному пользователю изменить аватар.  
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь нажимает кнопку "Редактировать" в окне профиля;
2. Приложение отображает окно настроек профиля, в котором возможны действия:[изменить информацию о себе](#change_info_about_yourself) , [изменить аватар](#change_avatar), сохранить настройки;
3. Пользователь нажимает кнопку "Изменить аватар";
4. Пользователь выбирает новый аватар;
5. Пользователь выбирает пункт "Сохранить";
6. Приложение сохраняет новые настройки профиля в файл; 
7. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность отменить действие до выбора пункта "Сохранить".

<a name="view_messenges"/>

## 2.10 Просмотр списка переписок

**Описание** Вариант использования "Просмотр списка переписок" позволяет зарегистрированному пользователю просмотреть историю и список всех сообщений.  
**Основной поток.**
1. Вариант использования начинается, когда зарегистрированный пользователь переходит на окно "Сообщения";  
2. Приложение отображает окно сообщений, в котором в порядке последней активности находится список диалогов;
3. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность открыть диалог и [написать сообщение](#write_message).

<a name="contacts"/>

## 2.11 Действие со списком контактов

**Описание** Вариант использования "Просмотр списка переписок" позволяет зарегистрированному и вошедшему в приложение пользователю манипулировать списком контактов.  
**Основной поток.**
1. Пользователь переходит на окно "Контакты";  
2. Приложение отображает список контактов, предоставляет возможность выполнить следующие действия: [удалить контакт](#remove_ontact), [добавить контакт](#add_contact), [написать сообщение](#write_message);  
3. Пользователь выбирает один из предложенных вариантов и этот вариант использования выполняется;  
4. Вариант использования завершается.

<a name="remove_ontact"/>

## 2.12 Удалить контакт

**Описание** Вариант использования "Удалить контакт" позволяет пользователю удалить контакт из списка.
**Основной поток.**
1. Пользователь выбирает пункт меню "Удалить контакт" в окне "Контакты";
2. Пользователь выбирает удаляемый контакт;
3. Приложение запрашивает подтверждение действия от пользователя;
4. Пользователь выбирает вариант на удаление. В случает выбора варианта на отказ возврат к пункту 2 основного потока;  
5. Приложение удаляет выбранный контакт из списка контактов пользователя;
6. Вариант использования завершается.

<a name="add_contact"/>

## 2.13 Добавить контакт    

**Описание** Вариант использования "Добавить контакт" позволяет пользователю добавить другого пользователя в свой список контактов.
**Основной поток.**
1. Пользователь выбирает пункт меню "Добавить контакт" в окне "Контакты";
2. Пользователь вводит имя пользователя для добавления;
3. Приложение ищет пользователя по введенному имени;
4. В случае, если аккаунт пользователя с запрошенным именем существует в системе, он добавляется в список контактов. Иначе - выполняется альтернатипный поток Е1;  
5. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность отменить добавление и вернуться на окно "Контакты";  

**Альтернативный поток Е1.**
1. Приложение сообщает пользователю о том, что пользователся с таким именем не существует;
2. Возврат к п. 2 основного потока.

<a name="write_message"/>

## 2.14 Написать сообщение   

**Описание** Вариант использования "Написать сообщение" позволяет пользователю отпраить сообщение.
**Предусловие** Пользователь должен выбрать либо контакт, которому будет отправляться сообщение, либо открыть диалог из окна "Сообщения";  
**Основной поток.**
1. Пользователь переходит в окно диалога;
2. Пользователь набирает сообщение, по необходимости прикрепляя документы;
3. Приложение нажимает кнопку "Отправить";  
4. Приложение формирует сообщение и отправляет его на сервер;  
5. Вариант использования завершается.

**Дополнительная информация.** Пользователь имеет возможность прервать отправление сообщения перейдя в друго окно приложения;  

<a name="update_info"/>

## 2.15 Обновить информацию о пользователе

**Описание** Вариант использования "Обновить информацию о пользователе" редактирует информацию о пользователе на сервере.
**Предусловие** Пользователь должен внести изменения в свой профиль или изменить список контактов;
**Основной поток.**
1. Приложени отправляет на сервер файл профиля пользователя;
2. На сервере происходит изменение профиля пользователя, которые после станут видны остальным пользователям;
3. Вариант использования завершается.
