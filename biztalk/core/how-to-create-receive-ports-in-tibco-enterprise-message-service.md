---
title: "如何创建在 TIBCO 企业消息服务接收端口 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- receive ports, creating
- creating receive ports
ms.assetid: ca623c81-3dd3-4824-a586-28055d01fe9f
caps.latest.revision: "7"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a85fad9dc0936baa0c3f584581d5483a30fedf6f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-receive-ports-in-tibco-enterprise-message-service"></a><span data-ttu-id="d45ae-102">如何创建 在 TIBCO Enterprise Message Service 中创建接收端口</span><span class="sxs-lookup"><span data-stu-id="d45ae-102">How to Create Receive Ports in TIBCO Enterprise Message Service</span></span>
<span data-ttu-id="d45ae-103">请遵循以下步骤创建一个接收端口。</span><span class="sxs-lookup"><span data-stu-id="d45ae-103">Follow these steps to create a receive port.</span></span>  
  
### <a name="to-create-a-receive-port"></a><span data-ttu-id="d45ae-104">若要创建接收端口</span><span class="sxs-lookup"><span data-stu-id="d45ae-104">To create a receive port</span></span>  
  
1.  <span data-ttu-id="d45ae-105">在 BizTalk Server 管理控制台中，展开**BizTalk Server 管理**，展开**BizTalk 组**，展开**应用程序**，然后展开所需应用程序。</span><span class="sxs-lookup"><span data-stu-id="d45ae-105">In the BizTalk Server Administration Console, expand **BizTalk Server Administration**, expand **BizTalk Group**, expand **Applications**, and then expand the desired application.</span></span>  
  
2.  <span data-ttu-id="d45ae-106">右键单击**接收端口**，指向**新建**，然后单击**单向接收端口**。</span><span class="sxs-lookup"><span data-stu-id="d45ae-106">Right-click **Receive Ports**, point to **New**, and then click **One-way Receive Ports**.</span></span>  
  
3.  <span data-ttu-id="d45ae-107">在**接收端口属性**窗口，请在**常规**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d45ae-107">In the **Receive Port Properties** window, on the **General** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="d45ae-108">在**名称**字段中，键入`ReceiveFromTIBCOEMS`。</span><span class="sxs-lookup"><span data-stu-id="d45ae-108">In the **Name** field, type `ReceiveFromTIBCOEMS`.</span></span>  
  
    2.  <span data-ttu-id="d45ae-109">在**身份验证**组框中，指定使用身份验证时处理消息的方式。</span><span class="sxs-lookup"><span data-stu-id="d45ae-109">In the **Authentication** group box, specify how messages are handled when using authentication.</span></span>  
  
    3.  <span data-ttu-id="d45ae-110">选择**启用路由失败消息**复选框。</span><span class="sxs-lookup"><span data-stu-id="d45ae-110">Select the **Enable routing for failed messages** checkbox.</span></span>  
  
4.  <span data-ttu-id="d45ae-111">上**接收位置**页上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="d45ae-111">On the **Receive Locations** page, do the following:</span></span>  
  
    1.  <span data-ttu-id="d45ae-112">单击 **“新建”**。</span><span class="sxs-lookup"><span data-stu-id="d45ae-112">Click **New**.</span></span>  
  
    2.  <span data-ttu-id="d45ae-113">在**接收位置**窗口，请在**常规**页上，键入**名称**的接收位置。</span><span class="sxs-lookup"><span data-stu-id="d45ae-113">In the **Receive Locations** window, on the **General** page, type the **Name** of the receive location.</span></span>  
  
    3.  <span data-ttu-id="d45ae-114">从**类型**下拉列表中，选择传输类型，并从**接收处理程序**下拉列表中，选择的传输地址。</span><span class="sxs-lookup"><span data-stu-id="d45ae-114">From the **Type** drop-down list, select the transport type, and from the **Receive handler** drop-down list, select the transport address.</span></span>  
  
    4.  <span data-ttu-id="d45ae-115">从**接收管道**下拉列表中，选择接收管道。</span><span class="sxs-lookup"><span data-stu-id="d45ae-115">From the **Receive pipeline** drop-down list, select the receive pipeline.</span></span>  
  
    5.  <span data-ttu-id="d45ae-116">上**计划**页上，选择**开始日期**和**结束日期**限制接收的文档。</span><span class="sxs-lookup"><span data-stu-id="d45ae-116">On the **Schedule** page, select the **Start date** and the **End date** to restrict receiving documents.</span></span>  
  
    6.  <span data-ttu-id="d45ae-117">选择**启用服务窗口**复选框。</span><span class="sxs-lookup"><span data-stu-id="d45ae-117">Select the **Enable service window** checkbox.</span></span>  
  
    7.  <span data-ttu-id="d45ae-118">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d45ae-118">Click **OK**.</span></span>  
  
5.  <span data-ttu-id="d45ae-119">上**入站映射**页上，选择转换所选的端口上的文档的入站的映射。</span><span class="sxs-lookup"><span data-stu-id="d45ae-119">On the **Inbound Maps** page, select the inbound maps for transforming documents on the selected port.</span></span>  
  
6.  <span data-ttu-id="d45ae-120">上**跟踪**页上，选择所需的跟踪消息正文和跟踪消息属性。</span><span class="sxs-lookup"><span data-stu-id="d45ae-120">On the **Tracking** page, select the desired tracking message bodies and tracking message properties.</span></span>  
  
7.  <span data-ttu-id="d45ae-121">单击 **“确定”**。</span><span class="sxs-lookup"><span data-stu-id="d45ae-121">Click **OK**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d45ae-122">另请参阅</span><span class="sxs-lookup"><span data-stu-id="d45ae-122">See Also</span></span>  
 [<span data-ttu-id="d45ae-123">设置 TIBCO 企业消息服务传输属性接收端口</span><span class="sxs-lookup"><span data-stu-id="d45ae-123">Setting TIBCO Enterprise Message Service Transport Properties for the Receive Port</span></span>](../core/set-tibco-enterprise-message-service-transport-properties-for-the-receive-port.md)