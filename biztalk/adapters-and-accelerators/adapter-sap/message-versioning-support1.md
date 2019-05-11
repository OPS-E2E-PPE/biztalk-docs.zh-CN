---
title: 消息版本控制 Support1 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- message versioning, support for
ms.assetid: 650b966e-9fa6-4af8-a061-7852a892717a
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: cc6a5d1d8bf6d9969deeca33110b1d05d20413ad
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373203"
---
# <a name="message-versioning-support"></a>消息版本控制支持
[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]通过消息操作、 命名空间和节点 Id 中包含的版本字符串组件来支持版本控制提供的操作。 当前版本是 http://Microsoft.LobServices.Sap/2007/03。 这意味着对于名为"RFC_SAMPLE"RFC 和 RFC 操作由适配器具有以下：  
  
-   节点 ID: http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   消息操作： http://Microsoft.LobServices.Sap/2007/03/Rfc/RFC_SAMPLE  
  
-   Namespace: http://Microsoft.LobServices.Sap/2007/03/Rfc  
  
> [!NOTE]
>  此功能不提供向后兼容早期版本的适配器。  
  
## <a name="see-also"></a>请参阅  
 [消息和消息架构用于 mySAP Business Suite 的 BizTalk 适配器](../../adapters-and-accelerators/adapter-sap/messages-and-message-schemas-for-biztalk-adapter-for-mysap-business-suite.md)