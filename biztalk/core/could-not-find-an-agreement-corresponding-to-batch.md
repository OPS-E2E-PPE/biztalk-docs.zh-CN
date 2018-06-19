---
title: 找不到对应于批处理协议 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4d1c0480-9a6f-481a-9143-e5a55707c3b5
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bce17af0e382a137dc8d55d30705da58dd52301c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22237925"
---
# <a name="could-not-find-an-agreement-corresponding-to-batch"></a>找不到对应于批的协议
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|EDI 引擎|  
|符号名称|AgreementNotFoundForBatch|  
|消息正文|找不到与批处理 {0} 相对应的协议。|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件指示 BizTalk Server 找不到启动/停止一批或处理批处理消息一批在尝试时与此 Id 相对应。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，确保验证具有给定 Id 的批处理中存在包含协议的协议属性。