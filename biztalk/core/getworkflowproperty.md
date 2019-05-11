---
title: GetWorkflowProperty |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c9d3029e-3267-46bc-ba2e-1c6fa1f2e931
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 53e31ea557508164bd5e434558ebdf6bb0689a7c
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344910"
---
# <a name="getworkflowproperty"></a>GetWorkflowProperty
推送到堆栈上的工作流的根活动中提取的属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 属性的名称。  
  
## <a name="pushed-value"></a>推送的值  
 包含属性的值的字符串。  
  
## <a name="remarks"></a>备注  
 此操作只是在更新中有效。  
  
 对符合条件的你想要检索的属性名称，可以使用点分表示法。 这将提供对通过属性公开的其他对象的内部对象的访问。 例如，若要访问采购订单的 Address 实例的 City 属性，请使用"purchaseOrder.Address.City"。  
  
 属性名称均区分大小写第一个，并区分大小写。 有两个或多个只是在 WF 应用程序中的大小写不同的活动属性时，这很重要。 例如，如果工作流应用程序具有的属性"了 myWorkflow"和"myworkflow 进行"定义，并且您正在查找"myworkflow"进行，它会通过区分大小写的匹配项的第二个属性上匹配。 如果指定了"MYWORKFLOW"，它将匹配了"myWorkflow"通过匹配区分大小写，不区分大小写的匹配尝试失败后。  
  
> [!NOTE]
>  属性为空值将导致 NullReferenceException 引发回工作流实例。  
  
## <a name="example"></a>示例  
 在以下示例中，更新表达式用于通过使用保留从采购订单的工作流属性"City" `GetWorkflowProperty`。  
  
```  
<ic:Update DataItemName="City" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetWorkflowProperty">  
      <wf:Argument>po.Info.City</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```