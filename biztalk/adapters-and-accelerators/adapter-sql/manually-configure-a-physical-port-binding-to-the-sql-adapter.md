---
title: 手动配置与 SQL 适配器的物理端口绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: d3f0bb78-c85f-4629-9e2d-cce180ff78ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0fccfcfed0e965831d0c40ccde94348440db357e
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65368790"
---
# <a name="manually-configure-a-physical-port-binding-to-the-sql-adapter"></a><span data-ttu-id="05e5b-102">手动配置与 SQL 适配器的物理端口绑定</span><span class="sxs-lookup"><span data-stu-id="05e5b-102">Manually configure a physical port binding to the SQL adapter</span></span>
<span data-ttu-id="05e5b-103">本部分提供有关配置信息[!INCLUDE[adaptersql](../../includes/adaptersql-md.md)]作为 WCF 自定义绑定或通过使用 WCF SQL 端口[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="05e5b-103">This section provides information about configuring the [!INCLUDE[adaptersql](../../includes/adaptersql-md.md)] as a WCF custom binding or as a WCF-SQL port by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="05e5b-104">在部署后，适配器，您将能够发送和接收消息从 SQL Server 使用[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="05e5b-104">After deploying the adapter, you will be able to send and receive messages from SQL Server by using the [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="05e5b-105">部署该适配器的步骤会有所不同，具体取决于：</span><span class="sxs-lookup"><span data-stu-id="05e5b-105">The steps for deploying the adapter vary depending on:</span></span>  
  
- <span data-ttu-id="05e5b-106">之间的通信方向[!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)]和[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05e5b-106">The direction of communication between [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] and the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span> <span data-ttu-id="05e5b-107">您可以选择配置发送、 接收或发送接收端口。</span><span class="sxs-lookup"><span data-stu-id="05e5b-107">You may choose to configure a send, receive, or a send-receive port.</span></span> <span data-ttu-id="05e5b-108">下表总结了你的选择。</span><span class="sxs-lookup"><span data-stu-id="05e5b-108">Your choices are summarized in the following table.</span></span>  
  
  |<span data-ttu-id="05e5b-109">端口方向</span><span class="sxs-lookup"><span data-stu-id="05e5b-109">Port direction</span></span>|<span data-ttu-id="05e5b-110">通信模式</span><span class="sxs-lookup"><span data-stu-id="05e5b-110">Communication pattern</span></span>|<span data-ttu-id="05e5b-111">可供选择的通信方向</span><span class="sxs-lookup"><span data-stu-id="05e5b-111">Direction of communication to choose from</span></span>|  
  |--------------------|---------------------------|-----------------------------------------------|  
  |<span data-ttu-id="05e5b-112">Send</span><span class="sxs-lookup"><span data-stu-id="05e5b-112">Send</span></span>|<span data-ttu-id="05e5b-113">单向</span><span class="sxs-lookup"><span data-stu-id="05e5b-113">One-way</span></span>|<span data-ttu-id="05e5b-114">我将始终在发送消息此端口上。</span><span class="sxs-lookup"><span data-stu-id="05e5b-114">I will always be sending messages on this port.</span></span>|  
  |<span data-ttu-id="05e5b-115">Receive</span><span class="sxs-lookup"><span data-stu-id="05e5b-115">Receive</span></span>|<span data-ttu-id="05e5b-116">单向</span><span class="sxs-lookup"><span data-stu-id="05e5b-116">One-way</span></span>|<span data-ttu-id="05e5b-117">我始终将接收此端口上的消息。</span><span class="sxs-lookup"><span data-stu-id="05e5b-117">I will always be receiving messages on this port.</span></span>|  
  |<span data-ttu-id="05e5b-118">发送接收</span><span class="sxs-lookup"><span data-stu-id="05e5b-118">Send-receive</span></span>|<span data-ttu-id="05e5b-119">请求-响应</span><span class="sxs-lookup"><span data-stu-id="05e5b-119">Request-response</span></span>|<span data-ttu-id="05e5b-120">我将发送请求并接收响应。</span><span class="sxs-lookup"><span data-stu-id="05e5b-120">I will be sending a request and receiving a response.</span></span>|  
  
  > [!NOTE]
  >  <span data-ttu-id="05e5b-121">双向接收端口不受[!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="05e5b-121">Two-way receive ports are not supported by the [!INCLUDE[adaptersqlshort](../../includes/adaptersqlshort-md.md)].</span></span>  
  
   <span data-ttu-id="05e5b-122">有关详细信息，请参阅[如何创建发送端口](../../core/how-to-create-a-send-port2.md)，或[如何创建接收端口](../../core/how-to-create-a-receive-port.md)。</span><span class="sxs-lookup"><span data-stu-id="05e5b-122">For more information, see [How to Create a Send Port](../../core/how-to-create-a-send-port2.md), or [How to Create a Receive Port](../../core/how-to-create-a-receive-port.md).</span></span> 
  
- <span data-ttu-id="05e5b-123">是否该适配器将消息发送到 SQL Server （出站操作），或从 SQL Server （入站操作） 接收消息。</span><span class="sxs-lookup"><span data-stu-id="05e5b-123">Whether the adapter sends messages to the SQL Server (outbound operations) or receives messages from SQL Server (inbound operations).</span></span> <span data-ttu-id="05e5b-124">具体取决于是否想要发送或接收消息，将创建一个发送或接收端口，分别。</span><span class="sxs-lookup"><span data-stu-id="05e5b-124">Depending on whether you want to send or receive messages, you will create a send or receive port, respectively.</span></span>  
  
  > [!NOTE]
  >  <span data-ttu-id="05e5b-125">此外可以配置发送或接收端口通过导入创建的绑定配置文件[!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)]作为元数据生成的一部分。</span><span class="sxs-lookup"><span data-stu-id="05e5b-125">You can also configure the send or receive ports by importing a binding configuration file that is created by the [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] as part of metadata generation.</span></span> <span data-ttu-id="05e5b-126">有关使用此绑定文件配置端口的说明，请参阅[配置使用的端口绑定文件以使用 SQL 适配器的物理端口绑定](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md)。</span><span class="sxs-lookup"><span data-stu-id="05e5b-126">For instructions on configuring ports using this binding file, see [Configure a physical port binding using a port binding file to use the SQL adapter](../../adapters-and-accelerators/adapter-sql/configure-a-physical-port-binding-using-a-port-binding-file-to-sql-adapter.md).</span></span>
  
## <a name="in-this-section"></a><span data-ttu-id="05e5b-127">本节内容</span><span class="sxs-lookup"><span data-stu-id="05e5b-127">In This Section</span></span>  
  
-   [<span data-ttu-id="05e5b-128">使用 WCF 自定义适配器和 SQL 适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="05e5b-128">Configure a port using the WCF-custom adapter and SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-custom-adapter-and-sql-adapter.md)  
  
-   [<span data-ttu-id="05e5b-129">使用 WCF-SQL 适配器配置端口</span><span class="sxs-lookup"><span data-stu-id="05e5b-129">Configure a port using the WCF-SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/configure-a-port-using-the-wcf-sql-adapter.md)  
  
## <a name="see-also"></a><span data-ttu-id="05e5b-130">请参阅</span><span class="sxs-lookup"><span data-stu-id="05e5b-130">See Also</span></span>  
[<span data-ttu-id="05e5b-131">若要开发使用 SQL 适配器的 BizTalk 应用程序的构建基块</span><span class="sxs-lookup"><span data-stu-id="05e5b-131">Building blocks to develop BizTalk applications with the SQL adapter</span></span>](../../adapters-and-accelerators/adapter-sql/building-blocks-to-develop-biztalk-applications-with-the-sql-adapter.md)