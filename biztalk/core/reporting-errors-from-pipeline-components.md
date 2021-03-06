---
title: 报告来自管道组件的错误 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- IErrorInfo object
- pipeline components [custom], errors
- SetErrorInfo method
- Exception object
ms.assetid: ad7c519e-829a-4a92-a42f-3e367d5dbaa8
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 043ecab38e664d332ab10018d28189db8bb0277d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65397887"
---
# <a name="reporting-errors-from-pipeline-components"></a>报告来自管道组件的错误
管道组件以两种方式报告错误：  
  
-   有关。基于 NET 的组件，通过引发异常。  
  
-   对于基于 COM 的组件，通过设置**ErrorInfo**对象并返回失败 HRESULT。  
  
## <a name="reporting-errors-from-net-pipeline-components"></a>报告来自.NET 管道组件的错误  
 报告错误。基于 NET 的管道组件需要引发异常，以便报告的错误说明。 若要报告引发错误的组件的名称，设置**源**的属性**异常**对象。  
  
 消息引擎将使用**消息**并**源**的属性**异常**对象来报告错误。 以下消息写入事件日志：  
  
 "出现故障执行 [接收&#124;发送] 管道：\<管道名称\>源：\<源\>[接收位置&#124;发送端口:]\<位置&#124;端口名称\>原因：\<消息\>。"  
  
## <a name="reporting-errors-from-com-pipeline-components"></a>报告来自 COM 管道组件的错误  
 若要报告错误，基于 COM 的管道组件，请执行以下操作：  
  
1. 管道组件集**IErrorInfo**对象通过调用**SetErrorInfo**方法。  
  
2. 管道组件返回到消息引擎失败的 HRESULT。  
  
   消息引擎将使用**GetSource**并**GetDescription**的属性**IErrorInfo**对象来报告错误。 如果未设置源，则使用该组件的名称。 如果在说明不组或整个**ErrorInfo**未设置对象，则返回的 HRESULT 报告而不是说明。 以下消息写入事件日志：  
  
   "出现故障执行 [接收&#124;发送] 管道：\<管道名称\>源：\<GetSource\> [接收位置&#124;发送端口:]\<位置&#124;端口名称\>原因：\<GetDescription 或 HRESULT\>。"  
  
## <a name="see-also"></a>请参阅  
 [开发自定义管道组件](../core/developing-custom-pipeline-components.md)