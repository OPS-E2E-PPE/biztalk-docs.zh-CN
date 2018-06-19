---
title: 消息版本控制 Support2 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 5b7b9202-9f45-450e-918f-b26a03711aab
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 04514a9c55fa29a930b6ba7467177d6a754ff3db
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22221853"
---
# <a name="message-versioning-support"></a>消息版本控制支持
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]通过消息操作、 命名空间和的节点 Id 中包含的版本字符串组件的支持版本控制中加以表示的操作。 当前版本为 http://Microsoft.LobServices.Siebel/2007/03。 这意味着 Siebel 存储库中的帐户业务对象上的插入操作，该适配器显示在插入操作具有以下：  
  
-   节点 ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   消息操作： http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation  
  
> [!NOTE]
>  此功能不提供与早期版本的适配器的向后兼容性。  
  
## <a name="see-also"></a>另请参阅  
 [消息和用于 Siebel eBusiness Applications 的 BizTalk Adapter 的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)