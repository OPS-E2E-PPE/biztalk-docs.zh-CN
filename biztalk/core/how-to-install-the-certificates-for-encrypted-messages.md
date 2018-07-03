---
title: 如何为加密消息安装证书 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e11fdb81-041c-4ba6-849d-d511ead0e8be
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c24cd9c34fef3c7d984874cc72da13030b167d0f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36994094"
---
# <a name="how-to-install-the-certificates-for-encrypted-messages"></a><span data-ttu-id="880f7-102">如何为加密消息安装证书</span><span class="sxs-lookup"><span data-stu-id="880f7-102">How to Install the Certificates for Encrypted Messages</span></span>
<span data-ttu-id="880f7-103">下面的过程列出了安装证书以便接收和发送加密消息所需遵守的高级步骤。</span><span class="sxs-lookup"><span data-stu-id="880f7-103">The following procedure lists the high-level steps that you have to follow to install the certificates for receiving and sending encrypted messages.</span></span>  
  
-   <span data-ttu-id="880f7-104">在证书存储中安装证书以进行解密</span><span class="sxs-lookup"><span data-stu-id="880f7-104">To install certificates in the certificates store for decryption</span></span>  
  
-   <span data-ttu-id="880f7-105">在证书存储中安装证书以进行加密</span><span class="sxs-lookup"><span data-stu-id="880f7-105">To install certificates in the certificates store for encryption</span></span>  
  
-   <span data-ttu-id="880f7-106">配置 BizTalk 主机以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="880f7-106">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="880f7-107">可以使用一个证书同时执行签名和加密操作，也可以对于每种功能使用一个证书。</span><span class="sxs-lookup"><span data-stu-id="880f7-107">You can use one certificate for both signing and decryption operations, or you can use one certificate for each function.</span></span>  
  
### <a name="to-install-the-decryption-certificates-in-the-certificates-store"></a><span data-ttu-id="880f7-108">在证书存储中安装解密证书</span><span class="sxs-lookup"><span data-stu-id="880f7-108">To install the decryption certificates in the certificates store</span></span>  
  
1. <span data-ttu-id="880f7-109">组织中的管理员从证书颁发机构 (CA) 请求用于加密的私钥/公钥对以供 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 使用。</span><span class="sxs-lookup"><span data-stu-id="880f7-109">An administrator in your organization requests a private-public key pair for encryption from the certification authority (CA) for [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to use.</span></span>  
  
2. <span data-ttu-id="880f7-110">管理员向合作伙伴 A 发送用于加密的公钥。</span><span class="sxs-lookup"><span data-stu-id="880f7-110">The administrator sends the public key for encryption to Partner A.</span></span>  
  
3. <span data-ttu-id="880f7-111">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，使用主机实例（该主机实例运行将从合作伙伴 A 接收消息的处理程序）的服务帐户登录。在服务帐户的个人存储中安装用于解密消息的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 私钥证书。</span><span class="sxs-lookup"><span data-stu-id="880f7-111">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on as the service account for the host instance running the handler that will receive messages from Partner A. Install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] private key certificate for decrypting messages in the personal store for the service account.</span></span> <span data-ttu-id="880f7-112">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="880f7-112">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="880f7-113">![若要接收安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span><span class="sxs-lookup"><span data-stu-id="880f7-113">![Certificates required to receive secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-receive.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Receive")</span></span>  
  
4. <span data-ttu-id="880f7-114">在合作伙伴 A 中，在适当的存储中安装 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 公钥证书，以便对发送到合作伙伴 A 的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="880f7-114">In Partner A, install the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] public key certificate for encrypting messages sent to Partner A in the appropriate store.</span></span> <span data-ttu-id="880f7-115">（如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]  [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、 [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请安装“其他人”存储区中的公钥）。</span><span class="sxs-lookup"><span data-stu-id="880f7-115">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the public key in the Other People store.)</span></span>  
  
### <a name="to-install-the-encryption-certificates-in-the-certificates-store"></a><span data-ttu-id="880f7-116">在证书存储中安装加密证书</span><span class="sxs-lookup"><span data-stu-id="880f7-116">To install the encryption certificates in the certificates store</span></span>  
  
1. <span data-ttu-id="880f7-117">合作伙伴 A 从 CA 请求用于加密的私钥/公钥对。</span><span class="sxs-lookup"><span data-stu-id="880f7-117">Partner A requests a private-public key pair for encryption from the CA.</span></span>  
  
2. <span data-ttu-id="880f7-118">合作伙伴 A 在适当存储中安装私钥证书，以用于解密消息。</span><span class="sxs-lookup"><span data-stu-id="880f7-118">Partner A installs the private key certificate for decrypting the messages in the appropriate store.</span></span> <span data-ttu-id="880f7-119">（如果合作伙伴 A 使用 [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)]、[!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)]、[!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)]，请安装个人证书存储中的私钥）。</span><span class="sxs-lookup"><span data-stu-id="880f7-119">(If Partner A is using [!INCLUDE[btsWin2kSvr](../includes/btswin2ksvr-md.md)], [!INCLUDE[btsWinSvr2k3](../includes/btswinsvr2k3-md.md)], [!INCLUDE[btsWinSvr2k8](../includes/btswinsvr2k8-md.md)], install the private key in the personal certificate store.)</span></span>  
  
3. <span data-ttu-id="880f7-120">合作伙伴 A 向您发送它的公钥，将使用该公钥对发送到合作伙伴 A 的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="880f7-120">Partner A sends you its public key for encrypting messages sent to Partner A.</span></span>  
  
4. <span data-ttu-id="880f7-121">在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 中，登录到具有主机实例（该主机实例运行将消息发送到合作伙伴 A 的处理程序）的服务器上。在“其他人”存储中安装合作伙伴 A 的公钥证书，以便对发送至合作伙伴 A 的消息进行加密。</span><span class="sxs-lookup"><span data-stu-id="880f7-121">In [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)], log on to the server that has a host instance running a handler that will send messages to Partner A. Install the Partner A public key certificate for encrypting messages sent to Partner A in the Other People store.</span></span> <span data-ttu-id="880f7-122">下图显示您安装证书的证书存储。</span><span class="sxs-lookup"><span data-stu-id="880f7-122">The following figure shows the certificate store where you install the certificate.</span></span>  
  
    <span data-ttu-id="880f7-123">![若要发送安全消息所需证书](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span><span class="sxs-lookup"><span data-stu-id="880f7-123">![Certificates required to send secure messages](../core/media/bpi-sp-msgsec-certmgmt-certstores-send.gif "BPI_SP_MSGSEC_CertMgmt_CertStores_Send")</span></span>  
  
### <a name="to-configure-biztalk-hosts-for-receiving-encrypted-messages"></a><span data-ttu-id="880f7-124">配置 BizTalk 主机以便接收加密消息</span><span class="sxs-lookup"><span data-stu-id="880f7-124">To configure BizTalk hosts for receiving encrypted messages</span></span>  
  
1. <span data-ttu-id="880f7-125">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="880f7-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="880f7-126">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，展开**平台设置**，展开**主机**。</span><span class="sxs-lookup"><span data-stu-id="880f7-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, expand **Platform Settings**, expand **Hosts**.</span></span>  
  
   1.  <span data-ttu-id="880f7-127">在右窗格中，右键单击以便接收加密的消息，处理程序的 BizTalk 主机，然后单击**属性**。</span><span class="sxs-lookup"><span data-stu-id="880f7-127">On the right pane, right-click a BizTalk host that is the handler for receiving the encrypted messages, and then click **Properties**.</span></span>  
  
   2.  <span data-ttu-id="880f7-128">上**主机属性**对话框中，单击**证书**，单击**浏览**。</span><span class="sxs-lookup"><span data-stu-id="880f7-128">On the **Host Properties** dialog box, click **Certificate**, click **Browse**.</span></span>  
  
   3.  <span data-ttu-id="880f7-129">上**选择证书**对话框中，选择你安装的解密证书，然后关闭所有对话框。</span><span class="sxs-lookup"><span data-stu-id="880f7-129">On the **Select Certificate** dialog box, select the decryption certificate that you installed, and then close all of the dialog boxes.</span></span>  
  
       > [!NOTE]
       >  <span data-ttu-id="880f7-130">有关详细信息，请参阅[如何修改主机属性](../core/how-to-modify-host-properties.md)。</span><span class="sxs-lookup"><span data-stu-id="880f7-130">For more information, see [How to Modify Host Properties](../core/how-to-modify-host-properties.md).</span></span>  
  
## <a name="next-steps"></a><span data-ttu-id="880f7-131">后续步骤</span><span class="sxs-lookup"><span data-stu-id="880f7-131">Next Steps</span></span>  
 <span data-ttu-id="880f7-132">创建管道以便接收加密的消息中[如何配置为接收加密消息的 BizTalk Server](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="880f7-132">You create a pipeline to receive encrypted messages in [How to Configure BizTalk Server for Receiving Encrypted Messages](../core/how-to-configure-biztalk-server-for-receiving-encrypted-messages.md)</span></span>  
  
 <span data-ttu-id="880f7-133">创建管道以便发送加密的消息[如何为发送加密消息配置 BizTalk Server](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span><span class="sxs-lookup"><span data-stu-id="880f7-133">You create a pipeline to send encrypted messages in [How to Configure BizTalk Server for Sending Encrypted Messages](../core/how-to-configure-biztalk-server-for-sending-encrypted-messages.md)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="880f7-134">请参阅</span><span class="sxs-lookup"><span data-stu-id="880f7-134">See Also</span></span>  
 <span data-ttu-id="880f7-135">[BizTalk Server 用来加密消息的证书](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span><span class="sxs-lookup"><span data-stu-id="880f7-135">[Certificates that BizTalk Server Uses for Encrypted Messages](../core/certificates-that-biztalk-server-uses-for-encrypted-messages.md) </span></span>  
 [<span data-ttu-id="880f7-136">发送和接收加密消息</span><span class="sxs-lookup"><span data-stu-id="880f7-136">Sending and Receiving Encrypted Messages</span></span>](../core/sending-and-receiving-encrypted-messages.md)