---
title: 手动配置到 Oracle 数据库适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- messages, sending to an Oracle database
- messages, receiving from an Oracle database
- physical port binding, manually configuring
ms.assetid: 6b118236-e9eb-494e-96b2-969c7064943d
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 79e002762175eb847385617e2efd570d342b1c3a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36976200"
---
# <a name="manually-configure-a-physical-port-binding-to-the-oracle-database-adapter"></a><span data-ttu-id="a7b1f-102">手动配置到 Oracle 数据库适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="a7b1f-102">Manually configure a physical port binding to the Oracle Database Adapter</span></span>
<span data-ttu-id="a7b1f-103">本部分提供有关配置信息[!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)]作为 WCF 自定义绑定或通过使用 Wcf-oracledb 绑定[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-103">This section provides information about configuring the [!INCLUDE[adapteroracle](../../includes/adapteroracle-md.md)] as a WCF-Custom binding or WCF-OracleDB binding by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a7b1f-104">在部署后，适配器，您将能够发送和接收消息从 Oracle 数据库使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-104">After deploying the adapter, you will be able to send and receive messages from the Oracle database by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="a7b1f-105">部署该适配器的步骤会有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="a7b1f-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="a7b1f-106">BizTalk Server 之间的通信的方向和[!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-106">The direction of communication between BizTalk Server and [!INCLUDE[adapteroracle_short](../../includes/adapteroracle-short-md.md)].</span></span> <span data-ttu-id="a7b1f-107">您可以选择配置发送、 接收、 发送-接收或发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-107">You may choose to configure a send, receive, send-receive, or a receive-send port.</span></span> <span data-ttu-id="a7b1f-108">下表总结了你的选择。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="a7b1f-109">端口方向</span><span class="sxs-lookup"><span data-stu-id="a7b1f-109">Port direction</span></span>|<span data-ttu-id="a7b1f-110">通信模式</span><span class="sxs-lookup"><span data-stu-id="a7b1f-110">Communication pattern</span></span>|<span data-ttu-id="a7b1f-111">可供选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="a7b1f-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="a7b1f-112">Send</span><span class="sxs-lookup"><span data-stu-id="a7b1f-112">Send</span></span>|<span data-ttu-id="a7b1f-113">单向</span><span class="sxs-lookup"><span data-stu-id="a7b1f-113">One-way</span></span>|<span data-ttu-id="a7b1f-114">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="a7b1f-115">Receive</span><span class="sxs-lookup"><span data-stu-id="a7b1f-115">Receive</span></span>|<span data-ttu-id="a7b1f-116">单向</span><span class="sxs-lookup"><span data-stu-id="a7b1f-116">One-way</span></span>|<span data-ttu-id="a7b1f-117">始终在此端口上接收消息。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="a7b1f-118">发送接收</span><span class="sxs-lookup"><span data-stu-id="a7b1f-118">Send-receive</span></span>|<span data-ttu-id="a7b1f-119">请求-响应</span><span class="sxs-lookup"><span data-stu-id="a7b1f-119">Request-response</span></span>|<span data-ttu-id="a7b1f-120">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-120">I will be sending a request and receiving a response.</span></span>|  
  |<span data-ttu-id="a7b1f-121">接收发送</span><span class="sxs-lookup"><span data-stu-id="a7b1f-121">Receive-send</span></span>|<span data-ttu-id="a7b1f-122">要求响应</span><span class="sxs-lookup"><span data-stu-id="a7b1f-122">Solicit-response</span></span>|<span data-ttu-id="a7b1f-123">我将接收请求并发送响应。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-123">I will be receiving a request and sending a response.</span></span>|  
  
   <span data-ttu-id="a7b1f-124">有关详细信息，请参阅[创建一个发送端口](../../core/how-to-create-a-send-port2.md)，或[创建一个接收端口](../../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-124">For more information, see [Create a Send Port](../../core/how-to-create-a-send-port2.md), or [Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
- <span data-ttu-id="a7b1f-125">是否该适配器将消息发送到 Oracle 数据库或从 Oracle 数据库接收消息。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-125">Whether the adapter sends messages to the Oracle database or receives messages from the Oracle database.</span></span> <span data-ttu-id="a7b1f-126">具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-126">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="a7b1f-127">此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-127">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="a7b1f-128">有关使用此绑定文件配置端口的说明，请参阅[配置使用的 Oracle 数据库的端口绑定文件的物理端口绑定](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md)。</span><span class="sxs-lookup"><span data-stu-id="a7b1f-128">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to Oracle Database](../../adapters-and-accelerators/adapter-oracle-database/configure-a-physical-port-binding-using-a-port-binding-file-to-oracle-database.md).</span></span>  
  
 
  
## <a name="see-also"></a><span data-ttu-id="a7b1f-129">请参阅</span><span class="sxs-lookup"><span data-stu-id="a7b1f-129">See Also</span></span>  
[<span data-ttu-id="a7b1f-130">开发 BizTalk 应用程序</span><span class="sxs-lookup"><span data-stu-id="a7b1f-130">Develop your BizTalk applications</span></span>](../../core/develop-your-biztalk-applications.md)