---
title: "GetUserData |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c243555b-109f-47e3-8084-ab13a8e22ac5
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 57bc0ffcefc00e9fae20c7b2c8449c21c549b377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="getuserdata"></a>GetUserData
推送到堆栈的当前用户数据。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetUserData" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前的用户数据的字符串。  
  
## <a name="remarks"></a>注释  
 此操作无效，不能在筛选器。  
  
## <a name="example"></a>示例  
 以下示例包含使用 `GetUserData` 运算的针对数据项“UserData”的更新表达式。  
  
```  
<ic:Update DataItemName="UserData" Type="NVARCHAR">  
  <ic:Expression>  
    <wf:Operation Name="GetUserData" />  
  </ic:Expression>  
</ic:Update>  
```