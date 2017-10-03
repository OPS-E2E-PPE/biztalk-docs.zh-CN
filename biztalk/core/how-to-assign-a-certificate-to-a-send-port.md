---
title: "如何将证书分配给发送端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- certificates, assigning
- managing [send ports], certificates
- assigning certificates
- certificates, send ports
ms.assetid: ba9e9c8b-f5b6-4fee-9e89-31b0f1df6ed4
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ec19c845c6b0cfb5d19bd7a961fe9ddfbcf2a3d7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="3d5f2-102">如何为发送端口分配证书</span><span class="sxs-lookup"><span data-stu-id="3d5f2-102">How to Assign a Certificate to a Send Port</span></span>
<span data-ttu-id="3d5f2-103">本主题将介绍如何使用 BizTalk Server 管理控制台为发送端口分配安全证书。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-103">This topic describes how to use the BizTalk Server Administration console to assign a security certificate to a send port.</span></span> <span data-ttu-id="3d5f2-104">在运行 BizTalk Server 的计算机上的“其他人”证书存储中必须有证书，否则不会处理与此发送端口关联的消息并记录错误。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-104">The certificate must exist in the Other People certificate store on the computer running BizTalk Server, or messages associated with this send port will not be processed, and errors will be logged.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="3d5f2-105">应用程序开发人员可以通过在开发过程中使用本主题中的过程来为发送端口分配安全证书。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-105">The application developer can assign a security certificate to a send port during the development process by using the procedure in this topic.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="3d5f2-106">先决条件</span><span class="sxs-lookup"><span data-stu-id="3d5f2-106">Prerequisites</span></span>  
 <span data-ttu-id="3d5f2-107">若要执行本主题中的过程，必须使用 BizTalk Server Administrators 组的成员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-107">To perform the procedure in this topic, you must be logged on with an account that is a member of the BizTalk Server Administrators group.</span></span> <span data-ttu-id="3d5f2-108">有关更多详细权限的信息，请参阅[用于部署和管理 BizTalk 应用程序所需权限](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md)。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-108">For more detailed information on permissions, see [Permissions Required for Deploying and Managing a BizTalk Application](../core/permissions-required-for-deploying-and-managing-a-biztalk-application.md).</span></span>  
  
### <a name="to-assign-a-certificate-to-a-send-port"></a><span data-ttu-id="3d5f2-109">为发送端口分配证书</span><span class="sxs-lookup"><span data-stu-id="3d5f2-109">To assign a certificate to a send port</span></span>  
  
1.  <span data-ttu-id="3d5f2-110">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-110">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="3d5f2-111">在控制台树中，展开要为其分配证书的发送端口所属的 BizTalk 组和 BizTalk 应用程序。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-111">In the console tree, expand the BizTalk group and the BizTalk application for which you want to assign a certificate to a send port.</span></span>  
  
3.  <span data-ttu-id="3d5f2-112">展开**发送端口**，右键单击发送端口，请单击**属性**，然后单击**证书**。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-112">Expand **Send Ports**, right-click the send port, click **Properties**, and then click **Certificate**.</span></span>  
  
4.  <span data-ttu-id="3d5f2-113">如果本地计算机上是否存在此证书，请单击**浏览**，浏览到你想要分配到此发送端口，，然后单击的证书**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-113">If the certificate exists on the local computer, click **Browse**, browse to the certificate that you want to assign to this send port, and then click **OK**.</span></span> <span data-ttu-id="3d5f2-114">否则，跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-114">Otherwise, skip this step.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="3d5f2-115">即使本地计算机上有证书，如果在另一台计算机上运行 BizTalk Server，则该计算机上必须也有证书，发送端口才能处理消息。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-115">Even if the certificate exists on the local computer, it must also exist on the computer running BizTalk Server, if different, before the send port will be able to process messages.</span></span>  
  
5.  <span data-ttu-id="3d5f2-116">如果证书中不存在的本地计算机上，**指纹**框中，键入或粘贴证书指纹，，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-116">If the certificate does not exist on the local computer, in the **Thumbprint** box, type or paste the certificate thumbprint, and then click **OK**.</span></span> <span data-ttu-id="3d5f2-117">证书指纹的格式为 HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH，其中 H 为十六进制数。</span><span class="sxs-lookup"><span data-stu-id="3d5f2-117">The certificate thumbprint has the format HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH HHHH, where H is a hexadecimal digit.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d5f2-118">另请参阅</span><span class="sxs-lookup"><span data-stu-id="3d5f2-118">See Also</span></span>  
 [<span data-ttu-id="3d5f2-119">创建和配置发送端口</span><span class="sxs-lookup"><span data-stu-id="3d5f2-119">Creating and Configuring Send Ports</span></span>](../core/creating-and-configuring-send-ports.md)