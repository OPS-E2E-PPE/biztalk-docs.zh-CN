---
title: 如何安装进行数字签名的证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 910ccd84-c022-46a5-a9de-b99046a480b8
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3bec4fd58532201efc430855464a90f03a824400
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65384907"
---
# <a name="how-to-install-the-certificates-for-digital-signatures"></a><span data-ttu-id="0b9ef-102">如何安装进行数字签名的证书</span><span class="sxs-lookup"><span data-stu-id="0b9ef-102">How to install the Certificates for Digital Signatures</span></span>
<span data-ttu-id="0b9ef-103">以下过程列出了您必须按照安装证书以便接收和发送签名的消息的高级步骤。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending signed messages.</span></span>  
  
-   <span data-ttu-id="0b9ef-104">若要以接收签名的消息的证书存储中安装证书</span><span class="sxs-lookup"><span data-stu-id="0b9ef-104">To install the certificates in the certificates store to receive signed messages</span></span>  
  
-   <span data-ttu-id="0b9ef-105">若要安装的证书存储区中发送签名的消息的签名证书</span><span class="sxs-lookup"><span data-stu-id="0b9ef-105">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
-   <span data-ttu-id="0b9ef-106">若要配置 BizTalk 组，以便发送签名的消息</span><span class="sxs-lookup"><span data-stu-id="0b9ef-106">To configure the BizTalk Group for sending signed messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="0b9ef-107">你可以使用一个证书签名和加密操作，或可以为每个函数使用一个证书。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
> 
> [!IMPORTANT]
>  <span data-ttu-id="0b9ef-108">只能指定一个签名证书与[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]对所有出站消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-108">You can only specify one signing certificate with which [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] signs all outbound messages.</span></span> <span data-ttu-id="0b9ef-109">换而言之，不能使用不同的签名证书，具体取决于谁发送到的消息。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-109">In other words, you cannot use different signing certificates depending on who you are sending the message to.</span></span>  
  
### <a name="to-install-the-certificates-in-the-certificates-store-to-receive-signed-messages"></a><span data-ttu-id="0b9ef-110">若要以接收签名的消息的证书存储中安装证书</span><span class="sxs-lookup"><span data-stu-id="0b9ef-110">To install the certificates in the certificates store to receive signed messages</span></span>  
  
1. <span data-ttu-id="0b9ef-111">合作伙伴 A 从证书颁发机构 (CA) 请求数字签名的私钥 / 公钥对。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-111">Partner A requests a private-public key pair for digital signatures from the certification authority (CA).</span></span>  
  
2. <span data-ttu-id="0b9ef-112">合作伙伴 A 向您发送其公钥数字签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-112">Partner A sends you its public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="0b9ef-113">在[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，登录到服务器的已存储的主机实例运行将从合作伙伴 A.安装接收消息的处理程序的合作伙伴的公钥证书以验证其他人在其签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-113">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will receive messages from Partner A. Install the Partner A public key certificate to verify their signature in the Other People store.</span></span> <span data-ttu-id="0b9ef-114">下图显示了你在其中安装证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-114">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="0b9ef-115">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="0b9ef-115">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="0b9ef-116">在合作伙伴 A 中，安装合作伙伴 A 私钥证书在适当的存储中的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-116">In Partner A, install the Partner A private key certificate for signing messages in the appropriate store.</span></span> <span data-ttu-id="0b9ef-117">(如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，将发送到的消息进行签名的帐户的个人存储中安装私钥[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]。)</span><span class="sxs-lookup"><span data-stu-id="0b9ef-117">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal store for the account that will sign messages sent to [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].)</span></span>  
  
### <a name="to-install-the-signing-certificates-for-sending-signed-messages-in-the-certificates-store"></a><span data-ttu-id="0b9ef-118">若要安装的证书存储区中发送签名的消息的签名证书</span><span class="sxs-lookup"><span data-stu-id="0b9ef-118">To install the signing certificates for sending signed messages in the certificates store</span></span>  
  
1. <span data-ttu-id="0b9ef-119">在你的组织中的管理员从 CA 请求用于数字签名的私钥 / 公钥对[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]使用。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-119">An administrator in your organization requests a private-public key pair for digital signatures from the CA for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2. <span data-ttu-id="0b9ef-120">管理员发送合作伙伴 A （以及所有其他合作伙伴） 数字签名的公钥。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-120">The administrator sends Partner A (and all other partners) the public key for digital signatures.</span></span>  
  
3. <span data-ttu-id="0b9ef-121">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]，以运行将消息发送到合作伙伴 a。 安装的处理程序的主机实例的服务帐户身份登录[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]私钥证书的服务帐户的个人存储中的消息进行签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as service account for the host instance running the handler that will send messages to Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for signing messages in the personal store for the service account.</span></span> <span data-ttu-id="0b9ef-122">下图显示了你在其中安装证书的证书存储区。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="0b9ef-123">![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="0b9ef-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
4. <span data-ttu-id="0b9ef-124">在合作伙伴 A 中，安装[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]公钥证书以验证适当的存储其数字签名。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-124">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for verifying its digital signature in the appropriate store.</span></span> <span data-ttu-id="0b9ef-125">(如果合作伙伴 A 使用[!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]， [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]，或[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，在其他人存储中安装公钥。)</span><span class="sxs-lookup"><span data-stu-id="0b9ef-125">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], or [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other people store.)</span></span>  
  
### <a name="to-configure-the-biztalk-group-for-sending-signed-messages"></a><span data-ttu-id="0b9ef-126">若要配置 BizTalk 组，以便发送签名的消息</span><span class="sxs-lookup"><span data-stu-id="0b9ef-126">To configure the BizTalk Group for sending signed messages</span></span>  
  
1. <span data-ttu-id="0b9ef-127">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-127">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="0b9ef-128">右键单击**BizTalk 组**，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-128">Right-click **BizTalk Group**, and then click **Properties**.</span></span>  
  
3. <span data-ttu-id="0b9ef-129">上**组属性**对话框中，单击**证书**，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-129">On the **Group Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
4. <span data-ttu-id="0b9ef-130">上**选择证书**对话框中，选择你安装的签名证书，然后关闭所有对话框。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-130">On the **Select Certificate** dialog box, select the signing certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="0b9ef-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0b9ef-131">Next Steps</span></span>  
 <span data-ttu-id="0b9ef-132">创建一个管道以接收签名的消息[如何配置为接收签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-132">You create a pipeline to receive signed messages in [How to Configure BizTalk Server for Receiving Signed Messages](../core/how-to-configure-biztalk-server-for-receiving-signed-messages.md).</span></span>  
  
 <span data-ttu-id="0b9ef-133">创建一个管道以发送签名的消息[如何配置为发送签名消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md)。</span><span class="sxs-lookup"><span data-stu-id="0b9ef-133">You create a pipeline to send signed messages in [How to Configure BizTalk Server for Sending Signed Messages](../core/how-to-configure-biztalk-server-for-sending-signed-messages.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0b9ef-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="0b9ef-134">See Also</span></span>  
 <span data-ttu-id="0b9ef-135">[BizTalk Server 用于签名消息的证书](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span><span class="sxs-lookup"><span data-stu-id="0b9ef-135">[Certificates that BizTalk Server Uses for Signed Messages](../core/certificates-that-biztalk-server-uses-for-signed-messages.md) </span></span>  
 [<span data-ttu-id="0b9ef-136">发送和接收签名消息</span><span class="sxs-lookup"><span data-stu-id="0b9ef-136">Sending and Receiving Signed Messages</span></span>](../core/sending-and-receiving-signed-messages.md)