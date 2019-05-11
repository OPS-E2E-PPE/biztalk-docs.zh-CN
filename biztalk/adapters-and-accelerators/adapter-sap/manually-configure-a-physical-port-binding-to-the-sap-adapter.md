---
title: 手动配置到 SAP 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deploying, sending messages to the SAP system
- physical port binding, manually configuring
- deploying, receiving messages from the SAP system
ms.assetid: c4f547aa-5514-4ca9-809b-d8d395de419c
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3011bea808e59ec0ee80f3ac030937a9987d9233
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65373250"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sap-adapter"></a><span data-ttu-id="c6c06-102">手动配置到 SAP 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="c6c06-102">Manually configure a physical port binding to the SAP adapter</span></span>
<span data-ttu-id="c6c06-103">配置[!INCLUDE[adaptersap](../../includes/adaptersap-md.md)]为使用自定义 WCF 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c6c06-103">Configure the [!INCLUDE[adaptersap](../../includes/adaptersap-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> 

## <a name="port-overview"></a><span data-ttu-id="c6c06-104">端口概述</span><span class="sxs-lookup"><span data-stu-id="c6c06-104">Port overview</span></span>
<span data-ttu-id="c6c06-105">在部署后，适配器，您将能够发送和接收来自 SAP 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="c6c06-105">After deploying the adapter, you will be able to send and receive messages from the SAP system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="c6c06-106">部署该适配器的步骤会有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="c6c06-106">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="c6c06-107">之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="c6c06-107">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersap_short](../../includes/adaptersap-short-md.md)].</span></span> <span data-ttu-id="c6c06-108">您可以选择配置发送、 接收、 发送-接收端口或接收发送端口。</span><span class="sxs-lookup"><span data-stu-id="c6c06-108">You may choose to configure a Send, Receive, Send-Receive, or a Receive-Send port.</span></span> <span data-ttu-id="c6c06-109">下表总结了你的选择：</span><span class="sxs-lookup"><span data-stu-id="c6c06-109">Your choices are summarized in the following table:</span></span>  
  
  |<span data-ttu-id="c6c06-110">端口方向</span><span class="sxs-lookup"><span data-stu-id="c6c06-110">Port direction</span></span>|<span data-ttu-id="c6c06-111">通信模式</span><span class="sxs-lookup"><span data-stu-id="c6c06-111">Communication pattern</span></span>|<span data-ttu-id="c6c06-112">可供选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="c6c06-112">Direction of communication to choose from</span></span>|  
  |---|---|---|  
  |<span data-ttu-id="c6c06-113">Send</span><span class="sxs-lookup"><span data-stu-id="c6c06-113">Send</span></span>|<span data-ttu-id="c6c06-114">单向</span><span class="sxs-lookup"><span data-stu-id="c6c06-114">One-way</span></span>|<span data-ttu-id="c6c06-115">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="c6c06-115">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="c6c06-116">Receive</span><span class="sxs-lookup"><span data-stu-id="c6c06-116">Receive</span></span>|<span data-ttu-id="c6c06-117">单向</span><span class="sxs-lookup"><span data-stu-id="c6c06-117">One-way</span></span>|<span data-ttu-id="c6c06-118">我始终将接收此端口上的消息。</span><span class="sxs-lookup"><span data-stu-id="c6c06-118">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="c6c06-119">发送接收</span><span class="sxs-lookup"><span data-stu-id="c6c06-119">Send-Receive</span></span>|<span data-ttu-id="c6c06-120">请求-响应</span><span class="sxs-lookup"><span data-stu-id="c6c06-120">Request-response</span></span>|<span data-ttu-id="c6c06-121">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="c6c06-121">I will be sending a request and receiving a response.</span></span>|  
  |<span data-ttu-id="c6c06-122">接收发送</span><span class="sxs-lookup"><span data-stu-id="c6c06-122">Receive-Send</span></span>|<span data-ttu-id="c6c06-123">要求响应</span><span class="sxs-lookup"><span data-stu-id="c6c06-123">Solicit-response</span></span>|<span data-ttu-id="c6c06-124">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="c6c06-124">I will be receiving a request and sending a response.</span></span>|  
  
   <span data-ttu-id="c6c06-125">有关详细信息，请参阅[创建一个发送端口](../../core/how-to-create-a-send-port2.md)，或[创建一个接收端口](../../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c06-125">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span>
  
- <span data-ttu-id="c6c06-126">是否该适配器将消息发送到 SAP 系统，或接收来自 SAP 系统的消息。</span><span class="sxs-lookup"><span data-stu-id="c6c06-126">Whether the adapter sends messages to the SAP system or receives messages from the SAP system.</span></span> <span data-ttu-id="c6c06-127">具体取决于是否想要发送或接收消息，将创建一个发送或接收端口。</span><span class="sxs-lookup"><span data-stu-id="c6c06-127">Depending on whether you want to send or receive messages, you will create a send or receive port.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="c6c06-128">此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="c6c06-128">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="c6c06-129">有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件与 SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md)。</span><span class="sxs-lookup"><span data-stu-id="c6c06-129">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to SAP](../../adapters-and-accelerators/adapter-sap/configure-a-physical-port-binding-using-a-port-binding-file-to-sap.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="c6c06-130">本节内容</span><span class="sxs-lookup"><span data-stu-id="c6c06-130">In this section</span></span>  
  
-   [<span data-ttu-id="c6c06-131">使用 WCF 自定义适配器和 Oracle 数据库适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="c6c06-131">Configure a port using the WCF-custom adapter and Oracle Database adapter</span></span>](../../adapters-and-accelerators/adapter-oracle-database/configure-a-port-using-the-wcf-custom-adapter-and-oracle-database-adapter.md)  
  
-   [<span data-ttu-id="c6c06-132">使用 WCF-SAP 适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="c6c06-132">Configure a port using the WCF-SAP adapter</span></span>](../../adapters-and-accelerators/adapter-sap/configure-a-port-using-the-wcf-sap-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="c6c06-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="c6c06-133">See Also</span></span>  
[<span data-ttu-id="c6c06-134">生成块以创建 SAP 应用程序</span><span class="sxs-lookup"><span data-stu-id="c6c06-134">Building blocks to create SAP applications</span></span>](../../adapters-and-accelerators/adapter-sap/building-blocks-to-create-sap-applications.md)