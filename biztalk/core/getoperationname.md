---
title: GetOperationName | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: f858269c-d412-43e3-85e1-398afa9375ab
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 92eba73898b08e89cd1c3c7cdbd5f65c14ba048f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387678"
---
# <a name="getoperationname"></a>GetOperationName
将当前操作的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="GetOperationName" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前操作名称的字符串。  
  
## <a name="remarks"></a>备注  
 如果使用 GetOperationName，请确保在应用程序调用它时对操作名称进行比较。 例如，如果使用服务约定上的名称属性来指定自定义名称，客户端将具有使用该方法的自定义名称生成的默认代理。 但是，服务器应用程序将使用对应操作的实际方法名称，而不是在名称属性中指定的名称。  
  
## <a name="example"></a>示例  
 在下面的示例中，`GetOperationName` 用于生成一个可筛选名称为“AuthorizePayment”的操作的表达式。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wcf:Operation Name="GetOperationName" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>AuthorizePayment</ic:Argument>  
    </ic:Operation>  
  </ic:Expression>  
</ic:Filter>  
```  
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)