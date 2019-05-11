---
title: 如何分配证书到接收位置 |Microsoft Docs
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
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d02cf6c22de920b166fcbe1e0b238b02b5bf2398
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65342735"
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="a2b90-102">如何分配证书到接收位置</span><span class="sxs-lookup"><span data-stu-id="a2b90-102">How to Assign a Certificate to a Receive Location</span></span>
<span data-ttu-id="a2b90-103">本主题介绍如何使用 BizTalk Server 管理控制台为接收位置分配安全证书。</span><span class="sxs-lookup"><span data-stu-id="a2b90-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a receive location.</span></span> <span data-ttu-id="a2b90-104">可以在执行此过程的双向接收位置仅。</span><span class="sxs-lookup"><span data-stu-id="a2b90-104">You can perform this procedure on a two-way receive location only.</span></span> <span data-ttu-id="a2b90-105">在运行 BizTalk Server 的计算机上的其他人证书存储中必须有证书，或与此相关联的消息接收位置将不会处理，并且将记录错误。</span><span class="sxs-lookup"><span data-stu-id="a2b90-105">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this receive location will not be processed, and errors will be logged.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="a2b90-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="a2b90-106">Prerequisites</span></span>  
 <span data-ttu-id="a2b90-107">若要执行本主题中的过程，必须是 BizTalk Server Administrators 组的成员的帐户登录。</span><span class="sxs-lookup"><span data-stu-id="a2b90-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="a2b90-108">有关详细的权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="a2b90-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="a2b90-109">若要将证书分配到接收位置</span><span class="sxs-lookup"><span data-stu-id="a2b90-109">To assign a certificate to a receive location</span></span>  
  
1. <span data-ttu-id="a2b90-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a2b90-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="a2b90-111">在控制台树中，展开 BizTalk 组和 BizTalk 应用程序想要将证书分配到接收位置。</span><span class="sxs-lookup"><span data-stu-id="a2b90-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a receive location.</span></span>  
  
3. <span data-ttu-id="a2b90-112">展开**接收位置**，右键单击接收位置，单击**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="a2b90-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificate**.</span></span>  
  
4. <span data-ttu-id="a2b90-113">如果证书存在于本地计算机上，单击**浏览**，浏览到证书，你想要分配给此接收位置，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a2b90-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this receive location, and then click **OK**.</span></span> <span data-ttu-id="a2b90-114">否则，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="a2b90-114">Otherwise, skip this step.</span></span>  
  
   > [!NOTE]
   >  <span data-ttu-id="a2b90-115">如果您正在从远程计算机执行此操作，请确保证书存在运行 BizTalk Server 的计算机上而不在本地计算机。</span><span class="sxs-lookup"><span data-stu-id="a2b90-115">If you are performing this operation from a remote computer, make sure that the certificate exists on the computer running BizTalk Server, and not only on the local computer.</span></span> <span data-ttu-id="a2b90-116">否则，接收位置将不能处理的消息。</span><span class="sxs-lookup"><span data-stu-id="a2b90-116">Otherwise, the receive location will not be able to process messages.</span></span>  
  
5. <span data-ttu-id="a2b90-117">如果证书中不存在本地计算机上**指纹**框中，键入或粘贴证书指纹，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="a2b90-117">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="a2b90-118">证书指纹的格式 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数字。</span><span class="sxs-lookup"><span data-stu-id="a2b90-118">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a2b90-119">请参阅</span><span class="sxs-lookup"><span data-stu-id="a2b90-119">See Also</span></span>  
 [<span data-ttu-id="a2b90-120">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="a2b90-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)