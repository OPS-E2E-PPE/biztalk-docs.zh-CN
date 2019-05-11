---
title: 用于 SSO 的处理服务器 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- SSO, processing servers
- processing servers [SSO]
ms.assetid: 9e80a456-974a-49b3-bb64-2e4713036cfb
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e2676de4e698f3ea9221b35c349819f163b74b3a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255136"
---
# <a name="processing-servers-for-sso"></a><span data-ttu-id="4bfa1-102">用于 SSO 的处理服务器</span><span class="sxs-lookup"><span data-stu-id="4bfa1-102">Processing Servers for SSO</span></span>
<span data-ttu-id="4bfa1-103">在多计算机环境中，已创建主密钥服务器和 SSO 数据库后，你可以安装企业单一登录在随后的计算机上。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-103">In a multi-computer environment, after the master secret server and SSO database have been created, you can install Enterprise Single Sign-On on subsequent computers.</span></span> <span data-ttu-id="4bfa1-104">这些通常是 BizTalk Server 或 Host Integration Server 也在其安装的计算机。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-104">These are typically the computers on which either BizTalk Server or Host Integration Server is installed as well.</span></span>  
  
 <span data-ttu-id="4bfa1-105">初始安装过程是第一台计算机上相同。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-105">The initial installation process is the same as on the first computer.</span></span> <span data-ttu-id="4bfa1-106">但是，配置中，将成为略有不同。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-106">Configuration, however, becomes slightly different.</span></span> <span data-ttu-id="4bfa1-107">由于主密钥服务器和 SSO 数据库均已就位，选择**加入**时配置向导询问**创建新的 SSO 系统**或**加入现有系统**.</span><span class="sxs-lookup"><span data-stu-id="4bfa1-107">Since the master secret server and the SSO database are already in place, select **Join** when the Configuration Wizard asks, **Create a new SSO system** or **Join an existing system**.</span></span>  
  
 <span data-ttu-id="4bfa1-108">请注意，它可能在一台计算机上要加入不是为该组配置的数据库的其他计算机上的 SSO 数据库的组的配置过程。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-108">Note that it is possible during configuration for a group on one computer to join an SSO database on a different computer that is not the database configured for that group.</span></span> <span data-ttu-id="4bfa1-109">虽然这可能，但不建议。</span><span class="sxs-lookup"><span data-stu-id="4bfa1-109">While this is possible, it is not recommended.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4bfa1-110">请参阅</span><span class="sxs-lookup"><span data-stu-id="4bfa1-110">See Also</span></span>  
 [<span data-ttu-id="4bfa1-111">从早期版本的 SSO 升级</span><span class="sxs-lookup"><span data-stu-id="4bfa1-111">Upgrading from a Previous Version of SSO</span></span>](../core/upgrading-from-a-previous-version-of-sso.md)