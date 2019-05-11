---
title: 管理主密钥 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Master Secret server, managing
- managing [Master Secret server]
- SSO, Master Secret server
ms.assetid: f79e8f3f-c740-4ea1-9589-b42552fcd52d
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f4bc7c0222a635b3b698adf899f98a8ff96e08de
ms.sourcegitcommit: d27732e569b0897361dfaebca8352aa97bb7efe1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2019
ms.locfileid: "65531137"
---
# <a name="managing-the-master-secret"></a>管理主密钥
主密钥是用于加密存储在 SSO 数据库中的所有信息的键。 如果主服务器发生故障，并且如果丢失了密钥，你将无法检索存储在 SSO 数据库中的信息。 因此，它是非常重要，只要在生成备份主密钥。  
  
## <a name="in-this-section"></a>本节内容  
  
-   [如何生成主密钥](../core/how-to-generate-the-master-secret.md)  
  
-   [如何备份主密钥](../core/how-to-back-up-the-master-secret.md)  
  
-   [如何还原主密钥](../core/how-to-restore-the-master-secret.md)  
  
-   [如何移动主密钥服务器](../core/how-to-move-the-master-secret-server.md)