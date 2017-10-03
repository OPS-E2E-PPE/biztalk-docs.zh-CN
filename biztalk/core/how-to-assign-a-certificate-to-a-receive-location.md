---
title: "如何分配到证书接收位置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, receive locations
- receive locations, certificates
- managing [receive locations], certificates
ms.assetid: 54ae300e-62c5-480f-a9b7-e5c3457a0f80
caps.latest.revision: "11"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 94554aa5781ed609e5129d58ab75e5709e432278
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="b430c-102">如何分配到证书接收位置</span><span class="sxs-lookup"><span data-stu-id="b430c-102">How to Assign a Certificate to a Receive Location</span></span>
<span data-ttu-id="b430c-103">本主题将介绍如何使用 BizTalk Server 管理控制台向接收位置分配安全证书。</span><span class="sxs-lookup"><span data-stu-id="b430c-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a receive location.</span></span> <span data-ttu-id="b430c-104">您只能在双向接收位置上执行此过程。</span><span class="sxs-lookup"><span data-stu-id="b430c-104">You can perform this procedure on a two-way receive location only.</span></span> <span data-ttu-id="b430c-105">在运行 BizTalk Server 的计算机上的“其他人”证书存储中必须有证书，否则不会处理与此接收位置关联的消息并将记录错误。</span><span class="sxs-lookup"><span data-stu-id="b430c-105">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this receive location will not be processed, and errors will be logged.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="b430c-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="b430c-106">Prerequisites</span></span>  
 <span data-ttu-id="b430c-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b430c-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="b430c-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="b430c-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-receive-location"></a><span data-ttu-id="b430c-109">若要将证书分配给接收位置</span><span class="sxs-lookup"><span data-stu-id="b430c-109">To assign a certificate to a receive location</span></span>  
  
1.  <span data-ttu-id="b430c-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="b430c-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="b430c-111">在控制台树中，展开要为其分配证书的接收位置所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="b430c-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a receive location.</span></span>  
  
3.  <span data-ttu-id="b430c-112">展开**接收位置**，右键单击接收位置，单击**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="b430c-112">Expand **Receive Locations**, right-click the receive location, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="b430c-113">如果本地计算机上是否存在此证书，请单击**浏览**，浏览到你想要分配给此证书接收位置，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b430c-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this receive location, and then click **OK**.</span></span> <span data-ttu-id="b430c-114">否则，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="b430c-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="b430c-115">如果您在从远程计算机执行此操作，则确保在运行 BizTalk Server 的计算机上存在证书，而不是只在本地计算机上存在证书。</span><span class="sxs-lookup"><span data-stu-id="b430c-115">If you are performing this operation from a remote computer, make sure that the certificate exists on the computer running BizTalk Server, and not only on the local computer.</span></span> <span data-ttu-id="b430c-116">否则，接收位置将无法处理消息。</span><span class="sxs-lookup"><span data-stu-id="b430c-116">Otherwise, the receive location will not be able to process messages.</span></span>  
  
5.  <span data-ttu-id="b430c-117">如果证书中不存在的本地计算机上，**指纹**框中，键入或粘贴证书指纹，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="b430c-117">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="b430c-118">证书指纹的格式为 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="b430c-118">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b430c-119">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b430c-119">See Also</span></span>  
 [<span data-ttu-id="b430c-120">管理接收位置</span><span class="sxs-lookup"><span data-stu-id="b430c-120">Managing Receive Locations</span></span>](../core/managing-receive-locations.md)