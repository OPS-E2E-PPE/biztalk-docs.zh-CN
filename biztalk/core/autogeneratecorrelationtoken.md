---
title: AutoGenerateCorrelationToken |Microsoft 文档
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
ms.openlocfilehash: 2e396fd0b2c6153a5252d336b9af9c22bf9421fd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230253"
---
# <a name="autogeneratecorrelationtoken"></a>AutoGenerateCorrelationToken
自动生成相关标记，并将其放到堆栈上。  
  
## <a name="syntax"></a>语法  
  
```  
  
<wcf:Operation Name="AutoGenerateCorrelationToken" />  
```  
  
#### <a name="parameters"></a>Parameters  
 无。  
  
## <a name="pushed-value"></a>推送的值  
 包含相关标记的字符串。  
  
## <a name="remarks"></a>注释  
 当没有相关标记的消息中存在，但你仍想要关联请求和答复中的信息时，可以使用此操作。 它可以用于将特定客户端或服务端上请求/答复关联起来。  
  
> [!NOTE]
>  如果你想要关联的请求和答复的客户端和服务 （延续） 收集的数据，你将需要使用的数据元素或从你的消息的元素。  
  
## <a name="example"></a>示例  
 下面的示例关联表达式依靠 `AutoGenerateCorrelationToken` 来生成相关标记。  
  
```  
<ic:CorrelationID>  
  <ic:Expression>            
    <wcf:Operation Name="AutoGenerateCorrelationToken"/>  
  </ic:Expression>  
</ic:CorrelationID>  
```  
  
## <a name="see-also"></a>另请参阅  
 [Windows Communication Foundation 中的操作](../core/operations-in-windows-communication-foundation.md)