==============================
Синхронизация с Thunderbird
==============================

`Thunderbird <https://www.thunderbird.net>`_ -  это современный и многофункциональный клиент электронной почты, который, при минимуме усилий, может помочь организовать работу с контактами и календарями. По умолчанию он не поддерживает синхронизацию контактов с помощью протокола CardDAV и не может автоматически находить уже созданные на сервере адрессные книги и календари, поэтому для синхронизации с Nextcloud также необходимо установить несколько дополнений. Они легко устанавливаются с помощью встроеннтого в Thunderbird менеджера дополнений. 

Предпочтительный вариант
------------------------

Необходимо предварительно установить два или три дополнения:

1. `Lightning calendar <https://addons.thunderbird.net/en/thunderbird/addon/lightning/>`_ (если ваша версия Thunderbird ниже 68).
2. Менеджер синхронизации `TBSync <https://addons.thunderbird.net/en/thunderbird/addon/tbsync/>`_.
3. `Расширение TBSync <https://addons.thunderbird.net/en/thunderbird/addon/dav-4-tbsync/>`_ для поддержки протоколов CalDAV и CardDAV.

После этого, для того чтобы открыть Менеджер аккаунтов TBSync, необходимо в главном меню окна Thunderbird (вызывается нажатием левого Alt на клавиатуре) последовательно зайти в
**Инструменты** - **Настройка синхронизации (TBSync)**, в том случае если у вас Windows, или
**Правка** - **Настройка синхронизации (TBSync)**, в том случае если у вас Linux.

Затем:

* В разделе "Настройки аккаунта" нажать последовательно **Действия для аккаунта** - **Добавить новый аккаунт** - **CalDAV & CardDAV**
* В окне "Выберите профиль сервера" убедиться в том, что выбран пункт **Автоматическая настройка** и нажать **Далее**
* Ввести произвольное **Имя аккаунта** и полученные заранее **Имя пользователя**, **Пароль**, **Адрес сервера**, нажать **Далее**
* На следующем этапе TBSync попытается получить с сервера доступные ссылки для взаимодействия по протоколам CalDAV и CardDAV. По окончании нажмите **Готово**
* Теперь проверьте галочку **Включить и синхронизировать этот аккаунт**. TBSync найдёт все ссылки на календари и адрессные книги, доступные пользователю на данном сервере.
* Поставьте галочку напротив каждого из пунктов, которые должны синхронизироваться. Выберите время, по истечении которого каждый раз будет запускаться автоматическая синхронизация. Нажмите кнопку **Синхронизировать**
* После успешного выполнения первой синхронизации можно закрыть Менеджер аккаунтов TBSync. В большинстве случаев, если у вас нет необходимости в более продвинутой настройке, на этом настройку можно закончить.


Альтернативный вариант: использовать дополнение CardBook (Только для синхронизации контактов)
---------------------------------------------------------------------------------------------
`CardBook <https://addons.thunderbird.net/en/thunderbird/addon/cardbook/>`_  это продвинутый аналог встроенной в Thunderbird адрессной книги, поддержтвающий протокол CardDAV. Вы можете пользоваться одновременно TBSync и CardBook.
 
1. Нажмите значек CardBook в верхнем правом углу окна Thunderbird:

.. image:: ../images/cardbook_icon.png

2. В CardBook:

   -  "Address book > New Address book **Remote** > Next
   -  Select **CardDAV**, fill in the address of your Nextcloud server, your user name and password

.. image:: ../images/new_addressbook.png

4. Click on "Validate", click Next, then choose the name of the address book and click Next again:

.. image:: ../images/addressbook_name.png

5. When you are finished, CardBook synchronizes your address books. You can always trigger a synchronisation manually by clicking "Synchronize" in the top left corner of CardBook:

.. image:: ../images/synchronize_cardbook.png

The old method: Manually subscribing to calendars
-------------------------------------------------
This method is only needed if you don't want to install TBSync.

1. Go to your Nextcloud Calendar and click on the 3 dotted menu for the calendar that you want to synchronize which will display and URL that looks something like this:

   ``https://cloud.nextcloud.com/remote.php/dav/calendars/daniel/personal/``

2. Go to the calendar view in Thunderbird and right click in the calendar menu to the left (where the names of the calendars are) to add a **New Calendar**.

3. Choose **On the Network**:

.. image:: ../images/new_calendar.png

4. Choose **CalDAV** and fill in the missing information:

.. image:: ../images/CalDAV_calendar.png

Исправление для Thunderbird 60
------------------------------
Если вы всё ещё пользуетесь Thunderbird 60, необходимо изменить настройки, что бы заставть CalDAV/CardDAV обойти ошибку `#1468918 <https://bugzilla.mozilla.org/show_bug.cgi?id=1468912>`_ в Thunderbird. Подробное описание ошибки `здесь <https://help.nextcloud.com/t/thunderbird-60-problems-with-address-and-calendar-sync/35773>`_.
