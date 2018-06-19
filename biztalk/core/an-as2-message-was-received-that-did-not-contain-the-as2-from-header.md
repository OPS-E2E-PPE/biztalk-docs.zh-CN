---
title: 已接收的 AS2 消息，不包含 AS2-从标头 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 899f9b21-b321-49a3-84bd-a5410c883968
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a63829b8a52088893a595549637f82be67efcd59
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22230077"
---
# <a name="an-as2-message-was-received-that-did-not-contain-the-as2-from-header"></a>收到的 AS2 消息不包含 AS2-From 标头
## <a name="details"></a>详细信息  
  
|||  
|-|-|  
|产品名称|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|产品版本|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|事件 ID|-|  
|事件源|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] EDI|  
|组件|AS2 引擎|  
|符号名称|-|  
|消息正文|收到的 AS2 消息不包含 AS2-From 标头|  
  
## <a name="explanation"></a>解释  
 此错误/警告/信息事件表明 BizTalk Server 无法处理传入的 AS2 消息，因为该消息不包含指明消息源的 AS2-From 标头。 AS2 消息必须有 AS2-From 标头。 如果消息没有 AS2-From 标头，则会挂起该消息。  
  
## <a name="user-action"></a>用户操作  
 若要解决此错误，请执行以下操作：  
  
-   确保在发送之前发送参与方向 AS2 消息的 HTTP、AS2 和 MIME 标头中添加 AS2-To 标头。