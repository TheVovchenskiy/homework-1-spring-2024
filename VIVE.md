# Домашнее задание 1 <!-- omit from toc -->

<style>
bug{
    color: orange;
    font-weight: bold;
}
</style>

## Содержание <!-- omit from toc -->

- [1 Соискатель](#1-соискатель)
  - [1.1 Страница авторизации](#11-страница-авторизации)
  - [1.2 Страница регистрации](#12-страница-регистрации)
  - [1.3 Страница вакансий](#13-страница-вакансий)

Проект доступен по [ссылке](http://212.233.90.231:8085/vacs).



## 1 Соискатель

### 1.1 Страница авторизации

Форма авторизации соискателем представлена на рисунке

![app-auth-form](./images/app-auth-form/form.png)

- поле `Электронная почта`:

  - валидация происходит по регулярному выражению `/.+@.+\..+$g`

  - при ошибке валидации выводится соответсвующее сообщение об ошибке

    ![app-auth-invalid-email-error](./images/app-auth-form/invalid-email-error.png)

  - при вводе одних пробелов в поле возникает следующее сообщение об ошибке

    ![app-auth-empty-email-error](./images/app-auth-form/empty-email-error.png)

  - при вводе нескольких слов в поле, возникает следующее сообщение об ошибке

    ![app-auth-email-one-word-error](./images/app-auth-form/email-one-word-error.png)

  - при валидном значении в поле сообщения не возникает

- <bug>⚠ BUG:</bug> при попытке отправки пустых полей в каждом поле возникает сообщение об ошибке

  ![app-auth-required-fields-error](./images/app-auth-form/required-fields-error.png)

- при отправке неверных данных возникает общая ошибка

  ![app-auth-invalid-email-or-password-error](./images/app-auth-form/invalid-email-or-password-error.png)

- при всех валидных заполненных полях сообщений об ошибках нет, пользователя редиректит на страницу с вакансиями

### 1.2 Страница регистрации

Форма регистрации соискателем представлена на рисунке
![app-reg-form](./images/app-reg-form/form.png)

- поля формы `Имя`, `Фамилия`:

  - обязательные поля для заполнения, иначе, если не заполнены или заполнены пробелами, то выводится сообщения об ошибке

    ![app-reg-name-required-error](./images/app-reg-form/name/required-error.png)

  - должны содержать одно слово, иначе выводится сообщение об ошибке

    ![app-reg-name-one-word-error](./images/app-reg-form/name/one-word-error.png)

  - не должны содержать цифр, иначе выводится сообщение об ошибке

    ![app-reg-name-digits-error](/images/app-reg-form/name/digits-error.png)

  - не должны быть длиннее 20 символов, иначе выводится сообщение об ошибке

    ![app-reg-name-max-len-error](./images/app-reg-form/name/max-len-error.png)

- поле `Электронная почта`

  - валидация происходит по регулярному выражению `/.+@.+\..+$g`

  - должно содержать одно слово, иначе выводится сообщение об ошибке

    ![app-reg-form-email-one-word-error](./images/app-reg-form/email/one-word-error.png)

  - при невалидном значении выводится сообщение об ошибке

    ![app-reg-form-email-invalid-email-error](./images/app-reg-form/email/invalid-email-error.png)

  - в ситуации, когда пользователь с введенной электронной почтой уже существует, выводится общее сообщение об ошибке

    ![app-reg-form-email-already-exist-error](./images/app-reg-form/email/already-exist-error.png)

  - при некорректном домене почты выведится общее сообщение об ошибке

    ![app-reg-form-email-invalid-domain](./images/app-reg-form/email/invalid-domain.png)

- поле `Придумайте пароль`:

  - обязательное поле для заполнения
  - требования к сложности пароля:
    - должен быть от 6 до 128 символов в длину
    - должен содержать заглавные буквы
    - должен содержать цифры
  - при неудовлетварении требованиям сложности пароля выводится сообщение об ошибке

    ![app-reg-form-password-password-error](./images/app-reg-form/password/password-error.png)

- поле `Повторите пароль`:

  - должно совпадать со значением в поле `Придумайте пароль`, иначе выводится сообщение об ошибке

    ![app-reg-form-password-match-error](./images/app-reg-form/password/match-error.png)

- при отсутствии ошибок, сообщений нет, пользователя редиректит на страницу с вакансиями

### 1.3 Страница вакансий
