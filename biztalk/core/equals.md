---
title: 等于 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ac93031a-9d18-443d-9e38-71ef9edd5a30
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2b82ac5c779dc6b4d3624b48cebe9df1bc3d1966
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22239813"
---
# <a name="equals"></a>等于
删除堆栈最上方的两项，比较这两项，然后将结果推送到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<ic:Operation Name="Equals" />  
```  
  
#### <a name="parameters"></a>Parameters  
 堆栈最上方的两项。  
  
## <a name="pushed-value"></a>推送的值  
 比较操作的字符串结果。  
  
## <a name="remarks"></a>注释  
  
## <a name="example"></a>示例  
 下面的示例筛选器表达式使用**等于**操作进行比较到常量"CheckPO"的当前活动名称。 如果两者相等，则表达式的计算结果为 `true`。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetActivityName"/>  
    <ic:Operation Name="Constant">  
      <ic:Argument>CheckPO</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals"/>  
  </ic:Expression>  
</ic:Filter>  
```  
  
 执行比较时，如果您在 C# 中写入语句，则可以确切地指引您生成表达式。 例如，您可能要比较三个值；可在 C# 中会写入类似如下的语句：  
  
```  
bool res = a == b == c;  
```  
  
 但是，作为表达式筛选器的模型，此语句有些短。 因此，可以考虑下面修改后（但等效）的语句：  
  
```  
Bool res = (a == b) && (a == c);  
```  
  
 这与您用来执行比较的筛选器表达式更加匹配。 有关更多详细信息及示例，请参阅[和](../core/and.md)。  
  
## <a name="see-also"></a>另请参阅  
 [拦截器操作](../core/interceptor-operations.md)