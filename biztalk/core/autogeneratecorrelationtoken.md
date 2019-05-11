---
title: AutoGenerateCorrelationToken | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a24357c9-34e5-4caa-b41c-19551cfe81f9
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cf2b3fd5ea662af08cf5613570ba65c4fd1017f6
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65528902"
---
# <a name="autogeneratecorrelationtoken"></a>AutoGenerateCorrelationToken
自动生成相关标记，并将其放置到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含相关标记的字符串。  
  
## <a name="remarks"></a>备注  
 消息中出现任何相关标记，但您仍想要将请求和答复中的信息相关联时，可以使用此操作。 它可以用于将特定客户端或服务端上请求/答复相关联。  
  
> [!NOTE]
>  如果你想要将请求和答复的客户端和服务 （延续） 收集的数据相关联，您需要使用数据元素或从您的消息的元素。  
  
## <a name="example"></a>示例  
 下面的示例关联表达式依靠`AutoGenerateCorrelationToken`生成相关标记。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)