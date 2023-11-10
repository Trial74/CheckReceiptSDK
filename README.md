[![NuGet](https://img.shields.io/nuget/dt/CheckReceiptSDK.svg?label=NuGet)](https://www.nuget.org/packages/CheckReceiptSDK) 
![Nuget](https://img.shields.io/nuget/v/CheckReceiptSDK)
# CheckReceiptSDK
Библиотека для получения информации по чекам от Федеральной Налоговой Службы (ФНС).

### Usage example:

Регистрация:
```csharp
var result = await FNS.Instance.RegisterAsync("some@mail.com", "Name", "+79991234567");
```
Восстановление пароля:
```csharp
var result = await FNS.Instance.RestorePasswordAsync("+79991234567");
```
Проверка наличия квитанции:
```csharp
var date = DateTime.Parse("2018-05-18T22:05:00");
var result = await FNS.Instance.CheckAsync("8710000101337659", "94248", "815426975", date, 235.61);
```
Получение подробной информации о чеке:
```csharp
var result = await FNS.Instance.ReceiveAsync("8710000101337659", "94248", "815426975", "+79991234567", "123456");
```

### Testing
Существует два типа тестов: модульные тесты и интеграционные тесты. Юнит-тесты можно запускать как есть.
Для запуска интеграционных тестов атрибут Ignore должен быть удален в IntegrationTests.
класс и правильные значения должны быть предоставлены для тестов.

### NB: недостаточно информации для указания всех полей в чеке
