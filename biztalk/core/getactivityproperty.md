---
title: GetActivityProperty | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2321f1ec-d98d-478f-bb1d-a11a98e60fa5
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9ca7eef66216eb8a3a2aae79d34fa7619ef96ef3
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65345097"
---
# <a name="getactivityproperty"></a>GetActivityProperty
将推送到堆栈上的跟踪事件与相关的活动提取的属性。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetActivityProperty">  
      <wf:Argument>Arg1</wf:Argument>  
</wf:Operation>  
```  
  
#### <a name="parameters"></a>Parameters  
 属性的名称。  
  
## <a name="return-value"></a>返回值  
 包含属性的值的字符串。  
  
## <a name="remarks"></a>备注  
 对符合条件的你想要检索的属性名称，可以使用点分表示法。 这将提供对通过属性公开的其他对象的内部对象的访问。 例如，若要访问采购订单的 Address 实例的 City 属性，请使用"purchaseOrder.Address.City"。  
  
 属性名称均区分大小写第一个，并区分大小写。 有两个或多个只是在 WF 应用程序中的大小写不同的活动属性时，这很重要。 例如，如果工作流应用程序具有的属性"了 myWorkflow"和"myworkflow 进行"定义，并且您正在查找"myworkflow"进行，它会通过区分大小写的匹配项的第二个属性上匹配。 如果指定了"MYWORKFLOW"，它区分大小写的匹配尝试失败后，会与"myworkflow"通过不区分大小写的匹配项进行。  
  
 例如，如果您有两个活动属性仅可由不同的情况下:"myProperty"和"MyProperty"。  
  
> [!NOTE]
>  属性为空值将导致 NullReferenceException 引发回工作流实例。  
  
## <a name="example"></a>示例  
 在下面的示例中，更新表达式用于通过使用持久化活动属性"MyProperty" `GetActivityProperty`。  
  
```  
<ic:Update DataItemName="TextData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetActivityProperty">  
      <wf:Argument>MyProperty</wf:Argument>  
    </wf:Operation>  
  </ic:Expression>  
</ic:Update>  
```