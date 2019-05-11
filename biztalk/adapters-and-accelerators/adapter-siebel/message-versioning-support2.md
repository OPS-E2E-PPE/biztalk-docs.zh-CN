---
title: 消息版本控制 Support2 |Microsoft Docs
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
ms.openlocfilehash: 181e242334d91b92eeaa2800baf9a56bd936a3eb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371323"
---
# <a name="message-versioning-support"></a>消息版本控制支持
[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]通过消息操作、 命名空间和节点 Id 中包含的版本字符串组件来支持版本控制提供的操作。 当前版本是 http://Microsoft.LobServices.Siebel/2007/03。 这意味着在 Siebel 存储库中帐户业务对象上的插入操作，适配器提供的插入操作具有以下：  
  
-   节点 ID: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   消息操作： http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Insert  
  
-   Namespace: http://Microsoft.LobServices.Siebel/2007/03/BusinessObjects/Account/Account/Operation  
  
> [!NOTE]
>  此功能不提供向后兼容早期版本的适配器。  
  
## <a name="see-also"></a>请参阅  
 [消息和用于 Siebel eBusiness 应用程序的 BizTalk 适配器的消息架构](../../adapters-and-accelerators/adapter-siebel/messages-and-message-schemas-for-siebel-adapter-in-biztalk.md)