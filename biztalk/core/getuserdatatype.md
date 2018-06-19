---
title: GetUserDataType |Microsoft 文档
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
ms.openlocfilehash: 5525dba034571acd91d1f3dd99f2b56069f81fc2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22246461"
---
# <a name="getuserdatatype"></a>GetUserDataType
将当前用户数据类型的名称推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetUserDataType" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含程序集限定格式的当前用户数据类型的字符串。  
  
## <a name="remarks"></a>注释  
 与不同**GetActivityType**，此操作不使用限定程序集的类名的格式; 相反，它会推送仅的类型名称：  
  
```  
MyLibrary.MyObject  
```  
  
> [!NOTE]
>  如果比较值时使用程序集限定类名格式作为常数，计算结果将始终为 `false`。  
  
## <a name="special-filter-behavior"></a>特殊筛选器行为  
 在筛选器内部执行此操作时，还将始终匹配派生的用户数据类型。  
  
## <a name="example"></a>示例  
 以下示例包含的事件筛选器表达式对 `true` 实例和派生自 `MyLibrary.MyObject` 的类的任何实例的计算结果将为 `MyLibrary.MyObject`。  
  
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