---
title: "如何从发送端口中删除证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- send ports, certificates
- managing [send ports], certificates
- certificates, deleting
- deleting, certificates
ms.assetid: fd93a83f-c2aa-4de2-9996-4ca4ec6d4a4c
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5193b1b6003660aac0e0b427da0f0a338b56d8ea
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="aec0f-102">如何从发送端口中删除证书</span><span class="sxs-lookup"><span data-stu-id="aec0f-102">How to Remove a Certificate from a Send Port</span></span>
<span data-ttu-id="aec0f-103">本主题将介绍如何使用 BizTalk Server 管理控制台从发送端口删除安全证书。</span><span class="sxs-lookup"><span data-stu-id="aec0f-103">This topic describes how to use the BizTalk Server Administration console to remove a security certificate from a send port.</span></span> <span data-ttu-id="aec0f-104">执行此操作后，发送端口将不再对消息进行加密，消息将以明文形式发送。</span><span class="sxs-lookup"><span data-stu-id="aec0f-104">When you do this, the send port will no longer encrypt messages; messages will be sent in clear text.</span></span> <span data-ttu-id="aec0f-105">从发送端口删除证书并不会从证书存储中删除该证书。</span><span class="sxs-lookup"><span data-stu-id="aec0f-105">Removing a certificate from a send port does not remove it from the certificate store.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="aec0f-106">应用程序开发人员可以通过在开发过程中使用本主题中的过程来从发送端口删除安全证书。</span><span class="sxs-lookup"><span data-stu-id="aec0f-106">The application developer can remove a security certificate from a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="aec0f-107">先决条件</span><span class="sxs-lookup"><span data-stu-id="aec0f-107">Prerequisites</span></span>  
 <span data-ttu-id="aec0f-108">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="aec0f-108">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="aec0f-109">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="aec0f-109">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-remove-a-certificate-from-a-send-port"></a><span data-ttu-id="aec0f-110">从发送端口删除证书</span><span class="sxs-lookup"><span data-stu-id="aec0f-110">To remove a certificate from a send port</span></span>  
  
1.  <span data-ttu-id="aec0f-111">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="aec0f-111">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="aec0f-112">在控制台树中，展开要为其删除证书的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="aec0f-112">In the console tree, expand the BizTalk group and the BizTalk application for which you want to remove a certificate from a send port.</span></span>  
  
3.  <span data-ttu-id="aec0f-113">展开**发送端口**，右键单击发送端口，请单击**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="aec0f-113">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificates**.</span></span>  
  
4.  <span data-ttu-id="aec0f-114">单击**删除证书**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="aec0f-114">Click **Remove certificate**, and then click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="aec0f-115">另请参阅</span><span class="sxs-lookup"><span data-stu-id="aec0f-115">See Also</span></span>  
 [<span data-ttu-id="aec0f-116">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="aec0f-116">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)