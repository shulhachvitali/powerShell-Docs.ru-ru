---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,командлет"
ms.date: 2016-12-12
title: "Другие полезные объекты для сценариев"
ms.technology: powershell
ms.assetid: 4d781196-720b-4ccc-90d2-c570e5e719f5
ms.openlocfilehash: a1e3ad310303fe02ee61bcd6d2681df6d91a4924
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
---
# <a name="other-useful-scripting-objects"></a>Другие полезные объекты для сценариев
  Следующие объекты предоставляют дополнительные возможности создания сценариев в интегрированной среде сценариев Windows PowerShell. Они не являются частью иерархии **$psISE**.

## <a name="useful-scripting-objects"></a>Полезные объекты для сценариев

### <a name="psunsupportedconsoleapplications"></a>$psUnsupportedConsoleApplications
 Существуют некоторые ограничения, применяемые к взаимодействию интегрированной среды сценариев Windows PowerShell с консольными приложениями. Команда или сценарий автоматизации, требующие участия пользователя, могут не работать так, как при запуске из консоли Windows PowerShell. Может потребоваться заблокировать запуск этих команд или сценариев в области команд интегрированной среды сценариев Windows PowerShell. Объект **$PsUnsupportedConsoleApplications** хранит список таких команд. При попытке выполнить команды, указанные в этом списке, вы получите сообщение о том, что они не поддерживаются. Следующий сценарий добавляет запись в этот список.

```
# List the unsupported commands
psUnsupportedConsoleApplications
# Add a command to this list
psUnsupportedConsoleApplications.Add(“Mycommand”)
#Show the augmented list of commands
psUnsupportedConsoleApplications

```

### <a name="pslocalhelp"></a>$psLocalHelp
 Это объект словаря, который поддерживает сопоставление с учетом контекста разделов справки и связанных ссылок в локальном скомпилированном файле справки HTML. Он используется для поиска локальной справки для определенного раздела. Разделы в этом списке можно добавлять и удалять. В следующем примере кода показаны некоторые примеры пар "ключ —значение", которые содержатся в объекте **$psLocalHelp**.

```
# See the local help map
$psLocalHelp | Format-List

```

### <a name="sample-output"></a>Пример вывода

|||
|-|-|
|Ключ: Add-Computer|Значение: WindowsPowerShellHelp.chm::/html/093f660c-b8d5-43cf-aa0c-54e5e54e76f9.htm|
|Ключ: Add-Content|Значение: WindowsPowerShellHelp.chm::/html/0c836a1b-f389-4e9a-9325-0f415686d194.htm|

 Следующий сценарий добавляет запись в этот список.

```
$psLocalHelp.Add("get-myNoun","c:\MyFolder\MyHelpChm.chm::/html/0198854a-1298-57ae-aa0c-87b5e5a84712.htm")
```

### <a name="psonlinehelp"></a>$psOnlineHelp
 Это объект словаря, который поддерживает сопоставление с учетом контекста заголовков разделов справки и связанных внешних URL-адресов. Он используется для поиска справки для определенного раздела в Интернете. Разделы в этом списке можно добавлять и удалять.

```
$psOnlineHelp | Format-List

```

### <a name="sample-output"></a>Пример вывода

|||
|-|-|
|Ключ: Add-Computer|Значение: http://go.microsoft.com/fwlink/p/?LinkID=135194|
|Ключ: Add-Content|Значение: http://go.microsoft.com/fwlink/p/?LinkID=113278|

 Следующий сценарий добавляет запись в этот список.

```
$psOnlineHelp.Add("get-myNoun","http://www.mydomain.com/MyNoun.html")
```

## <a name="see-also"></a>См. также
- [Объектная модель скриптов интегрированной среды скриптов Windows PowerShell](../../core-powershell/ise/The-Windows-PowerShell-ISE-Scripting-Object-Model.md)

  
