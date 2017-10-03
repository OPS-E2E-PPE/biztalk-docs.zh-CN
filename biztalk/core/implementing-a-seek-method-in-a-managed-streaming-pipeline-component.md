---
title: "实现查找托管流式处理管道组件中的方法 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- pipeline interfaces, IStream interface
- pipeline components [custom], code samples
- IStream interface
- Seek method
ms.assetid: 2e546c41-822d-4e22-a8f6-8959072ef3d2
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b5181957f691502dcc2b09a367c31de575097d1a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="implementing-a-seek-method-in-a-managed-streaming-pipeline-component"></a>实现查找托管流式处理管道组件中的方法
本机**IStream**接口不提供一种检查将当前流的位置，因此消息引擎使用以下方法**Seek**方法。  
  
```  
pStream->Seek(0, STREAM_SEEK_CUR, &pNewPosition);  
```  
  
 此方法不移动流指针，而是查询当前位置。 因此如果你实现的管道组件的适用于 nonseekable 流，你可以使用**Stream.Seek**如以下示例所示的方法。  
  
## <a name="example"></a>示例  
  
```csharp  
override public long Seek(long offset, SeekOrigin origin)  
{  
   long pos = -1;  
  
   switch(origin)  
   {  
      case SeekOrigin.Begin :  
         pos = offset;  
         break;  
      case SeekOrigin.Current :  
         pos = Position + offset;  
         break;  
      case SeekOrigin.End :  
         break;  
   }  
  
   // We generally disallow seeking of the stream  
   // However, in unmanaged code, many people use Seek(0,CURR) to retrieve    // the current position  
   // Special case (that is, if Seek does not change position, do not   
   // throw an exception)  
   if (pos==Position)  
   {  
      return pos;  
   }  
   else  
   {  
      throw new NotSupportedException("ForwardOnlyEventingReadStream does not support Seek()");  
   }  
}  
```  
  
## <a name="see-also"></a>另请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)