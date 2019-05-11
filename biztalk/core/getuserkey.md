---
title: GetUserKey |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9353a7f0-9bbd-4cfa-92e6-ed2b86e3a88e
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc4f163d35901a0cec9919e3053f84fd21cb712f
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65344889"
---
# <a name="getuserkey"></a>GetUserKey
将推送到堆栈上的当前用户密钥。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wf:Operation Name="GetUserKey" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含当前用户密钥的字符串。  
  
## <a name="remarks"></a>备注  
 此操作是仅在用户跟踪点中有效。  
  
## <a name="example"></a>示例  
 下面的示例包含的事件筛选器表达式的计算结果将为`true`用户密钥等于"DocumentUrl"时。  
  
```  
<ic:Filter>  
  <ic:Expression>  
    <wf:Operation Name="GetUserKey" />  
    <ic:Operation Name="Constant">  
      <ic:Argument>DocumentUrl</ic:Argument>  
    </ic:Operation>  
    <ic:Operation Name="Equals" />  
  </ic:Expression>  
</ic:Filter>  
```