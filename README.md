# ModxAccount
<h3>Личный кабинет веб пользователя MODx Evo</h3>

<p>Сниппет для регистрации, входа, напоминания пароля и личного кабинета пользователя.</p>
<p>Для работы через ajax используется <b>ModxLoader</b> - https://github.com/64j/ModxLoader </p>

<p>Создётся сниппет <b>account</b> с кодом</p>

```php
<?php
require MODX_BASE_PATH.'assets/snippets/account/snippet.account.php';
?>
```

<p>
Создаётся документ "Личный кабинет" -> псевдоним -> <b>account</b> <br>
Далее в нём дочерние ресурсы<br>
Регистрация -> <b>register</b><br>
Профиль -> <b>profile</b><br>
Восстановление пароля -> <b>forgot</b><br>
<br>
и на каждой странице ставится вызов сниппета
</p>

<b>account</b>
<pre>
[!account?
&controller=`account`
&controllerRegister=`account/register`
&controllerLogin=`account`
&controllerForgot=`account/forgot`
&controllerProfile=`account/profile`
&success=``
&userGroupId=``
!]
</pre>

<b>register</b>
<pre>
[!account?
&controller=`account/register`
&controllerRegister=`account/register`
&controllerLogin=`account`
&controllerForgot=`account/forgot`
&controllerProfile=`account/profile`
&success=``
&userGroupId=``
!]
</pre>

<b>profile</b>
<pre>
[!account?
&controller=`account/profile`
&controllerRegister=`account/register`
&controllerLogin=`account`
&controllerForgot=`account/forgot`
&controllerProfile=`account/profile`
&success=``
&userGroupId=``
!]
</pre>

<b>forgot</b>
<pre>
[!account?
&controller=`account/forgot`
&controllerRegister=`account/register`
&controllerLogin=`account`
&controllerForgot=`account/forgot`
&controllerProfile=`account/profile`
&success=``
&userGroupId=``
!]
</pre>

<p>
Вместо псевдонимов контроллеров &controller..., можно поставить id страниц на которых расположен тот или иной вызов сниппета.
</p>
<p>
<b>&success</b> - перенаправление после удачного действия сниппета.
</p>
<p>
<b>&userGroupId</b> - id групп, через запятую для нового зарегистрированного пользователя.
</p>

<h3>Капча</h3>
<p>Используется эта https://github.com/64j/ModxCaptcha</p>
