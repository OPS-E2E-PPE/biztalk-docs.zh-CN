---
title: "常见的事件筛选器模式 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ef90a4533b8b12929488d3a323dae47976eace0a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="common-event-filter-patterns"></a>常用事件筛选模式
使用用于 Windows Workflow Foundation (WF) 的 BAM 侦听器时，您可能会注意到，在侦听器配置文件中存在一组频繁使用的常用筛选模式。 虽然其中的某些筛选模式对于应用程序和环境而言是唯一的，但许多模式可跨环境和在不同的应用程序中使用。  
  
 本主题收集了许多针对 WF 应用程序编写的侦听器配置文件所使用的常用筛选模式。 这些模式将按如下 Windows Workflow Foundation 跟踪事件进行分组：  
  
-   活动状态事件  
  
-   工作流状态事件  
  
-   用户事件  
  
 可以将每种模式复制到侦听器配置文件中并进行修改使其适合您的应用程序。  
  
## <a name="activity-status-event-filter-patterns"></a>活动状态事件筛选模式  
 活动是工作流的基本构造块。 工作流是树结构中按层次结构组织的一组活动。 一个活动代表工作流中的一个操作。 它可以是一个简单操作（如延迟），也可以是一个包含多个子活动的复合活动。  
  
 本部分中的筛选器将使用以下一个或多个针对 WF 的 BAM 侦听器的自定义操作对活动进行筛选：  
  
-   GetActivityName  
  
-   GetActivityEvent  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
> [!NOTE]
>  如果在筛选器中不使用 GetActivityEvent 操作，则筛选器将仅查找“已关闭”的活动事件。  
  
### <a name="filter-by-activity-name-closed-activity"></a>按活动名筛选（关闭的活动）  
 您将经常需要按活动名筛选关闭的活动事件。 当您需要捕获特定活动（如接收文件或将数据写入数据库）中的数据时，此筛选器将非常有用。  
  
 下面的片断将筛选名为“MyActivity”的关闭活动。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-closed-activity-event"></a>按活动类型筛选（关闭的活动事件）  
 有时，您可能希望按类型而不是按名称筛选活动。 例如，您可能希望将所有活动的活动名和日期/时间戳都保存在工作流中。 若要实现此目的，你可以使用`GetActivityType`操作。 `GetActivityType`比较提供的类型，针对要确定匹配的基类型和所有派生的类型。 将与进行比较`System.Workflow.ComponentModel.Activity`由于所有工作流活动必须派生自它将与匹配。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-event-any-activity-type"></a>按活动事件筛选（任意活动类型）  
 此筛选器使用 GetActivityEvent 操作查找关闭的活动。 捕获有关所有关闭事件的信息时，此筛选器将非常有用（与按名称或类型的特定事件相比较而言）。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a>按活动名和类型筛选（关闭的活动事件）  
 如果要指定想要查找的活动的精确类型（其中包括处理器结构），可以选择按活动名和活动类型筛选活动。 下面的示例将查找从 `System.Workflow.ComponentModel.Activity` 派生的“MyActivity”；可以将此活动更改为派生类型以进一步限制查找范围。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
<ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a>按活动名和事件筛选（任意活动类型）  
 此表达式将基于活动名和活动事件进行筛选。 当您希望捕获有关特定活动和事件的信息时，或捕获多个活动事件中有关给定活动的数据时，此筛选器将非常有用。 例如，您可能需要两个不同的 OnEvent 元素，一个用于“正在执行”时的 MyActivity，另一个用于“已关闭”时的 MyActivity，如下所示。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-event"></a>按活动类型和事件筛选  
 当在单个活动事件期间捕获有关从特定类型派生的所有活动的信息时，此筛选器将非常有用。 例如，当采购订单通过工作流时，您可能希望跟踪采购订单中的采购订单 ID 和日期/时间戳。 若要实现此目的，你可以使用`GetActivityEvent`和`GetActivityType`操作。 `GetActivityType`比较提供的类型，针对要确定匹配的基类型和所有派生的类型。 将与进行比较`System.Workflow.ComponentModel.Activity`由于所有工作流活动必须派生自它将与匹配。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-type-and-event"></a>按活动名、类型和事件筛选  
 当您希望进一步限定想要跟踪的活动时，按名称、类型和事件筛选活动将非常有用。 例如，下面的筛选器将查找关闭的活动“MyActivity”，该活动将具有等效于 `System.Workflow.ComponentModel.Activity` 或从其派生的类型。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Closed</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="workflow-status-event-filter-patterns"></a>工作流状态事件筛选模式  
 本部分中的筛选器将使用以下一个或多个针对 WF 的 BAM 侦听器的自定义操作对工作流事件进行筛选：  
  
-   GetWorkflowEvent  
  
-   GetContextProperty  
  
### <a name="filter-by-workflow-event"></a>按工作流事件筛选  
 此表达式将按工作流事件进行筛选。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowEvent" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>Created</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="user-event-filter-patterns"></a>用户事件筛选模式  
 如果您的应用程序使用 TrackData 方法跟踪自定义信息，则您可以使用以下一个或多个针对 WF 的 BAM 侦听器的自定义用户数据操作基于数据特性对信息进行筛选：  
  
-   GetUserDataType  
  
-   GetUserKey  
  
-   GetUserData  
  
 该筛选器可以将上述操作与下列操作组合起来，以创建更为复杂的表达式：  
  
-   GetActivityName  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
 如果筛选器不包括任何用户数据操作，则该筛选器不是用户事件筛选器，并且封闭的 OnEvent 将导致错误（如果用户操作出现在相应的更新表达式中）或将被标识为活动跟踪点而非用户跟踪点。  
  
### <a name="filter-by-activity-name-and-user-data-type"></a>按活动名和用户数据类型筛选  
 通常，您可以按活动名和用户数据类型标识事件。 下面的表达式将筛选名为“MyActivity”的活动和一个从 `System.Object` 派生的用户数据类型。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-data-type"></a>按活动类型和用户数据类型筛选  
 可以基于活动类型和用户数据类型进行筛选。 这将授予你筛选事件的纬度基于类型从派生因为同时`GetActivityType`和`GetUserDataType`针对的指定类型和所有派生的类型的比较。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a>按活动名、活动类型和用户数据类型筛选  
 此筛选器将通过包含活动名来进一步限制活动类型和用户数据类型筛选模式。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-and-user-key"></a>按活动名和用户密钥筛选  
 如果你的应用程序具有调用的活动`TrackData`在运行时确定的密钥，你可能想要按活动名称和用户密钥进行筛选。 这将使你能够触发`OnEvent`基于特定的密钥值。 例如，您的应用程序可能定义了多个密钥，并在活动内动态选择一个密钥。  
  
 下面的表达式将筛选包含名为“ItemKey”用户密钥的“MyActivity”。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-and-user-key"></a>按活动类型和用户密钥筛选  
 如果您的应用程序包含多个使用运行时确定的密钥调用 `TrackData` 的活动，您可能希望按活动名和用户密钥进行筛选。 这将使你能够触发`OnEvent`基于特定的密钥值。 例如，您的应用程序可能定义了多个密钥，并在活动内动态选择一个密钥。  
  
 下面的表达式将筛选从包含名为“ItemKey”用户密钥的 `System.Workflow.ComponentModel.Activity` 派生的任意活动。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>ItemKey</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a>按活动名、活动类型和用户密钥筛选  
 此筛选模式将通过在筛选器中包含活动名来进一步限制活动类型和用户密钥筛选模式。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a>按活动名、用户数据类型和用户密钥筛选  
 当您希望将筛选器限制为筛选包含特定用户密钥并从特定数据类型派生的指定活动时，此筛选器将非常有用。 例如，您的活动可能使用密钥“Item”和字符串或整数（取决于项类型）的数据值来调用 TrackData。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a>按活动类型、用户数据类型和用户密钥筛选  
 当您希望将筛选器限制为筛选包含特定用户密钥并从特定数据类型派生的活动类型时，此筛选器将非常有用。 相对于使用活动名、用户数据类型和用户密钥的筛选器，此筛选器可以具有较强或较弱限制性（取决于所使用的类型）。 如果您指定派生程度最高的类型，则此筛选器可以具有较强限制性；如果您指定根基本类型，则此筛选器可以具有较弱限制性。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>  
```  
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a>按活动名、活动类型、用户数据类型和用户密钥筛选  
 此筛选器将通过添加活动名来进一步限制活动类型、用户数据类型和用户密钥筛选模式。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Workflow.ComponentModel.Activity, System.Workflow.ComponentModel, Version=3.0.0.0, Culture=neutral, PublicKeyToken=31bf3856ad364e35, processorArchitecture=MSIL</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <wf:Operation Name="GetActivityName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyActivity</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>System.Object</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>key</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
    <ic:Operation Name="And" />  
  </ic:Expression>  
</ic:Filter>   
```