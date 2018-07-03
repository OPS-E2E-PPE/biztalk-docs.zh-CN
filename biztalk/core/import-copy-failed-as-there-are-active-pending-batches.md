---
title: 导入复制失败，因为有活动挂起的批处理 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 17803f0a-3c70-4a8a-8e8d-7f874ed9ad92
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a74bfdccbd12db00cd0f325aedee2e42cc76729
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36970534"
---
# <a name="import-copy-failed-as-there-are-active-pending-batches"></a>导入复制失败，因为有活动挂起的批处理
## <a name="details"></a>详细信息  
  
|                 |                                                                                                                |
|-----------------|----------------------------------------------------------------------------------------------------------------|
|  产品名称   |               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]               |
| 产品版本 |                           [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]                           |
|    事件 ID     |                                                       -                                                        |
|  事件源   |             [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI             |
|    组件    |                                                   EDI 引擎                                                   |
|  符号名称  |                                              Err_ActiveBatchFound                                              |
|  消息正文   | 导入/复制失败，因为有活动/挂起的批处理。 停止活动/挂起的批处理，然后尝试导入/复制。 |
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法导入绑定文件或无法复制设置，因为受影响的协议具有一个或多个活动或挂起的批处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保受影响的协议中的所有批处理在“协议”属性中显示为已停止。