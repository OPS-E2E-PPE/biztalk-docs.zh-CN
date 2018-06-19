---
title: 找不到批处理 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6e967e1a-b87f-4c87-a157-a6f63ba96d78
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a73c3e65a806f02faeb81baa6a5263019079b0c6
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22279477"
---
# <a name="the-batch-was-not-found"></a>找不到批处理
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|Err_BatchNotFound|  
|消息正文|未找到批处理。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 在启动/停止批处理期间或者在批处理业务流程尝试对消息进行批处理时未找到批处理。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请确保所包含协议的“协议”属性中存在相应的批处理。