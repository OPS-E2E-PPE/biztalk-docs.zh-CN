---
title: 管理主密钥 |Microsoft 文档
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
ms.openlocfilehash: c2505fa6f5ec1abc04ded45e7701fd4e5212f889
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262173"
---
# <a name="managing-the-master-secret"></a><span data-ttu-id="3a928-102">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="3a928-102">Managing the Master Secret</span></span>
<span data-ttu-id="3a928-103">主密钥是用于对 SSO 数据库中存储的所有信息进行加密的密钥。</span><span class="sxs-lookup"><span data-stu-id="3a928-103">The master secret is the key used to encrypt all the information stored in the SSO database.</span></span> <span data-ttu-id="3a928-104">在主密钥服务器发生故障的情况下，如果丢失了密钥，您将无法检索 SSO 数据库中存储的信息。</span><span class="sxs-lookup"><span data-stu-id="3a928-104">If the master secret server fails and you lose the secret, you will not be able to retrieve the information stored in the SSO database.</span></span> <span data-ttu-id="3a928-105">因此，请务必在生成主密钥后立即备份该主密钥。</span><span class="sxs-lookup"><span data-stu-id="3a928-105">Therefore, it is very important to back up the master secret as soon as you generate it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="3a928-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="3a928-106">In This Section</span></span>  
  
-   [<span data-ttu-id="3a928-107">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="3a928-107">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="3a928-108">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="3a928-108">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="3a928-109">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="3a928-109">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="3a928-110">如何移动主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="3a928-110">How to Move the Master Secret Server</span></span>](../core/how-to-move-the-master-secret-server.md)