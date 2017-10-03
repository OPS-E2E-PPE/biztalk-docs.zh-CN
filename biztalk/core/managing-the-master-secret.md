---
title: "管理主密钥 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c2505fa6f5ec1abc04ded45e7701fd4e5212f889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="managing-the-master-secret"></a>管理主密钥
主密钥是用于对 SSO 数据库中存储的所有信息进行加密的密钥。 在主密钥服务器发生故障的情况下，如果丢失了密钥，您将无法检索 SSO 数据库中存储的信息。 因此，请务必在生成主密钥后立即备份该主密钥。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  
  
-   [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  
  
-   [如何还原主密钥](../core/how-to-restore-the-master-secret.md)  
  
-   [如何移动主密钥服务器](../core/how-to-move-the-master-secret-server.md)