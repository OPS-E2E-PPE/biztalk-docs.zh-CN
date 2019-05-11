---
title: GetUserDataType |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b0605919-a733-4a9d-a725-109346db11a2
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78fb7766363b212e6d913565d43f07500b0d1340
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65387642"
---
# <a name="getuserdatatype"></a>GetUserDataType
将推送到堆栈上的当前用户数据类型的名称。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含程序集限定格式中的当前用户数据类型的字符串。  
  
## <a name="remarks"></a>备注  
 与不同**GetActivityType**，此操作不使用程序集限定类名格式; 相反，它将推送仅类型名称：  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  如果使用程序集限定类名格式，如常量比较值时将计算结果始终为`false`。  
  
## <a name="special-filter-behavior"></a>特殊筛选器行为  
 在筛选器内部执行此操作时，派生的用户数据还将始终匹配类型。  
  
## <a name="example"></a>示例  
 下面的示例包含的事件筛选器表达式的计算结果将为`true`有关`MyLibrary.MyObject`实例和任何实例派生的类的`MyLibrary.MyObject`。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserDataType" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>MyLibrary.MyObject</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```