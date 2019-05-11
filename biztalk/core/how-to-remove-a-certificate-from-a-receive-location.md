---
title: 如何从证书中删除接收位置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 717d41bf-4260-4df4-9d0a-07243bb9b12c
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2ac326fd11f55320de04033f44ba9f81ffd85282
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384383"
---
# <a name="how-to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="d8f0f-102">如何从证书中删除接收位置</span><span class="sxs-lookup"><span data-stu-id="d8f0f-102">How to Remove a Certificate from a Receive Location</span></span>
<span data-ttu-id="d8f0f-103">本主题介绍如何使用 BizTalk Server 管理控制台从接收位置删除安全证书。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a receive location.</span></span> <span data-ttu-id="d8f0f-104">接收位置时执行此操作时，将无法再加密的消息;将以明文形式发送消息。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-104">When you do this, the receive location will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="d8f0f-105">从接收位置删除证书不会删除它从证书存储。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-105">Removing a certificate from a receive location does not remove it from the certificate store.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="d8f0f-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="d8f0f-106">Prerequisites</span></span>  
 <span data-ttu-id="d8f0f-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="d8f0f-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-receive-location"></a><span data-ttu-id="d8f0f-109">若要从接收位置删除证书</span><span class="sxs-lookup"><span data-stu-id="d8f0f-109">To remove a certificate from a receive location</span></span>  
  
1. <span data-ttu-id="d8f0f-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="d8f0f-111">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要从接收位置删除证书。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a receive location.</span></span>  
  
3. <span data-ttu-id="d8f0f-112">展开**接收位置**，右键单击接收位置，单击**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificates**.</span></span>  
  
4. <span data-ttu-id="d8f0f-113">单击**删除证书**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="d8f0f-113">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d8f0f-114">请参阅</span><span class="sxs-lookup"><span data-stu-id="d8f0f-114">See Also</span></span>  
 [<span data-ttu-id="d8f0f-115">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="d8f0f-115">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)