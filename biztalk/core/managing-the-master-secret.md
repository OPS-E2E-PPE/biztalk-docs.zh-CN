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
# <a name="managing-the-master-secret"></a><span data-ttu-id="26142-102">管理主密钥</span><span class="sxs-lookup"><span data-stu-id="26142-102">Managing the Master Secret</span></span>
<span data-ttu-id="26142-103">主密钥是用于加密存储在 SSO 数据库中的所有信息的键。</span><span class="sxs-lookup"><span data-stu-id="26142-103">The master secret is the key used to encrypt all the information stored in the SSO database.</span></span> <span data-ttu-id="26142-104">如果主服务器发生故障，并且如果丢失了密钥，你将无法检索存储在 SSO 数据库中的信息。</span><span class="sxs-lookup"><span data-stu-id="26142-104">If the master secret server fails and you lose the secret, you will not be able to retrieve the information stored in the SSO database.</span></span> <span data-ttu-id="26142-105">因此，它是非常重要，只要在生成备份主密钥。</span><span class="sxs-lookup"><span data-stu-id="26142-105">Therefore, it is very important to back up the master secret as soon as you generate it.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="26142-106">本节内容</span><span class="sxs-lookup"><span data-stu-id="26142-106">In This Section</span></span>  
  
-   [<span data-ttu-id="26142-107">如何生成主密钥</span><span class="sxs-lookup"><span data-stu-id="26142-107">How to Generate the Master Secret</span></span>](../core/how-to-generate-the-master-secret.md)  
  
-   [<span data-ttu-id="26142-108">如何备份主密钥</span><span class="sxs-lookup"><span data-stu-id="26142-108">How to Back Up the Master Secret</span></span>](../core/how-to-back-up-the-master-secret.md)  
  
-   [<span data-ttu-id="26142-109">如何还原主密钥</span><span class="sxs-lookup"><span data-stu-id="26142-109">How to Restore the Master Secret</span></span>](../core/how-to-restore-the-master-secret.md)  
  
-   [<span data-ttu-id="26142-110">如何移动主密钥服务器</span><span class="sxs-lookup"><span data-stu-id="26142-110">How to Move the Master Secret Server</span></span>](../core/how-to-move-the-master-secret-server.md)