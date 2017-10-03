---
title: "手动配置到 SAP 适配器的物理端口绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 725a26eed4502e0a3d1eca8ed5f1429988590614
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a><span data-ttu-id="5008b-102">手动配置到 SAP 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="5008b-102">Manually configure a physical port binding to the SAP adapter</span></span>
<span data-ttu-id="5008b-103">配置[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]为 WCF 自定义绑定使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5008b-103">Configure the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> 

## <a name="port-overview"></a><span data-ttu-id="5008b-104">端口概述</span><span class="sxs-lookup"><span data-stu-id="5008b-104">Port overview</span></span>
<span data-ttu-id="5008b-105">在部署后适配器，你将能够发送和接收来自 SAP 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="5008b-105">After deploying the adapter, you will be able to send and receive messages from the SAP system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="5008b-106">部署该适配器的步骤有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="5008b-106">The steps for deploying the adapter vary depending on:</span></span>  
  
-   <span data-ttu-id="5008b-107">之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="5008b-107">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="5008b-108">你可以选择配置发送、 接收、 发送-接收或接收发送端口。</span><span class="sxs-lookup"><span data-stu-id="5008b-108">You may choose to configure a Send, Receive, Send-Receive, or a Receive-Send port.</span></span> <span data-ttu-id="5008b-109">下表对这些选项进行了概括介绍：</span><span class="sxs-lookup"><span data-stu-id="5008b-109">Your choices are summarized in the following table:</span></span>  
  
    |<span data-ttu-id="5008b-110">端口方向</span><span class="sxs-lookup"><span data-stu-id="5008b-110">Port direction</span></span>|<span data-ttu-id="5008b-111">通信模式</span><span class="sxs-lookup"><span data-stu-id="5008b-111">Communication pattern</span></span>|<span data-ttu-id="5008b-112">可供选择的通信的方向</span><span class="sxs-lookup"><span data-stu-id="5008b-112">Direction of communication to choose from</span></span>|  
    |---|---|---|  
    |<span data-ttu-id="5008b-113">Send</span><span class="sxs-lookup"><span data-stu-id="5008b-113">Send</span></span>|<span data-ttu-id="5008b-114">单向</span><span class="sxs-lookup"><span data-stu-id="5008b-114">One-way</span></span>|<span data-ttu-id="5008b-115">我将始终发送消息上此端口。</span><span class="sxs-lookup"><span data-stu-id="5008b-115">I will always be sending messages on this port.</span></span>|  
    |<span data-ttu-id="5008b-116">Receive</span><span class="sxs-lookup"><span data-stu-id="5008b-116">Receive</span></span>|<span data-ttu-id="5008b-117">单向</span><span class="sxs-lookup"><span data-stu-id="5008b-117">One-way</span></span>|<span data-ttu-id="5008b-118">始终在此端口上接收消息。</span><span class="sxs-lookup"><span data-stu-id="5008b-118">I will always be receiving messages on this port.</span></span>|  
    |<span data-ttu-id="5008b-119">发送-接收</span><span class="sxs-lookup"><span data-stu-id="5008b-119">Send-Receive</span></span>|<span data-ttu-id="5008b-120">请求-响应</span><span class="sxs-lookup"><span data-stu-id="5008b-120">Request-response</span></span>|<span data-ttu-id="5008b-121">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="5008b-121">I will be sending a request and receiving a response.</span></span>|  
    |<span data-ttu-id="5008b-122">接收-发送</span><span class="sxs-lookup"><span data-stu-id="5008b-122">Receive-Send</span></span>|<span data-ttu-id="5008b-123">请求作出响应</span><span class="sxs-lookup"><span data-stu-id="5008b-123">Solicit-response</span></span>|<span data-ttu-id="5008b-124">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="5008b-124">I will be receiving a request and sending a response.</span></span>|  
  
     <span data-ttu-id="5008b-125">有关详细信息，请参阅[创建发送端口](../../core/how-to-create-a-send-port2.md)，或[创建接收端口](../../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="5008b-125">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span>
  
-   <span data-ttu-id="5008b-126">是否适配器将消息发送到 SAP 系统，或从 SAP 系统接收消息。</span><span class="sxs-lookup"><span data-stu-id="5008b-126">Whether the adapter sends messages to the SAP system or receives messages from the SAP system.</span></span> <span data-ttu-id="5008b-127">具体取决于是否想要发送或接收消息，你将创建一个发送或接收端口。</span><span class="sxs-lookup"><span data-stu-id="5008b-127">Depending on whether you want to send or receive messages, you will create a send or receive port.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="5008b-128">你也可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="5008b-128">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="5008b-129">有关配置使用此绑定文件的端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件，以便 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="5008b-129">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="5008b-130">在本节中</span><span class="sxs-lookup"><span data-stu-id="5008b-130">In this section</span></span>  
  
-   [<span data-ttu-id="5008b-131">配置使用 WCF 自定义适配器和 Oracle 数据库适配器的端口</span><span class="sxs-lookup"><span data-stu-id="5008b-131">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="5008b-132">配置使用 WCF SAP 适配器的端口</span><span class="sxs-lookup"><span data-stu-id="5008b-132">Configure a port using the WCF-SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="5008b-133">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5008b-133">See Also</span></span>  
[<span data-ttu-id="5008b-134">若要创建的 SAP 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="5008b-134">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)