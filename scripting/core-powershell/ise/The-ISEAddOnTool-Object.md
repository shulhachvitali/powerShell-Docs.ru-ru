---
description: 
manager: carmonm
ms.topic: article
author: jpjofre
ms.prod: powershell
keywords: "powershell,командлет"
ms.date: 2016-12-12
title: "Объект ISEAddOnTool"
ms.technology: powershell
ms.assetid: ce84d8bc-07ba-41f6-bdde-d6f3fddcd1e3
ms.openlocfilehash: c1ab4220fdede7cabec99fd2d9dfb39648503f28
ms.sourcegitcommit: 8acbf9827ad8f4ef9753f826ecaff58495ca51b0
translationtype: HT
---
# <a name="the-iseaddontool-object"></a>Объект ISEAddOnTool
  Объект **ISEAddonTool** — это устанавливаемая надстройка, расширяющая функциональные возможности интегрированной среды сценариев Windows PowerShell. В качестве примера можно привести средство **Commands**, которое отображается, если выбрать **Вид**, а затем **Show Command Add-on** (Показать настройку Command). После этого средство становится доступным за счет манипуляций с различными доступными объектами **ISEAddOnTool**.

 Каждую надстройку можно связать с вертикальной или горизонтальной панелью. Вертикальная область прикрепляется к правому краю интегрированной среды сценариев Windows PowerShell. Горизонтальная панель прикрепляется к нижнему краю.

 Каждая вкладка PowerShell в интегрированной среде сценариев Windows PowerShell может содержать собственный набор установленных надстроек. Доступ к коллекции средств, доступных для выбранной вкладки, или к свойствам одного из объектов **PowerShellTab** в объекте коллекции [$psISE.PowerShellTabs](The-PowerShellTabCollection-Object.md) рассматривается в статьях [$psISE.CurrentPowerShellTab.HorizontalAddOnTools](The-ISEAddOnToolCollection-Object.md) и [$psISE.CurrentPowerShellTab.VerticalAddOnTools](The-ISEAddOnToolCollection-Object.md).

## <a name="methods"></a>Методы
 Для объектов этого класса нет доступных методов интегрированной среды сценариев Windows PowerShell.

## <a name="properties"></a>Свойства

###  <a name="a-namecontrola-control"></a><a name="Control"></a> Control
  Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

 Свойство **Control** обеспечивает доступ для чтения ко множеству сведений надстройки Command.

```
# View the properties of the Commands add-on tool.
# (assumes that it is visible in the vertical pane)
$psISE.CurrentVisibleVerticalTool.Control
HostObject                  : Microsoft.PowerShell.Host.ISE.ObjectModelRoot
Content                     :
HasContent                  :
ContentTemplate             :
ContentTemplateSelector     :
ContentStringFormat         :
BorderBrush                 :
BorderThickness             :
Background                  :
Foreground                  :
FontFamily                  :
FontSize                    :
FontStretch                 :
FontStyle                   :
FontWeight                  :
HorizontalContentAlignment  :
VerticalContentAlignment    :
TabIndex                    :
IsTabStop                   :
Padding                     :
Template                    : System.Windows.Controls.ControlTemplate
Style                       :
OverridesDefaultStyle       :
UseLayoutRounding           :
Triggers                    : {}
TemplatedParent             :
Resources                   : {System.Windows.Controls.TabItem}
DataContext                 :
BindingGroup                :
Language                    :
Name                        :
Tag                         :
InputScope                  :
ActualWidth                 : 370.75
ActualHeight                : 676.559097412109
LayoutTransform             :
Width                       :
MinWidth                    :
MaxWidth                    :
Height                      :
MinHeight                   :
MaxHeight                   :
FlowDirection               : LeftToRight
Margin                      :
HorizontalAlignment         :
VerticalAlignment           :
FocusVisualStyle            :
Cursor                      :
ForceCursor                 :
IsInitialized               : True
IsLoaded                    :
ToolTip                     :
ContextMenu                 :
Parent                      :
HasAnimatedProperties       :
InputBindings               :
CommandBindings             :
AllowDrop                   :
DesiredSize                 : 227.66,676.559097412109
IsMeasureValid              : True
IsArrangeValid              : True
RenderSize                  : 370.75,676.559097412109
RenderTransform             :
RenderTransformOrigin       :
IsMouseDirectlyOver         : False
IsMouseOver                 : False
IsStylusOver                : False
IsKeyboardFocusWithin       : False
IsMouseCaptured             :
IsMouseCaptureWithin        : False
IsStylusDirectlyOver        : False
IsStylusCaptured            :
IsStylusCaptureWithin       : False
IsKeyboardFocused           : False
IsInputMethodEnabled        :
Opacity                     :
OpacityMask                 :
BitmapEffect                :
Effect                      :
BitmapEffectInput           :
CacheMode                   :
Uid                         :
Visibility                  : Visible
ClipToBounds                : False
Clip                        :
SnapsToDevicePixels         : False
IsFocused                   :
IsEnabled                   :
IsHitTestVisible            :
IsVisible                   : True
Focusable                   :
PersistId                   : 1
IsManipulationEnabled       :
AreAnyTouchesOver           : False
AreAnyTouchesDirectlyOver   :
AreAnyTouchesCapturedWithin : False
AreAnyTouchesCaptured       :
TouchesCaptured             : {}
TouchesCapturedWithin       : {}
TouchesOver                 : {}
TouchesDirectlyOver         : {}
DependencyObjectType        : System.Windows.DependencyObjectType
IsSealed                    : False
Dispatcher                  : System.Windows.Threading.Dispatcher

```

###  <a name="a-nameisvisiblea-isvisible"></a><a name="IsVisible"></a> IsVisible
  Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

 Логическое свойство, которое определяет видимость надстройки в соответствующей области. Если она видна, свойству **IsVisible** можно присвоить значение **$false**, чтобы скрыть средство, или ******$true**, чтобы оно отображалось на вкладке PowerShell. Обратите внимание, что к скрытой надстройке нельзя получить доступ с помощью объекта **CurrentVisibleHorizontalTool** или **CurrentVisibleVerticalTool**, а значит, ее нельзя сделать видимой, используя данное свойство объекта.

```
# Hide the current tool in the vertical tool pane
$psISE.CurrentVisibleVerticalTool.IsVisible = $false
# Show the first tool on the currently selected PowerShell tab
$psISE.CurrentPowerShellTab.VerticalAddOnTools[0].IsVisible=$true

```

###  <a name="a-namenamea-name"></a><a name="name"></a> Name
  Поддерживается в интегрированной среде сценариев Windows PowerShell 3.0 и более поздних версия и отсутствует в более ранних версиях.

 Свойство только для чтения, которое получает имя надстройки.

```
# Gets the name of the visible vertical pane add-on tool.
$psISE.CurrentVisibleVerticalTool.name
Commands

```

## <a name="see-also"></a>См. также
- [Объект ISEAddOnToolCollection](The-ISEAddOnToolCollection-Object.md)
- [Объектная модель скриптов интегрированной среды скриптов Windows PowerShell](The-Windows-PowerShell-ISE-Scripting-Object-Model.md)
- [Справочник по объектной модели интегрированной среды скриптов Windows PowerShell](Windows-PowerShell-ISE-Object-Model-Reference.md)
- [Иерархия объектной модели интегрированной среды скриптов](The-ISE-Object-Model-Hierarchy.md)

