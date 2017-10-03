---
title: "单一登录规划 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bc35c53193ac8e48c9169131b637dc1d7a581fc
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="planning-for-single-sign-on"></a><span data-ttu-id="6a425-102">规划上单一登录</span><span class="sxs-lookup"><span data-stu-id="6a425-102">Planning for Single Sign-On</span></span>
<span data-ttu-id="6a425-103">企业单一登录 (SSO) 是一个重要组成部分的[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="6a425-103">Enterprise Single Sign-On (SSO) is a critical component of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="6a425-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]没有 SSO 服务，因为运行的时无法运行所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器的配置信息加密，并在 SSO 数据库中存储和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]访问此信息通过 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="6a425-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run time cannot function without the SSO service because all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter configuration information is encrypted and stored in the SSO database and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] accesses this information via the SSO service.</span></span> <span data-ttu-id="6a425-105">如果 SSO 服务未在 BizTalk server 上运行，或者 SSO 服务没有 SSO 主密钥服务器的访问，此适配器的配置信息不可访问。</span><span class="sxs-lookup"><span data-stu-id="6a425-105">This adapter configuration information is not accessible if the SSO service is not running on the BizTalk server or if the SSO service does not have access to the SSO master secret server.</span></span>  
  
 <span data-ttu-id="6a425-106">SSO 实施应包括以下计划。</span><span class="sxs-lookup"><span data-stu-id="6a425-106">Your SSO implementation should include the following plans.</span></span>  
  
## <a name="backing-up-the-master-secret"></a><span data-ttu-id="6a425-107">备份主密钥</span><span class="sxs-lookup"><span data-stu-id="6a425-107">Backing Up the Master Secret</span></span>  
 <span data-ttu-id="6a425-108">如果 SSO 主密钥服务器失败，并且您丢失了密钥，或者如果密钥已损坏，你将不能检索 SSO 数据库中存储数据。</span><span class="sxs-lookup"><span data-stu-id="6a425-108">If the SSO master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="6a425-109">因此必须备份主密钥，否则将面临丢失 SSO 数据库中数据的风险。</span><span class="sxs-lookup"><span data-stu-id="6a425-109">You must back up the master secret, or you risk losing data from the SSO database.</span></span> <span data-ttu-id="6a425-110">因此它是必不可少的 SSO 主密钥进行备份和存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="6a425-110">Therefore it is absolutely critical that the SSO master secret is backed up and stored in a secure location.</span></span> <span data-ttu-id="6a425-111">有关备份 SSO 主密钥的信息，请参阅[如何返回向上主密钥](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。</span><span class="sxs-lookup"><span data-stu-id="6a425-111">For information about backing up the SSO master secret, see [How to Back Up the Master Secret](http://go.microsoft.com/fwlink/?LinkId=151395) (http://go.microsoft.com/fwlink/?LinkId=151395).</span></span>  
  
## <a name="configuring-sso-for-high-availability"></a><span data-ttu-id="6a425-112">针对高可用性配置 SSO</span><span class="sxs-lookup"><span data-stu-id="6a425-112">Configuring SSO for High Availability</span></span>  
 <span data-ttu-id="6a425-113">因为 SSO 的此类的关键组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，应针对高可用性配置 SSO 主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="6a425-113">Because SSO is such a critical component of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, the SSO master secret server should be configured for high availability.</span></span> <span data-ttu-id="6a425-114">有可能，应按照中的步骤群集上的主密钥服务器的企业单一登录服务[群集主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。</span><span class="sxs-lookup"><span data-stu-id="6a425-114">If at all possible, the Enterprise Single Sign-On service on the master secret server should be clustered by following the steps in [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md).</span></span> <span data-ttu-id="6a425-115">事件中没有可访问 Windows Server 群集，你仍然可以提供高可用性的主密钥服务器上的企业单一登录服务通过以下主题中所述的步骤[指定新的主服务器密钥服务器手动](../technical-guides/designating-a-new-master-secret-server-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="6a425-115">In the event that you do not have access to a Windows Server cluster, you can still provide high availability for the Enterprise Single Sign-On service on the master secret server by following the steps documented in the topic [Designating a New Master Secret Server Manually](../technical-guides/designating-a-new-master-secret-server-manually.md).</span></span>  
  
## <a name="following-established-sso-security-recommendations"></a><span data-ttu-id="6a425-116">以下建立的 SSO 安全建议</span><span class="sxs-lookup"><span data-stu-id="6a425-116">Following Established SSO Security Recommendations</span></span>  
 <span data-ttu-id="6a425-117">请遵循本主题所述的 SSO 安全建议[SSO 安全建议](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)。</span><span class="sxs-lookup"><span data-stu-id="6a425-117">Follow SSO security recommendations described in the topic [SSO Security Recommendations](http://go.microsoft.com/fwlink/?LinkId=155753) (http://go.microsoft.com/fwlink/?LinkId=155753).</span></span>