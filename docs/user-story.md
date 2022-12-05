# Пользовательские истории

## Пользователь системы
Потенциальным пользователем системы является человек, который проживает в квартире/доме и имеет необходимость хранить или отправлять показания счетчиков*, а также просматривать статистику расходов/потребления коммунальных услуг.

> * **счетчик** - прибор, предназначенный для измерения и учета объема потребления коммунальных услуг. Может учитывать услуги разных видов - вода ХВС/ГВС, электроэнергия (день/ночь), газ.


---


# Сценарии использования

## Главная страница
Я, как пользователь системы, хочу ознакомиться с возможностями системы, в виде текстово-графической информации и иметь возможность войти в систему или зарегистрироваться в ней.

> // TODO

---

## Личный кабинет

### Страница входа в личный кабинет
Я, как пользователь системы, хочу войти в свой личный кабинет, чтобы воспользоваться функционалом системы. 

#### Основной сценарий
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь активирует поле ввода логина | Система предоставляет возможность ввода логина |
| 2 | Пользователь вводит логин | Система выдает предупреждение, если введенный логин  не соответствует валидации |
| 3 | Пользователь активирует  поле ввода пароля | Система предоставляет  возможность ввода пароля |
| 4 | Пользователь вводит пароль | Система активирует кнопку "Войти" |
| 5 | Пользователь нажимает кнопку "Войти" | Система уведомляет об успешном входе в систему и переадресовывает пользователя в личный кабинет, либо уведомляет об ошибке, подсвечивая поле, содержащее ошибку и сообщение о типе ошибки |

#### Альтернативный сценарий #1
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь выбирает способ входа по коду в сообщении | Система предоставляет возможность ввода номера телефона/email/telegram в качестве логина |
| 2 | Пользователь вводит в поле вводе логина номер телефона/email/telegram | Система генерирует уникальный 6-ти значный код и отправляет его в сообщении пользователю способом, который зависит от введенного логина - SMS сообщение по номеру телефону, письмо на email или сообщение в мессенджере telegram |
| 3 | Пользователь вводит полученный код в поле ввода кода | Система уведомляет об успешном входе в систему и переадресовывает пользователя в личный кабинет (если есть квартиры, то в журнал активной квартиры, если нет - то на страницу добавления квартиры), либо уведомляет об ошибке, подсвечивая поле, содержащее ошибку и сообщение о типе ошибки |

#### Альтернативный сценарий #2
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на кнопку "Нет аккаунта?" | Система переадресовывает пользователя на страницу регистрации |
  
#### Правила валидации пароля
| № | Правило |
| ------------- | ------------- |
| 1 | Пароль должен быть не короче 8 символов и не длиннее 40 символов |
| 2 | Пароль должен содержать хотя бы одну заглавную букву и одну цифру |
| 3 | Пароль должен содержать только латинские буквы |
| 4 | Пароль может содержать цифры |
| 5 | Пароль может содержать спецсимволы |
| 6 | Пароль не должен содержать пробелы |

#### Правила валидации логина
_Если в качестве логина используется номер телефона_
| № | Правило |
| ------------- | ------------- |
| 1 | Логин должен содержать только цифры |
| 2 | Логин должен начинать с +7 и соответствовать маске "+79010020304" |

_Если в качестве логина используется email_
| № | Правило |
| ------------- | ------------- |
| 1 | Логин должен содержать только латинские буквы |
| 2 | Логин может включать цифры и спецсимволы, вроде дефис |
| 3 | Логин должен содержать символ @ и точку после нее, но перед точкой обязательно должны быть буквы. Пример - mail@yandex.ru |

_Если в качестве логина используется telegram_
| № | Правило |
| ------------- | ------------- |
| 1 | Логин должен содержать только латинские буквы |
| 2 | Логин может включать цифры и спецсимволы, вроде дефис |

#### Требования к пользовательскому интерфейсу
Пароль не должен отображаться на экране при вводе. Вместо символов должны отображаться кружочки.

В поле ввода пароля должен быть значок глаза, при нажатии на который пароль показывается.


---


### Страница регистрации в личном кабинете
Я, как пользователь системы, хочу зарегистрироваться в системе, чтобы ознакомиться и начать пользоваться функционалом системы.

#### Основной сценарий
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь активирует поле ввода логина | Система предоставляет возможность ввода логина |
| 2 | Пользователь вводит логин | Система выдает предупреждение, если введенный логин  не соответствует валидации |
| 3 | Пользователь активирует  поле ввода пароля | Система предоставляет возможность ввода пароля |
| 4 | Пользователь вводит пароль | Система активирует кнопку "Зарегистрироваться" |
| 5 | Пользователь нажимает кнопку "Зарегистрироваться" | Система уведомляет об успешной регистрации в системе и переадресовывает пользователя в личный кабинет, либо уведомляет об ошибке, подсвечивая поле, содержащее ошибку и сообщение о типе ошибки |

#### Альтернативный сценарий #1
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь выбирает способ регистрации по коду в сообщении | Система предоставляет возможность ввода номера телефона/email/telegram в качестве логина |
| 2 | Пользователь вводит в поле вводе логина номер телефона/email/telegram | Система генерирует уникальный 6-ти значный код и отправляет его в сообщении пользователю способом, который зависит от введенного логина - SMS сообщение по номеру телефону, письмо на email или сообщение в мессенджере telegram |
| 3 | Пользователь вводит полученный код в поле ввода кода | Система уведомляет об успешной регистрации в системе и переадресовывает пользователя в личный кабинет, либо уведомляет об ошибке, подсвечивая поле, содержащее ошибку и сообщение о типе ошибки |

#### Альтернативный сценарий #2
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на кнопку "Уже есть аккаунт?" | Система переадресовывает пользователя на страницу входа в систему |

#### Требования к пользовательскому интерфейсу
Пароль не должен отображаться на экране при вводе. Вместо символов должны отображаться кружочки.

В поле ввода пароля должен быть значок глаза, при нажатии на который пароль показывается.


---


### Страница списка квартир пользователя
Я, как пользователь системы, хочу увидеть список добавленых мной квартир и иметь возможность управлять им. Под управлением я хочу иметь возможность добавить новую квартиру, удалить какую-либо из существующих квартир, отредактировать какую-либо из существующих квартир. Также хочу иметь возможность выбрать квартиру для добавления/управления счетчиками в этой квартире.

#### Основной сценарий, если еще нет добавленных квартир
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на элемент интерфейса в виде символа/иконки "+" для добавления новой квартиры | Система переадресовывает пользователя на форму добавления новой квартиры |

#### Основной сценарий, если уже есть добавленные квартиры
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на нужную квартиру | Система активирует выбранную квартиру и переадресовывает пользователя на страницу счетчиков, связанных с выбранной квартирой |

#### Альтернативный сценарий №1
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на иконку карандаша рядом с квартирой | Система переадресовывает пользователя на страницу редактирования выбранной квартиры |

#### Альтернативный сценарий №2
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на иконку корзины рядом с квартирой | Система показывает всплывающее окно с информацией о необходимости подтвердить удаление квартиры с помощью ввода названия квартиры |
| 2 | Пользователь нажимает на кнопку "Удалить" | Система удаляет выбранную квартиру и возвращает пользователя к списку его квартир, в котором выбранная была удалена. Система помещает квартиру в архив и отображает ее в списке квартир в отдельном списке внизу с возможность восстановить квартиру или удалить навсегда |

#### Альтернативный сценарий №3
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на иконку корзины рядом с квартирой | Система показывает всплывающее окно с информацией о необходимости подтвердить удаление квартиры с помощью ввода названия квартиры |
| 2 | Пользователь нажимает на кнопку "Отмена" | Система возвращает пользователя к списку его квартир |

#### Альтернативный сценарий №4
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на иконку активации рядом с квартирой | Система показывает всплывающее окно с информацией о необходимости подтвердить выбор данной квартиры в качестве основной (активной) |
| 2 | Пользователь нажимает на кнопку "Да" | Система помечает данную квартиру как основную (активную) |

#### Альтернативный сценарий №5
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь нажимает на иконку активации рядом с квартирой | Система показывает всплывающее окно с информацией о необходимости подтвердить выбор данной квартиры в качестве основной (активной) |
| 2 | Пользователь нажимает на кнопку "Нет" | Система возвращает пользователя на страницу списка квартир |


#### Требования к пользовательскому интерфейсу
Кнопка "Добавить квартиру" должна быть в виде иконки/символа "+", видимой в любом положении, выделяться визуально.


---


### Страница добавления квартиры
Я, как пользователь системы, хочу добавить свою квартиру, для дальнейшего управления счетчиками в ней.

#### Основной сценарий, если еще нет добавленных квартир
| № | Действия пользователя  | Ожидаемый результат |
| ------------- | ------------- | ------------- |
| 1 | Пользователь активирует поле ввода названия квартиры | Система предоставляет возможность ввода названия квартиры |
| 2 | Пользователь вводит название квартиры | Система выдает предупреждение, если введенное название  не соответствует валидации |
| 3 | Пользователь активирует поле ввода адреса квартиры | Система предоставляет возможность ввода названия адрес |
| 4 | Пользователь вводит адрес | Система выдает предупреждение, если введенный адрес не соответствует валидации |

#### Правила валидации названия квартиры
| № | Правило |
| ------------- | ------------- |
| 1 | Поле не должно быть пустым |

#### Правила валидации адреса квартиры
| № | Правило |
| ------------- | ------------- |
| 1 | Поле не должно быть пустым |
| 2 | Поле должно содержать кириллические символы, цифры, спецсимволы "-/." |



---


### Страница добавления счетчика
Я, как пользователь системы, добавить счетчик, для записи, хранения и отправки его показаний.

#### Основной сценарий, если еще нет добавленных счетчиков

| 1 | Пользователь активирует поле ввода названия счетчика | Система предоставляет возможность ввода названия счетчика |
| 2 | Пользователь вводит название счетчика | Система выдает предупреждение, если введенное название  не соответствует валидации |
| 3 | Пользователь активирует поле ввода описания счетчика | Система предоставляет возможность ввода описания счетчика |
| 4 | Пользователь вводит описание счетчика | Система выдает предупреждение, если введенное описание не соответствует валидации |
| 5 | Пользователь активирует поле выбора типа счетчика | Система показывает выпадающий список с предуказанными администратором типами |
| 6 | Пользователь выбирает необходимый типа счетчика | Система закрывает выпадающий список и активирует выбранный тип |
| 7 | Пользователь активирует поле ввода начального показания счетчика | Система предоставляет возможность ввода начального показания счетчика |
| 8 | Пользователь вводит начальное показание счетчика | Система выдает предупреждение, если введенное название  не соответствует валидации |