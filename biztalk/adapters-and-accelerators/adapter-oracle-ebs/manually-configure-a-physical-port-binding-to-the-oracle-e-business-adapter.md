---
title: 手动配置到 Oracle E-business 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 07369428-7b54-4d90-8c63-ba14e67fdbdd
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 354b3937036e9cff832b3c0898ea1fa8d41c6377
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36966678"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a><span data-ttu-id="c454d-102">手动配置到 Oracle E-business 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="c454d-102">Manually configure a physical port binding to the Oracle E-Business adapter</span></span>
<span data-ttu-id="c454d-103">本部分提供有关配置信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]作为 WCF 自定义绑定或通过使用 Wcf-oracleebs 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c454d-103">This section provides information about configuring the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] as a WCF custom binding or as a WCF-OracleEBS port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c454d-104">在部署后，适配器，您将能够发送和接收消息从 Oracle E-business Suite 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c454d-104">After deploying the adapter, you will be able to send and receive messages from Oracle E-Business Suite by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c454d-105">部署该适配器的步骤会有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="c454d-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="c454d-106">之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c454d-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="c454d-107">您可以选择配置发送、 接收、 发送-接收或发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="c454d-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="c454d-108">下表总结了你的选择。</span><span class="sxs-lookup"><span data-stu-id="c454d-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="c454d-109">端口方向</span><span class="sxs-lookup"><span data-stu-id="c454d-109">Port direction</span></span>|<span data-ttu-id="c454d-110">通信模式</span><span class="sxs-lookup"><span data-stu-id="c454d-110">Communication pattern</span></span>|<span data-ttu-id="c454d-111">可供选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="c454d-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="c454d-112">Send</span><span class="sxs-lookup"><span data-stu-id="c454d-112">Send</span></span>|<span data-ttu-id="c454d-113">单向</span><span class="sxs-lookup"><span data-stu-id="c454d-113">One-way</span></span>|<span data-ttu-id="c454d-114">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="c454d-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="c454d-115">Receive</span><span class="sxs-lookup"><span data-stu-id="c454d-115">Receive</span></span>|<span data-ttu-id="c454d-116">单向</span><span class="sxs-lookup"><span data-stu-id="c454d-116">One-way</span></span>|<span data-ttu-id="c454d-117">始终在此端口上接收消息。</span><span class="sxs-lookup"><span data-stu-id="c454d-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="c454d-118">发送接收</span><span class="sxs-lookup"><span data-stu-id="c454d-118">Send-receive</span></span>|<span data-ttu-id="c454d-119">请求-响应</span><span class="sxs-lookup"><span data-stu-id="c454d-119">Request-response</span></span>|<span data-ttu-id="c454d-120">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="c454d-120">I will be sending a request and receiving a response.</span></span>|  
  |<span data-ttu-id="c454d-121">接收发送</span><span class="sxs-lookup"><span data-stu-id="c454d-121">Receive-send</span></span>|<span data-ttu-id="c454d-122">要求响应</span><span class="sxs-lookup"><span data-stu-id="c454d-122">Solicit-response</span></span>|<span data-ttu-id="c454d-123">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="c454d-123">I will be receiving a request and sending a response.</span></span>|  
  
   <span data-ttu-id="c454d-124">有关详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]帮助文档，网址[ http://go.microsoft.com/fwlink/?LinkID=101130 ](http://go.microsoft.com/fwlink/?LinkID=101130)。</span><span class="sxs-lookup"><span data-stu-id="c454d-124">For more information, see the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Help documentation at [http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130).</span></span>  
  
- <span data-ttu-id="c454d-125">是否将适配器发送消息或接收来自 Oracle E-business Suite 的消息。</span><span class="sxs-lookup"><span data-stu-id="c454d-125">Whether the adapter sends messages to or receives messages from Oracle E-Business Suite.</span></span> <span data-ttu-id="c454d-126">具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。</span><span class="sxs-lookup"><span data-stu-id="c454d-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c454d-127">此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="c454d-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="c454d-128">有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用端口绑定文件到 Oracle E-business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="c454d-128">For instructions on configuring ports using this binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="c454d-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="c454d-129">In This Section</span></span>  
  
-   [<span data-ttu-id="c454d-130">配置使用 WCF 自定义适配器和 Oracle E-business Suite 的端口</span><span class="sxs-lookup"><span data-stu-id="c454d-130">Configuring a Port Using the WCF-Custom Adapter and Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="c454d-131">配置使用 Wcf-oracleebs 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="c454d-131">Configuring a Port Using the WCF-OracleEBS Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="c454d-132">请参阅</span><span class="sxs-lookup"><span data-stu-id="c454d-132">See Also</span></span>  
 [<span data-ttu-id="c454d-133">若要创建 Oracle E-business Suite 的应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="c454d-133">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)