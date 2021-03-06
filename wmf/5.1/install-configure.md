---
title: "Установка и настройка WMF 5.1"
ms.date: 2017-01-18
keywords: PowerShell, DSC, WMF
description: 
ms.topic: article
contributor: keithb
manager: carmonm
ms.prod: powershell
ms.technology: WMF
ms.openlocfilehash: 55a2e03385b90c7631d1b0373bf85602aa7d769b
ms.sourcegitcommit: 267688f61dcc76fd685c1c34a6c7bfd9be582046
translationtype: HT
---
# <a name="install-and-configure-wmf-51"></a>Установка и настройка WMF 5.1 #


## <a name="download-and-install-the-wmf-51-package"></a>Скачать и установить пакет WMF 5.1

Скачайте пакет WMF 5.1 для той операционной системы и архитектуры, в которой будет производиться установка.

| Операционная система         | Необходимые компоненты       | Ссылки на пакеты             |
|------------------------|---------------------|---------------------------|
| Windows Server 2012 R2 | | [Win8.1AndW2K12R2-KB3191564-x64.msu](https://go.microsoft.com/fwlink/?linkid=839516)|
| Windows Server 2012     | | [W2K12-KB3191565-x64.msu](https://go.microsoft.com/fwlink/?linkid=839513)|
| Windows Server 2008 R2 | [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) | [Win7AndW2K8R2-KB3191566-x64.ZIP](https://go.microsoft.com/fwlink/?linkid=839523) | 
| Windows 8.1            |  | **x64:** [Win8.1AndW2K12R2-KB3191564-x64.msu](https://go.microsoft.com/fwlink/?linkid=839516) </br> **x86:** [Win8.1-KB3191564-x86.msu](https://go.microsoft.com/fwlink/?linkid=839521) |
| Windows 7 с пакетом обновления 1 (SP1)          | [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642) | **x64:** [Win7AndW2K8R2-KB3191566-x64.ZIP](https://go.microsoft.com/fwlink/?linkid=839523) </br> **x86:** [Win7-KB3191566-x86.ZIP](https://go.microsoft.com/fwlink/?linkid=839522)



## <a name="install-wmf-51-for-windows-server-2008-r2-and-windows-7"></a>Установить WMF 5.1 для Windows Server 2008 R2 и Windows 7

> **Примечание**. Инструкции по установке для Windows Server 2008 R2 и Windows 7 изменились и отличаются от инструкций для других пакетов. Инструкции по установке для Windows Server 2012 R2, Windows Server 2012 и Windows 8.1 см. ниже.

**Установка WMF 5.1 на Windows Server 2008 R2 и Windows 7**

1. Перейдите в папку, куда был скачан ZIP-файл. 

2. Щелкните его правой кнопкой мыши и выберите команду "Извлечь все...". ZIP-файл содержит два файла: MSU и файл скрипта Install-WMF5.1.PS1. После распаковки ZIP-файла вы можете скопировать его содержимое на любой компьютер под управлением Windows 7 или Windows Server 2008 R2.  

3. После извлечения содержимого ZIP-файла откройте PowerShell от имени администратора, а затем перейдите в папку с  
содержимым ZIP-файла. 

4. Запустите скрипт Install-Wmf5.1.ps1 в этой папке и следуйте инструкциям. Этот скрипт проверит предварительные требования на локальном компьютере: если они выполнены, он установит WMF 5.1. Предварительные требования перечислены ниже. 

Install-WMF5.1.ps1 принимает следующие параметры для упрощения автоматизации установки в Windows Server 2008 R2 и Windows 7:

- AcceptEula: если этот параметр включен, условия EULA принимаются автоматически и не будут отображены.
- AllowRestart: этот параметр можно использовать, только если указан параметр AcceptEula. Если этот параметр включен и после установки WMF 5.1 требуется перезагрузка, она будет выполнена без запроса сразу после завершения установки. 

**Предварительные требования WMF 5.1 для Windows Server 2008 R2 с пакетом обновления 1 (SP1) и Windows 7 с пакетом обновления 1 (SP1)**

Для установки WMF 5.1 на компьютере с ОС Windows Server 2008 R2 с пакетом обновления 1 (SP1) или Windows 7 с пакетом обновления 1 (SP1) необходимо следующее.
- Должен быть установлен последний пакет обновления.
- Платформа WMF 3.0 **не должна** быть установлена. Установка WMF 5.1 поверх WMF 3.0 приведет к потере PSModulePath, что может вызвать сбой других приложений. Перед установкой WMF 5.1 нужно удалить WMF 3.0 или сохранить PSModulePath и восстановить его вручную после установки WMF 5.1. 
- Для WMF 5.1 требуется платформа [.NET Framework 4.5.2](https://www.microsoft.com/en-ca/download/details.aspx?id=42642). Вы можете установить Microsoft .NET Framework 4.5.2, следуя инструкциям по месту скачивания.

**Зависимость WinRM** 

Служба настройки требуемого состояния (DSC) Windows PowerShell зависит от WinRM. По умолчанию WinRM не включен в Windows Server 2008 R2 и Windows 7. Чтобы включить WinRM, выполните команду `Set-WSManQuickConfig` в сеансе Windows PowerShell с повышенными привилегиями.


## <a name="install-wmf-51-for-windows-server-2012-r2-windows-server-2012-and-windows-81"></a>Установка WMF 5.1 для Windows Server 2012 R2, Windows Server 2012 и Windows 8.1
**Установка из проводника**

1. Перейдите в папку, куда был скачан MSU-файл.

2. Дважды щелкните этот файл для его запуска.

**Установка из командной строки**

1. После скачивания подходящего пакета для архитектуры вашего компьютера откройте окно командной строки с повышенными правами (используйте "Запуск от имени администратора"). При выборе варианта "Установка основных серверных компонентов" для Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 с пакетом обновления 1 (SP1) командная строка по умолчанию открывается с повышенными правами.

2. Перейдите в папку, куда был скачан или скопирован пакет установки WMF 5.1.

3. Выполните одну из следующих команд:
    - На компьютерах с ОС Windows Server 2012 R2 или Windows 8.1 (64-разрядная версия) выполните команду `Win8.1AndW2K12R2-KB3191564-x64.msu /quiet`.
    - На компьютерах с ОС Windows Server 2012 выполните команду `W2K12-KB3191565-x64.msu /quiet`.
    - На компьютерах с ОС Windows 8.1 (32-разрядная версия) выполните команду `Win8.1-KB3191564-x86.msu /quiet`.
    
