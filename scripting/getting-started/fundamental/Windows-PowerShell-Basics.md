---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,командлет"
ms.date: 2016-12-12
title: "Основы Windows PowerShell"
ms.technology: powershell
ms.assetid: 6b3cbbc8-060c-4877-b00b-7300dbbe4e28
ms.openlocfilehash: 338d11350cd9baba82df7700e9df3688259a3907
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
---
# <a name="windows-powershell-basics"></a>Основы Windows PowerShell
В графических пользовательских интерфейсах используются общие концепции, знакомые большинству пользователей. Пользователи полагаются на эти привычные интерфейсы для выполнения задач. Операционные системы предлагают пользователю графическое представление элементов, которые можно просматривать, при этом раскрывающиеся меню обычно используются для доступа к конкретной функциональности, а контекстные меню — к контекстной функциональности.

Интерфейс командной строки (CLI), такой как Windows PowerShell, должен использовать другой подход для предоставления информации, так как в нем нет меню или графических систем, чтобы помочь пользователю. Для использования команд необходимо знать их имена. Хотя можно вводить сложные команды, эквивалентные функциям в среде графического пользовательского интерфейса, необходимо ознакомиться с наиболее распространенными командами и их параметрами.

В большинстве интерфейсов командной строки нет шаблонов, помогающих пользователю освоить интерфейс. Поскольку интерфейсы CLI были первыми оболочками операционных систем, многие имена команд и параметров выбирались произвольно. Предпочтение отдавалось лаконичным, а не понятным именам. Хотя справочные системы и стандарты проектирования команд интегрированы в большинство интерфейсов CLI, они обычно рассчитаны на совместимость с самыми ранними командами. Поэтому набор команд формируется согласно решениям, принятым десятилетия назад.

Windows PowerShell ориентирована на использование имеющихся у пользователей знаний об интерфейсах CLI. В этой главе мы рассмотрим некоторые основные средства и концепции, помогающие быстро освоить Windows PowerShell. в том числе:

-   Использование Get-Command

-   Использование команд Cmd.exe и UNIX

-   Использование внешних команд

-   Использование Tab-Completion

-   Использование Get-Help

