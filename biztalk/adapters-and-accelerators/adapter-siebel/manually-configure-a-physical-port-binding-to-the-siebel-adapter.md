---
title: 手动配置到 Siebel 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- physical port binding, manually configuring
- how to, manually configure adapters for sending messages to a Siebel system
ms.assetid: a1445b8a-440f-45e8-96e9-a13142ca87c6
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 576188121d5dd33541440c8bb34d7b59fc97fb47
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65371466"
---
# <a name="manually-configure-a-physical-port-binding-to-the-siebel-adapter"></a><span data-ttu-id="e0f57-102">手动配置到 Siebel 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="e0f57-102">Manually configure a physical port binding to the Siebel adapter</span></span>
<span data-ttu-id="e0f57-103">本部分提供有关配置信息[!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)]为使用自定义 WCF 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e0f57-103">This section provides information about configuring the [!INCLUDE[adaptersiebel](../../includes/adaptersiebel-md.md)] as a WCF custom binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="e0f57-104">在部署后，适配器，您将能够发送和接收消息从 Siebel 系统使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="e0f57-104">After deploying the adapter, you will be able to send and receive messages from the Siebel system by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration Console.</span></span> <span data-ttu-id="e0f57-105">部署该适配器的步骤而异的之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="e0f57-105">The steps for deploying the adapter vary depending on the direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)].</span></span> <span data-ttu-id="e0f57-106">您可以选择配置发送端口或发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="e0f57-106">You may choose to configure a Send or a Send-Receive port.</span></span> <span data-ttu-id="e0f57-107">下表总结了你的选择：</span><span class="sxs-lookup"><span data-stu-id="e0f57-107">Your choices are summarized in the following table:</span></span>  
  
|<span data-ttu-id="e0f57-108">端口方向</span><span class="sxs-lookup"><span data-stu-id="e0f57-108">Port direction</span></span>|<span data-ttu-id="e0f57-109">通信模式</span><span class="sxs-lookup"><span data-stu-id="e0f57-109">Communication pattern</span></span>|<span data-ttu-id="e0f57-110">可供选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="e0f57-110">Direction of communication to choose from</span></span>|  
|---|---|---|  
|<span data-ttu-id="e0f57-111">Send</span><span class="sxs-lookup"><span data-stu-id="e0f57-111">Send</span></span>|<span data-ttu-id="e0f57-112">单向</span><span class="sxs-lookup"><span data-stu-id="e0f57-112">One-way</span></span>|<span data-ttu-id="e0f57-113">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="e0f57-113">I will always be sending messages on this port.</span></span>|  
|<span data-ttu-id="e0f57-114">发送接收</span><span class="sxs-lookup"><span data-stu-id="e0f57-114">Send-Receive</span></span>|<span data-ttu-id="e0f57-115">请求-响应</span><span class="sxs-lookup"><span data-stu-id="e0f57-115">Request-response</span></span>|<span data-ttu-id="e0f57-116">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="e0f57-116">I will be sending a request and receiving a response.</span></span>|  
  
 <span data-ttu-id="e0f57-117">有关详细信息，请参阅[创建和配置发送端口](../../core/creating-and-configuring-send-ports.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f57-117">For more information, see [Creating and Configuring Send Ports](../../core/creating-and-configuring-send-ports.md).</span></span>
  
> [!NOTE]
>  <span data-ttu-id="e0f57-118">接收端口不支持，因为[!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)]不会启用从 Siebel 系统的入站的操作。</span><span class="sxs-lookup"><span data-stu-id="e0f57-118">Receive ports are not supported because the [!INCLUDE[adaptersiebel_short](../../includes/adaptersiebel-short-md.md)] does not enable inbound operations from the Siebel system.</span></span>  
> 
> [!NOTE]
>  <span data-ttu-id="e0f57-119">此外可以通过导入创建的绑定配置文件配置 Wcf-custom 发送端口[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="e0f57-119">You can also configure the WCF-Custom send ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="e0f57-120">有关使用此绑定文件配置端口的说明，请参阅[配置物理端口绑定使用的端口绑定文件到 Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md)。</span><span class="sxs-lookup"><span data-stu-id="e0f57-120">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Siebel](../../adapters-and-accelerators/adapter-siebel/configure-a-physical-port-binding-using-a-port-binding-file-to-siebel.md).</span></span>
  
 
  
## <a name="see-also"></a><span data-ttu-id="e0f57-121">请参阅</span><span class="sxs-lookup"><span data-stu-id="e0f57-121">See Also</span></span>  
[<span data-ttu-id="e0f57-122">若要创建与 Siebel 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="e0f57-122">Building blocks to create BizTalk applications with the Siebel adapter</span></span>](../../adapters-and-accelerators/adapter-siebel/building-blocks-to-create-biztalk-applications-with-the-siebel-adapter.md)