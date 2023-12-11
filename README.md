# LauncherPrestarter
Установщик Java и GravitLauncher для вашего проекта, написанный на .NET.
### Совместимость
Установщик требует .NET 4.5.1 и выше, который предустановлен на Windows 8.1/10/11. Установить эту версию можно на Windows 7 и выше. Многие сборки Windows уже содержат в себе .NET Framework подходящей версии.

> [!IMPORTANT]  
> Prestarter_module работает только с GravitLauncher версии 5.5.0+

### Сборка на Windows
- Установите [Visual Studio 2022](https://visualstudio.microsoft.com/ru/vs/community/) и откройте проект
- Откройте файл `PrestarterForm.cs`
- По желанию измените в конструкторе дизайн, надписи и логотип под ваш проект
- Откройте файл `Config.cs`
- Настройте обязательные параметры: `Project` (название вашего проекта, как в конфигурации лаунчсервера) и `LauncherDownloadUrl` (ссылку на загрузку вашего лаунчера с расширением .jar, как в конфигурации лаунчсервера)  
- Выберите тип сборки `Release` и соберите проект комбинацией клавиш `Ctrl+Shift+B`
- Перейдите в папку Prestarter_module командой `cd Prestarter_module`
- Соберите модуль для лаунчсервера командой `gradlew.bat build`
- После сборки перенесите файл `build\libs\Prestarter_module.jar` в папку `modules` лаунчсервера
- Соберите файл лаунчера командой `build` в консоли лаунчсервера
- Запустите собранный файл `Prestarter\bin\Release\Prestarter.exe`
### Сборка на Linux
- Установите `mono-msbuild` и перейдите в папку проекта
- Откройте файл `PrestarterForm.cs`
- По желанию измените дизайн, надписи и логотип под ваш проект
- Откройте файл `Config.cs`
- Настройте обязательные параметры: `Project` (название вашего проекта, как в конфигурации лаунчсервера) и `LauncherDownloadUrl` (ссылку на загрузку вашего лаунчера с расширением .jar, как в конфигурации лаунчсервера)
- Соберите проект командой `msbuild -p:Configuration=Release`
- Запустите собранный файл `Prestarter/bin/Release/Prestarter.exe` на ОС Windows
### Режим замены launch4j
Для использования Prestarter в режиме замены launch4j выполните следующие действия:
- Установите `LauncherDownloadUrl` в `null` в файле `Config.cs` (обратите внимание: `null` должен быть без кавычек)
- Соберите проект с помощью Visual Studio (Windows) или msbuild (Linux)
- Перейдите в папку Prestarter_module командой `cd Prestarter_module`
- Соберите модуль для лаунчсервера командой `./gradlew build`
- После сборки перенесите файл `build\libs\Prestarter_module.jar` в папку `modules` лаунчсервера
- Поместите собранный файл `bin\Release\Prestarter.exe` в корень лаунчсервера с названием `Prestarter.exe`
- Соберите файл лаунчера командой `build` в консоли лаунчсервера
