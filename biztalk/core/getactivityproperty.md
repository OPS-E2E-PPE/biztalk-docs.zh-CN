---
title: "GetActivityProperty |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a55f0d24da85088fb8f13693c8c71d32bee1bef7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getactivityproperty"></a>GetActivityProperty
将提取的属性从与跟踪事件相关的活动推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 属性名称。  
  
## <a name="return-value"></a>返回值  
 包含属性值的字符串。  
  
## <a name="remarks"></a>注释  
 您可以使用以点分隔的表达式来限定希望检索的属性名称。 这会为您提供对通过属性公开的其他对象的内部对象的访问。 例如，要访问采购订单的 Address 实例的 City 属性，请使用“purchaseOrder.Address.City”。  
  
 属性名称的第一次匹配区分大小写，其余匹配不区分大小写。 在 WF 应用程序中，当两个或多个活动属性仅大小写不同时，这一点非常重要。 例如，如果工作流应用程序定义了“myWorkflow”和“MyWorkflow”属性，而您正在查找“MyWorkflow”，则会通过区分大小写匹配与第二个属性进行匹配。 如果您指定了“MYWORKFLOW”，则在区分大小写的匹配尝试失败后，会通过不区分大小写匹配与“myWorkflow”进行匹配。  
  
 例如，如果你有两个活动属性仅可由不同用例:"myProperty"和"MyProperty"。  
  
> [!NOTE]
>  Null 属性值将导致 NullReferenceException 引发回工作流实例。  
  
## <a name="example"></a>示例  
 在下面的示例中，更新表达式会用于通过使用 `GetActivityProperty` 持久化活动属性“MyProperty”。  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```