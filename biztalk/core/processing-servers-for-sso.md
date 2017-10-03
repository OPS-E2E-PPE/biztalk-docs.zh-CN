---
title: "处理 SSO 服务器 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 972e1a3b01394cbf63fb0c8094586d2beda73c3e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="processing-servers-for-sso"></a><span data-ttu-id="d1b6d-102">SSO 的处理服务器</span><span class="sxs-lookup"><span data-stu-id="d1b6d-102">Processing Servers for SSO</span></span>
<span data-ttu-id="d1b6d-103">在多计算机环境中，在创建了主密钥服务器和 SSO 数据库之后，即可在随后的计算机上安装企业单一登录。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-103">In a multi-computer environment, after the master secret server and SSO database have been created, you can install Enterprise Single Sign-On on subsequent computers.</span></span> <span data-ttu-id="d1b6d-104">通常，这些计算机还是用来安装 BizTalk Server 或 Host Integration Server 的计算机。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-104">These are typically the computers on which either BizTalk Server or Host Integration Server is installed as well.</span></span>  
  
 <span data-ttu-id="d1b6d-105">初始安装过程与在第一台计算机上的安装相同。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-105">The initial installation process is the same as on the first computer.</span></span> <span data-ttu-id="d1b6d-106">但是，配置则略有不同。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-106">Configuration, however, becomes slightly different.</span></span> <span data-ttu-id="d1b6d-107">因为主密钥服务器和 SSO 数据库均已到位，请选择**加入**时配置向导将询问你，**创建新的 SSO 系统**或**加入现有系统**.</span><span class="sxs-lookup"><span data-stu-id="d1b6d-107">Since the master secret server and the SSO database are already in place, select **Join** when the Configuration Wizard asks, **Create a new SSO system** or **Join an existing system**.</span></span>  
  
 <span data-ttu-id="d1b6d-108">请注意，在配置过程中，某台计算机上的组可以加入另一台计算机上并非为该组配置的 SSO 数据库。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-108">Note that it is possible during configuration for a group on one computer to join an SSO database on a different computer that is not the database configured for that group.</span></span> <span data-ttu-id="d1b6d-109">虽然允许，但不建议这样做。</span><span class="sxs-lookup"><span data-stu-id="d1b6d-109">While this is possible, it is not recommended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d1b6d-110">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d1b6d-110">See Also</span></span>  
 [<span data-ttu-id="d1b6d-111">升级从早期版本的 SSO</span><span class="sxs-lookup"><span data-stu-id="d1b6d-111">Upgrading from a Previous Version of SSO</span></span>](../core/upgrading-from-a-previous-version-of-sso.md)