---
title: "如何安装进行数字签名的证书 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: "15"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 7a755e59c7c916f3abe037513ddbc9e2a89892fb
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a><span data-ttu-id="4ef06-102">如何安装进行数字签名的证书</span><span class="sxs-lookup"><span data-stu-id="4ef06-102">How to install the Certificates for Digital Signatures</span></span>
<span data-ttu-id="4ef06-103">下面的过程列出了安装证书以便接收和发送签名消息需遵守的高级步骤。</span><span class="sxs-lookup"><span data-stu-id="4ef06-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending signed messages.</span></span>  
  
-   <span data-ttu-id="4ef06-104">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="4ef06-105">在证书存储中安装签名证书以发送签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-105">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
-   <span data-ttu-id="4ef06-106">配置 BizTalk 组以发送签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-106">To configure the BizTalk Group for sending signed messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="4ef06-107">可以使用一个证书同时执行签名和加密操作，也可以对于每种功能使用一个证书。</span><span class="sxs-lookup"><span data-stu-id="4ef06-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
  
> [!IMPORTANT]
>  <span data-ttu-id="4ef06-108">您只能指定一个签名证书，供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 用来对所有出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="4ef06-108">You can only specify one signing certificate with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] signs all outbound messages.</span></span> <span data-ttu-id="4ef06-109">换句话说，您不能根据您要向其发送消息的人员来使用不同的签名证书。</span><span class="sxs-lookup"><span data-stu-id="4ef06-109">In other words, you cannot use different signing certificates depending on who you are sending the message to.</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="4ef06-110">在证书存储中安装证书以接收签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-110">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1.  <span data-ttu-id="4ef06-111">合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥/公钥对。</span><span class="sxs-lookup"><span data-stu-id="4ef06-111">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2.  <span data-ttu-id="4ef06-112">合作伙伴 A 向您发送它的数字签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="4ef06-112">Partner A sends you its public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="4ef06-113">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有特定主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书以验证其签名。</span><span class="sxs-lookup"><span data-stu-id="4ef06-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="4ef06-114">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="4ef06-114">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="4ef06-115">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="4ef06-115">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4.  <span data-ttu-id="4ef06-116">在合作伙伴 A 中，在适当的存储中安装合作伙伴 A 私钥证书以便对消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="4ef06-116">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="4ef06-117">（如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，则在将对发送到 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 的消息进行签名的帐户的个人存储中安装私钥。）</span><span class="sxs-lookup"><span data-stu-id="4ef06-117">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a><span data-ttu-id="4ef06-118">在证书存储中安装签名证书以发送签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-118">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
1.  <span data-ttu-id="4ef06-119">组织中的管理员从 CA 请求数字签名的私钥/公钥对以供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用。</span><span class="sxs-lookup"><span data-stu-id="4ef06-119">An administrator in your organization requests a private-public key pair for digital signatures from the CA for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2.  <span data-ttu-id="4ef06-120">管理员向合作伙伴 A（以及所有其他合作伙伴）发送数字签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="4ef06-120">The administrator sends Partner A (and all other partners) the public key for digital signatures.</span></span>  
  
3.  <span data-ttu-id="4ef06-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，作为特定主机实例（该主机实例运行将向合作伙伴 A 发送消息的处理程序）的服务帐户登录。安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 私钥证书以便对此服务帐户的个人存储中的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="4ef06-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as service account for the host instance running the handler that will send messages to Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for signing messages in the personal store for the service account.</span></span> <span data-ttu-id="4ef06-122">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="4ef06-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
     <span data-ttu-id="4ef06-123">![将发送安全消息所需的证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="4ef06-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
4.  <span data-ttu-id="4ef06-124">在合作伙伴 A 中，在适当的存储中安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 公钥证书以验证其数字签名。</span><span class="sxs-lookup"><span data-stu-id="4ef06-124">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for verifying its digital signature in the appropriate store.</span></span> <span data-ttu-id="4ef06-125">（如果合作伙伴 A 使用的是 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)] 或 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请在“其他人”存储中安装公钥）。</span><span class="sxs-lookup"><span data-stu-id="4ef06-125">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other people store.)</span></span>  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a><span data-ttu-id="4ef06-126">配置 BizTalk 组以发送签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-126">To configure the BizTalk Group for sending signed messages</span></span>  
  
1.  <span data-ttu-id="4ef06-127">单击**启动**，指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="4ef06-127">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="4ef06-128">右键单击**BizTalk 组**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="4ef06-128">Right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3.  <span data-ttu-id="4ef06-129">上**组属性**对话框中，单击**证书**，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="4ef06-129">On the **Group Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
4.  <span data-ttu-id="4ef06-130">上**选择证书**对话框中，选择你安装的签名证书，然后关闭所有对话框。</span><span class="sxs-lookup"><span data-stu-id="4ef06-130">On the **Select Certificate** dialog box, select the signing certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="4ef06-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4ef06-131">Next Steps</span></span>  
 <span data-ttu-id="4ef06-132">创建管道用于接收中的签名的消息[如何为接收签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="4ef06-132">You create a pipeline to receive signed messages in [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
 <span data-ttu-id="4ef06-133">创建管道中发送签名的消息[如何为发送签名消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="4ef06-133">You create a pipeline to send signed messages in [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4ef06-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ef06-134">See Also</span></span>  
 <span data-ttu-id="4ef06-135">[BizTalk Server 用于签名的消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="4ef06-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="4ef06-136">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="4ef06-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)