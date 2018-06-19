---
title: 手动配置到 Oracle E-business 适配器的物理端口绑定 |Microsoft 文档
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
ms.openlocfilehash: 24ea54009ba97732cbcf6f248127b078c1c9ed05
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22216413"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-e-business-adapter"></a><span data-ttu-id="1ad64-102">手动配置到 Oracle E-business 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="1ad64-102">Manually configure a physical port binding to the Oracle E-Business adapter</span></span>
<span data-ttu-id="1ad64-103">本部分提供有关配置信息[!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)]作为 WCF 自定义绑定或通过使用 WCF OracleEBS 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1ad64-103">This section provides information about configuring the [!INCLUDE[adapteroracleebusinesslong](../../includes/adapteroracleebusinesslong-md.md)] as a WCF custom binding or as a WCF-OracleEBS port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="1ad64-104">在部署后适配器，你将能够发送和接收来自 Oracle E-business Suite 的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="1ad64-104">After deploying the adapter, you will be able to send and receive messages from Oracle E-Business Suite by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="1ad64-105">部署该适配器的步骤有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="1ad64-105">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="1ad64-106">之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="1ad64-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)].</span></span> <span data-ttu-id="1ad64-107">你可以选择配置发送、 接收、 发送-接收或接收发送端口。</span><span class="sxs-lookup"><span data-stu-id="1ad64-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="1ad64-108">下表概述了你的选择。</span><span class="sxs-lookup"><span data-stu-id="1ad64-108">Your choices are summarized in the following table.</span></span>  
  
    |<span data-ttu-id="1ad64-109">端口方向</span><span class="sxs-lookup"><span data-stu-id="1ad64-109">Port direction</span></span>|<span data-ttu-id="1ad64-110">通信模式</span><span class="sxs-lookup"><span data-stu-id="1ad64-110">Communication pattern</span></span>|<span data-ttu-id="1ad64-111">可供选择的通信的方向</span><span class="sxs-lookup"><span data-stu-id="1ad64-111">Direction of communication to choose from</span></span>|  
    |--------------------|---------------------------|-----------------------------------------------|  
    |<span data-ttu-id="1ad64-112">Send</span><span class="sxs-lookup"><span data-stu-id="1ad64-112">Send</span></span>|<span data-ttu-id="1ad64-113">单向</span><span class="sxs-lookup"><span data-stu-id="1ad64-113">One-way</span></span>|<span data-ttu-id="1ad64-114">我将始终发送消息上此端口。</span><span class="sxs-lookup"><span data-stu-id="1ad64-114">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="1ad64-115">Receive</span><span class="sxs-lookup"><span data-stu-id="1ad64-115">Receive</span></span>|<span data-ttu-id="1ad64-116">单向</span><span class="sxs-lookup"><span data-stu-id="1ad64-116">One-way</span></span>|<span data-ttu-id="1ad64-117">始终在此端口上接收消息。</span><span class="sxs-lookup"><span data-stu-id="1ad64-117">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="1ad64-118">发送接收</span><span class="sxs-lookup"><span data-stu-id="1ad64-118">Send-receive</span></span>|<span data-ttu-id="1ad64-119">请求-响应</span><span class="sxs-lookup"><span data-stu-id="1ad64-119">Request-response</span></span>|<span data-ttu-id="1ad64-120">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="1ad64-120">I will be sending a request and receiving a response.</span></span>|  
    |<span data-ttu-id="1ad64-121">接收发送</span><span class="sxs-lookup"><span data-stu-id="1ad64-121">Receive-send</span></span>|<span data-ttu-id="1ad64-122">请求作出响应</span><span class="sxs-lookup"><span data-stu-id="1ad64-122">Solicit-response</span></span>|<span data-ttu-id="1ad64-123">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="1ad64-123">I will be receiving a request and sending a response.</span></span>|  
  
     <span data-ttu-id="1ad64-124">有关详细信息，请参阅[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]帮助文档，网址[http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130)。</span><span class="sxs-lookup"><span data-stu-id="1ad64-124">For more information, see the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Help documentation at [http://go.microsoft.com/fwlink/?LinkID=101130](http://go.microsoft.com/fwlink/?LinkID=101130).</span></span>  
  
-   <span data-ttu-id="1ad64-125">适配器是否发送到消息或接收来自 Oracle E-business Suite 的消息。</span><span class="sxs-lookup"><span data-stu-id="1ad64-125">Whether the adapter sends messages to or receives messages from Oracle E-Business Suite.</span></span> <span data-ttu-id="1ad64-126">具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。</span><span class="sxs-lookup"><span data-stu-id="1ad64-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1ad64-127">你也可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ad64-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="1ad64-128">有关配置使用此绑定文件的端口的说明，请参阅[物理端口绑定使用端口绑定文件到 Oracle E-business Suite 配置](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md)。</span><span class="sxs-lookup"><span data-stu-id="1ad64-128">For instructions on configuring ports using this binding file, see [Configure a Physical Port Binding Using a Port Binding File to Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-ebs.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="1ad64-129">本节内容</span><span class="sxs-lookup"><span data-stu-id="1ad64-129">In This Section</span></span>  
  
-   [<span data-ttu-id="1ad64-130">配置端口使用 WCF 自定义适配器和 Oracle E-business Suite</span><span class="sxs-lookup"><span data-stu-id="1ad64-130">Configuring a Port Using the WCF-Custom Adapter and Oracle E-Business Suite</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-custom-adapter-and-oracle-e-business-suite.md)  
  
-   [<span data-ttu-id="1ad64-131">配置使用 WCF OracleEBS 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="1ad64-131">Configuring a Port Using the WCF-OracleEBS Adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/configure-a-port-using-the-wcf-oracleebs-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="1ad64-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1ad64-132">See Also</span></span>  
 [<span data-ttu-id="1ad64-133">创建 Oracle E-business Suite 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="1ad64-133">Building blocks to create Oracle E-Business Suite applications</span></span>](../../adapters-and-accelerators/adapter-oracle-ebs/building-blocks-to-create-oracle-e-business-suite-applications.md)