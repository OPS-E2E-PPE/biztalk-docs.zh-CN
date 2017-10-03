---
title: "手动配置到 Siebel 适配器的物理端口绑定 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ed94ca9f6a44919684d36a1be931cbb33f746377
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a><span data-ttu-id="f01d3-102">手动配置到 Siebel 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="f01d3-102">Manually configure a physical port binding to the Siebel adapter</span></span>
<span data-ttu-id="f01d3-103">本部分提供有关配置信息[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]为 WCF 自定义绑定使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f01d3-103">This section provides information about configuring the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="f01d3-104">在部署后适配器，你将能够发送和接收来自 Siebel 系统的消息，通过使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="f01d3-104">After deploying the adapter, you will be able to send and receive messages from the Siebel system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="f01d3-105">部署该适配器的步骤有所不同具体取决于之间的通信的方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="f01d3-105">The steps for deploying the adapter vary depending on the direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="f01d3-106">你可以选择配置发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="f01d3-106">You may choose to configure a Send or a Send-Receive port.</span></span> <span data-ttu-id="f01d3-107">下表对这些选项进行了概括介绍：</span><span class="sxs-lookup"><span data-stu-id="f01d3-107">Your choices are summarized in the following table:</span></span>  
  
|<span data-ttu-id="f01d3-108">端口方向</span><span class="sxs-lookup"><span data-stu-id="f01d3-108">Port direction</span></span>|<span data-ttu-id="f01d3-109">通信模式</span><span class="sxs-lookup"><span data-stu-id="f01d3-109">Communication pattern</span></span>|<span data-ttu-id="f01d3-110">可供选择的通信的方向</span><span class="sxs-lookup"><span data-stu-id="f01d3-110">Direction of communication to choose from</span></span>|  
|---|---|---|  
|<span data-ttu-id="f01d3-111">Send</span><span class="sxs-lookup"><span data-stu-id="f01d3-111">Send</span></span>|<span data-ttu-id="f01d3-112">单向</span><span class="sxs-lookup"><span data-stu-id="f01d3-112">One-way</span></span>|<span data-ttu-id="f01d3-113">我将始终发送消息上此端口。</span><span class="sxs-lookup"><span data-stu-id="f01d3-113">I will always be sending messages on this port.</span></span>|  
|<span data-ttu-id="f01d3-114">发送-接收</span><span class="sxs-lookup"><span data-stu-id="f01d3-114">Send-Receive</span></span>|<span data-ttu-id="f01d3-115">请求-响应</span><span class="sxs-lookup"><span data-stu-id="f01d3-115">Request-response</span></span>|<span data-ttu-id="f01d3-116">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="f01d3-116">I will be sending a request and receiving a response.</span></span>|  
  
 <span data-ttu-id="f01d3-117">有关详细信息，请参阅[创建和配置发送端口](../../core/creating-and-configuring-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="f01d3-117">For more information, see [Creating and Configuring Send Ports](../../core/creating-and-configuring-send-ports.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="f01d3-118">接收端口不支持，因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会启用从 Siebel 系统的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="f01d3-118">Receive ports are not supported because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not enable inbound operations from the Siebel system.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f01d3-119">你还可以通过导入创建的绑定配置文件配置 WCF 自定义发送端口[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="f01d3-119">You can also configure the WCF-Custom send ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="f01d3-120">有关配置使用此绑定文件的端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件，以便 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="f01d3-120">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
 
  
## <a name="see-also"></a><span data-ttu-id="f01d3-121">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f01d3-121">See Also</span></span>  
[<span data-ttu-id="f01d3-122">构建基块创建带有 Siebel 适配器 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="f01d3-122">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)