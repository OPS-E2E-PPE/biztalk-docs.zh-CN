---
title: 规划单一登录 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 7d1bc220-4087-4603-ac15-6bb0c62c59d4
caps.latest.revision: 2
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4677eca7a6314da15f86257e17dbaf33cf0b8224
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65400696"
---
# <a name="planning-for-single-sign-on"></a><span data-ttu-id="76252-102">规划单一登录</span><span class="sxs-lookup"><span data-stu-id="76252-102">Planning for Single Sign-On</span></span>
<span data-ttu-id="76252-103">企业单一登录 (SSO) 是一个关键组成部分[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境。</span><span class="sxs-lookup"><span data-stu-id="76252-103">Enterprise Single Sign-On (SSO) is a critical component of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment.</span></span> <span data-ttu-id="76252-104">[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]运行的时将不能没有 SSO 服务，因为所有[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]适配器配置信息加密，并在 SSO 数据库中存储和[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]访问此信息通过 SSO 服务。</span><span class="sxs-lookup"><span data-stu-id="76252-104">The [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] run time cannot function without the SSO service because all [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] adapter configuration information is encrypted and stored in the SSO database and [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] accesses this information via the SSO service.</span></span> <span data-ttu-id="76252-105">如果 SSO 服务未在 BizTalk server 上运行，或如果 SSO 服务不具有对 SSO 主密钥服务器的访问，此适配器配置信息不可访问。</span><span class="sxs-lookup"><span data-stu-id="76252-105">This adapter configuration information is not accessible if the SSO service is not running on the BizTalk server or if the SSO service does not have access to the SSO master secret server.</span></span>  
  
 <span data-ttu-id="76252-106">SSO 实施应包括以下计划。</span><span class="sxs-lookup"><span data-stu-id="76252-106">Your SSO implementation should include the following plans.</span></span>  
  
## <a name="backing-up-the-master-secret"></a><span data-ttu-id="76252-107">备份主密钥</span><span class="sxs-lookup"><span data-stu-id="76252-107">Backing Up the Master Secret</span></span>  
 <span data-ttu-id="76252-108">如果 SSO 主密钥服务器失败，并且丢失了密钥，或者密钥损坏，您将不能检索存储在 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="76252-108">If the SSO master secret server fails and you lose the key, or if the key becomes corrupted, you will not be able to retrieve data stored in the SSO database.</span></span> <span data-ttu-id="76252-109">您必须备份主密钥或风险会丢失 SSO 数据库中的数据。</span><span class="sxs-lookup"><span data-stu-id="76252-109">You must back up the master secret, or you risk losing data from the SSO database.</span></span> <span data-ttu-id="76252-110">因此，它是 SSO 主密钥进行备份和存储在安全位置非常重要。</span><span class="sxs-lookup"><span data-stu-id="76252-110">Therefore it is absolutely critical that the SSO master secret is backed up and stored in a secure location.</span></span> <span data-ttu-id="76252-111">有关 SSO 主密钥备份的信息，请参阅[如何返回主密钥](http://go.microsoft.com/fwlink/?LinkId=151395)(http://go.microsoft.com/fwlink/?LinkId=151395)。</span><span class="sxs-lookup"><span data-stu-id="76252-111">For information about backing up the SSO master secret, see [How to Back Up the Master Secret](http://go.microsoft.com/fwlink/?LinkId=151395) (http://go.microsoft.com/fwlink/?LinkId=151395).</span></span>  
  
## <a name="configuring-sso-for-high-availability"></a><span data-ttu-id="76252-112">配置高可用性的 SSO</span><span class="sxs-lookup"><span data-stu-id="76252-112">Configuring SSO for High Availability</span></span>  
 <span data-ttu-id="76252-113">由于 SSO 是此类的关键组件[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]环境中，应以实现高可用性配置 SSO 主密钥服务器。</span><span class="sxs-lookup"><span data-stu-id="76252-113">Because SSO is such a critical component of a [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] environment, the SSO master secret server should be configured for high availability.</span></span> <span data-ttu-id="76252-114">如有可能，应按照中的步骤群集企业单一登录主密钥服务器上的服务[聚类分析主密钥服务器](../technical-guides/clustering-the-master-secret-server.md)。</span><span class="sxs-lookup"><span data-stu-id="76252-114">If at all possible, the Enterprise Single Sign-On service on the master secret server should be clustered by following the steps in [Clustering the Master Secret Server](../technical-guides/clustering-the-master-secret-server.md).</span></span> <span data-ttu-id="76252-115">如果您不有权访问 Windows Server 群集，你仍可以提供高可用性的主密钥服务器上的企业单一登录服务按照主题中所述的步骤[指定新的主服务器密钥服务器手动](../technical-guides/designating-a-new-master-secret-server-manually.md)。</span><span class="sxs-lookup"><span data-stu-id="76252-115">In the event that you do not have access to a Windows Server cluster, you can still provide high availability for the Enterprise Single Sign-On service on the master secret server by following the steps documented in the topic [Designating a New Master Secret Server Manually](../technical-guides/designating-a-new-master-secret-server-manually.md).</span></span>  
  
## <a name="following-established-sso-security-recommendations"></a><span data-ttu-id="76252-116">以下建立的 SSO 安全建议</span><span class="sxs-lookup"><span data-stu-id="76252-116">Following Established SSO Security Recommendations</span></span>  
 <span data-ttu-id="76252-117">遵循本主题中所述的 SSO 安全建议[SSO 安全建议](http://go.microsoft.com/fwlink/?LinkId=155753)(http://go.microsoft.com/fwlink/?LinkId=155753)。</span><span class="sxs-lookup"><span data-stu-id="76252-117">Follow SSO security recommendations described in the topic [SSO Security Recommendations](http://go.microsoft.com/fwlink/?LinkId=155753) (http://go.microsoft.com/fwlink/?LinkId=155753).</span></span>