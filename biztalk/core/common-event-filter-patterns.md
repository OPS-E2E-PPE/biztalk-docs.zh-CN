---
title: 常用事件筛选模式 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fc80168b-25bd-4228-b84c-d38bf4e2fe4a
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 05a81dcac4e7bd43a0a60e042d285c56a9fcc35c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65357133"
---
# <a name="common-event-filter-patterns"></a>常用事件筛选模式
使用 BAM 侦听器用于 Windows Workflow Foundation (WF) 工作时，你将很可能会有一组常用筛选模式，您将使用经常在侦听器配置文件中。 某些筛选模式将是唯一的应用程序和环境，而许多模式可用于跨环境和在不同的应用程序。  
  
 本主题收集了许多针对 WF 应用程序编写的侦听器配置文件所使用的常用筛选模式。 Windows Workflow Foundation 跟踪事件进行分组模式：  
  
- 活动状态事件  
  
- 工作流状态事件  
  
- 用户事件  
  
  每个模式可以复制到您的侦听器配置文件并修改使其适合你的应用程序。  
  
## <a name="activity-status-event-filter-patterns"></a>活动状态事件筛选模式  
 活动是工作流的基本构建基块。 工作流是一组在树结构中按层次结构组织的活动。 活动表示在工作流中的操作。 它可以是一个简单的操作 （如延迟），也可以是包含多个子活动的复合活动。  
  
 在本部分中的筛选器筛选活动和一个或多个以下的 BAM 侦听器的 WF 自定义操作的用法：  
  
-   GetActivityName  
  
-   GetActivityEvent  
  
-   GetActivityType  
  
-   GetActivityProperty  
  
-   GetWorkflowProperty  
  
-   GetContextProperty  
  
> [!NOTE]
>  如果在筛选器中不使用 GetActivityEvent 操作，你的筛选器将查找仅限于已关闭的活动事件。  
  
### <a name="filter-by-activity-name-closed-activity"></a>按活动名 （已关闭的活动） 筛选  
 经常需要按活动名筛选关闭的活动事件。 当您需要捕获特定活动，如接收文件或向数据库写入数据的数据时，这很有用。  
  
 下面的筛选器已关闭的活动的片断将名为"MyActivity"。  
  
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
  
### <a name="filter-by-activity-type-closed-activity-event"></a>按活动类型 （已关闭的活动事件） 进行筛选  
 将您想要筛选的活动类型而不是名称。 例如，你可能想要将活动名称和所有活动的日期/时间戳保存在工作流中。 若要完成此操作，请使用`GetActivityType`操作。 `GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。 比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。  
  
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
  
### <a name="filter-by-activity-event-any-activity-type"></a>按活动事件 （任意活动类型） 进行筛选  
 此筛选器使用 GetActivityEvent 操作查找关闭的活动。 它可用于捕获 （而不是按名称或类型的特定事件） 的所有已关闭事件的相关信息。  
  
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
  
### <a name="filter-by-activity-name-and-type-closed-activity-event"></a>按活动名筛选，并键入 （已关闭的活动事件）  
 您可以选择要筛选活动按活动名和活动类型，如果你想要指定您是想要查找的活动 （包括处理器体系结构） 的确切类型。 下面的示例将查找"MyActivity"派生自`System.Workflow.ComponentModel.Activity`; 你可以更改为派生类型以使其更具限制性。  
  
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
  
### <a name="filter-by-activity-name-and-event-any-activity-type"></a>按活动名和事件 （任意活动类型） 筛选  
 此表达式筛选器基于活动名和活动事件。 如果想要捕获特定活动和事件的信息或捕获多个给定活动的活动事件中的数据时，这非常有用。 例如，你可能想两个不同的 OnEvent 元素，一个用于 MyActivity 时正在执行另一个用于时关闭，如下所示。  
  
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
 此筛选器可用于捕获有关单个活动事件期间从特定类型派生的所有活动的信息。 例如，您可以根据兴趣参阅跟踪采购订单 ID 和日期/时间戳从采购订单通过工作流中流动。 若要完成此操作，请使用`GetActivityEvent`和`GetActivityType`操作。 `GetActivityType` 比较提供的类型与基类型和所有派生的类型来确定匹配。 比较`System.Workflow.ComponentModel.Activity`将匹配，因为必须从其派生所有工作流活动。  
  
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
  
### <a name="filter-by-activity-name-type-and-event"></a>按活动名、 类型和事件筛选  
 按名称筛选活动，类型和事件可在你想要更好地限定您感兴趣跟踪的活动。 例如，下面的筛选器查找已关闭的活动具有等于或派生的类型的"MyActivity" `System.Workflow.ComponentModel.Activity`。  
  
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
 在本部分中的筛选器筛选工作流事件并使用一个或多个以下的 BAM 侦听器的 WF 自定义操作：  
  
-   GetWorkflowEvent  
  
-   GetContextProperty  
  
### <a name="filter-by-workflow-event"></a>按工作流事件筛选  
 此表达式将筛选由工作流事件。  
  
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
 如果你的应用程序跟踪使用 TrackData 方法的自定义信息，您可以筛选使用一个或多个以下的 BAM 侦听器的 WF 自定义用户数据操作的数据的特征：  
  
- GetUserDataType  
  
- GetUserKey  
  
- GetUserData  
  
  筛选器可以组合这些操作与以下内容，以创建更复杂的表达式：  
  
- GetActivityName  
  
- GetActivityType  
  
- GetActivityProperty  
  
- GetWorkflowProperty  
  
- GetContextProperty  
  
  如果你的筛选器不包括至少一个用户数据操作，你的筛选器不会用户事件筛选器并且封闭的 OnEvent 将导致错误 （如果用户操作出现在相应的更新表达式中） 或将被标识为活动跟踪点而不是用户跟踪点。  
  
### <a name="filter-by-activity-name-and-user-data-type"></a>按活动名和用户数据类型筛选  
 经常可以确定按活动名和用户数据类型的事件。 以下表达式筛选器的名为"MyActivity"和用户数据类型派生的活动`System.Object`。  
  
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
  
### <a name="filter-by-activity-type-and-user-data-type"></a>按活动类型和用户数据类型进行筛选  
 您可以筛选基于活动类型和用户数据类型。 这将授予你筛选事件纬度根据类型从其派生因为两者`GetActivityType`和`GetUserDataType`与指定的类型及所有派生的类型的比较。  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-data-type"></a>按活动名、 活动类型和用户数据类型筛选  
 此筛选器进一步通过包含活动名来限制活动类型和用户数据类型筛选器模式。  
  
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
 如果你的应用程序具有调用的活动`TrackData`与在运行时确定的密钥，你可能希望按活动名和用户密钥筛选。 这样，便可触发`OnEvent`基于特定密钥值。 例如，你的应用程序可能会定义多个键，并动态选择一个活动中。  
  
 下面的筛选器的表达式将为"MyActivity"包含用户键名为"ItemKey"。  
  
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
 如果你的应用程序包含多个活动可调用`TrackData`与在运行时确定的密钥，你可能希望按活动名和用户密钥筛选。 这样，便可触发`OnEvent`基于特定密钥值。 例如，你的应用程序可能会定义多个键，并动态选择一个活动中。  
  
 下面从派生的任意活动的筛选器的表达式将`System.Workflow.ComponentModel.Activity`包含用户键名为"ItemKey"。  
  
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
  
### <a name="filter-by-activity-name-activity-type-and-user-key"></a>按活动名、 活动类型和用户密钥筛选  
 此筛选器模式进一步改进活动类型和用户密钥筛选模式通过将活动名称包含在筛选器中。  
  
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
  
### <a name="filter-by-activity-name-user-data-type-and-user-key"></a>按活动名、 用户数据类型和用户密钥筛选  
 此筛选器是你想要使用特定用户密钥的指定活动限制你的筛选器时很有用并从特定的数据类型派生。 例如，您的活动可以调用 TrackData 使用密钥"Item"和字符串或整数取决于项类型的数据值。  
  
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
  
### <a name="filter-by-activity-type-user-data-type-and-user-key"></a>按活动类型、 用户数据类型和用户密钥筛选  
 此筛选器会非常有用，当你想要将活动类型筛选器限制包含特定用户密钥并从特定的数据类型派生。 它可以是限制性更强或较弱限制性比使用活动名、 用户数据类型和用户密钥基于所使用的类型。 如果指定的派生程度最高的类型，则可能是限制性更强;如果指定根基本类型，则可能是限制性较弱。  
  
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
  
### <a name="filter-by-activity-name-activity-type-user-data-type-and-user-key"></a>按活动名、 活动类型、 用户数据类型和用户密钥筛选  
 此筛选器进一步限制活动类型、 用户数据类型和用户密钥模式通过添加活动名。  
  
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