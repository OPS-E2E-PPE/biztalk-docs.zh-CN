---
title: 步骤 3：配置单向 FILE 发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c52c6b6b-6f9c-48f2-8732-450fe3a15eae
caps.latest.revision: 4
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6ab2d37ba632b837e9ca13839cd5a1b8993f69bd
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65392667"
---
# <a name="step-3-configure-a-one-way-file-send-port"></a><span data-ttu-id="924c6-102">步骤 3：配置单向 FILE 发送端口</span><span class="sxs-lookup"><span data-stu-id="924c6-102">Step 3: Configure a One-way FILE Send Port</span></span>
<span data-ttu-id="924c6-103">在此步骤中配置一个单向 FILE 发送端口使用从 REST 接口接收的响应消息并将其复制到某个文件位置。</span><span class="sxs-lookup"><span data-stu-id="924c6-103">In this step you configure a one-way FILE send port that consumes the response message received from the REST interface and copies it to a file location.</span></span>  

### <a name="to-configure-a-file-send-port"></a><span data-ttu-id="924c6-104">若要配置 FILE 发送端口</span><span class="sxs-lookup"><span data-stu-id="924c6-104">To configure a FILE send port</span></span>  

1. <span data-ttu-id="924c6-105">从 BizTalk Server 管理控制台中下, **BizTalk Application 1**节点，右键单击**发送端口**，指向**新建**，然后单击**静态单向发送端口**。</span><span class="sxs-lookup"><span data-stu-id="924c6-105">From BizTalk Server Administration Console, under the **BizTalk Application 1** node, right-click **Send Ports**, point to **New**, and then click **Static One-way Send Port**.</span></span>  

2. <span data-ttu-id="924c6-106">在常规选项卡上，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="924c6-106">On the General tab, do the following:</span></span>  

   |<span data-ttu-id="924c6-107">使用此选项</span><span class="sxs-lookup"><span data-stu-id="924c6-107">Use this</span></span>|<span data-ttu-id="924c6-108">执行的操作</span><span class="sxs-lookup"><span data-stu-id="924c6-108">To do this</span></span>|  
   |--------------|----------------|  
   |<span data-ttu-id="924c6-109">**名称**</span><span class="sxs-lookup"><span data-stu-id="924c6-109">**Name**</span></span>|<span data-ttu-id="924c6-110">类型**SendPortOutAzureMarketPlaceData**。</span><span class="sxs-lookup"><span data-stu-id="924c6-110">Type **SendPortOutAzureMarketPlaceData**.</span></span>|  
   |<span data-ttu-id="924c6-111">**类型**</span><span class="sxs-lookup"><span data-stu-id="924c6-111">**Type**</span></span>|<span data-ttu-id="924c6-112">选择**文件**。</span><span class="sxs-lookup"><span data-stu-id="924c6-112">Select **FILE**.</span></span>|  
   |<span data-ttu-id="924c6-113">**发送处理程序**</span><span class="sxs-lookup"><span data-stu-id="924c6-113">**Send handler**</span></span>|<span data-ttu-id="924c6-114">选择“BizTalkServerApplication” 。</span><span class="sxs-lookup"><span data-stu-id="924c6-114">Select **BizTalkServerApplication**.</span></span>|  
   |<span data-ttu-id="924c6-115">**发送管道**</span><span class="sxs-lookup"><span data-stu-id="924c6-115">**Send pipeline**</span></span>|<span data-ttu-id="924c6-116">选择**PassThruTransmit**。</span><span class="sxs-lookup"><span data-stu-id="924c6-116">Select **PassThruTransmit**.</span></span>|  

    <span data-ttu-id="924c6-117">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="924c6-117">Click **Configure**.</span></span>  

3. <span data-ttu-id="924c6-118">从文件传输属性中，执行以下步骤：</span><span class="sxs-lookup"><span data-stu-id="924c6-118">From File Transport Properties, do the following:</span></span>  


   |      <span data-ttu-id="924c6-119">使用此选项</span><span class="sxs-lookup"><span data-stu-id="924c6-119">Use this</span></span>      |                                                              <span data-ttu-id="924c6-120">执行的操作</span><span class="sxs-lookup"><span data-stu-id="924c6-120">To do this</span></span>                                                               |
   |--------------------|---------------------------------------------------------------------------------------------------------------------------------------|
   | <span data-ttu-id="924c6-121">**接收文件夹**</span><span class="sxs-lookup"><span data-stu-id="924c6-121">**Receive folder**</span></span> | <span data-ttu-id="924c6-122">键入某一位置其中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]将复制的响应消息。</span><span class="sxs-lookup"><span data-stu-id="924c6-122">Type a location where [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] copies the response message.</span></span> |
   |   <span data-ttu-id="924c6-123">**文件名**</span><span class="sxs-lookup"><span data-stu-id="924c6-123">**File name**</span></span>    |                                                       <span data-ttu-id="924c6-124">保留 `%MessageID%.xml`</span><span class="sxs-lookup"><span data-stu-id="924c6-124">Retain `%MessageID%.xml`</span></span>                                                        |


4. <span data-ttu-id="924c6-125">上**筛选器**选项卡上，指定要使用写入到的所有消息的筛选器[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Messagebox 数据库中创建的接收端口通过[步骤 2:配置双向 Wcf-webhttp 发送端口](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md)。</span><span class="sxs-lookup"><span data-stu-id="924c6-125">On the **Filters** tab, specify the filter to consume all messages that are written to the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Message Box database by the receive port you created in [Step 2: Configure a Two-way WCF-WebHttp Send Port](../core/step-2-configure-a-two-way-wcf-webhttp-send-port.md).</span></span>  


   |              |                                       |
   |--------------|---------------------------------------|
   | <span data-ttu-id="924c6-126">**属性**</span><span class="sxs-lookup"><span data-stu-id="924c6-126">**Property**</span></span> |         <span data-ttu-id="924c6-127">设置为**BTS。SPName**</span><span class="sxs-lookup"><span data-stu-id="924c6-127">Set to **BTS.SPName**</span></span>         |
   | <span data-ttu-id="924c6-128">**“运算符”**</span><span class="sxs-lookup"><span data-stu-id="924c6-128">**Operator**</span></span> |             <span data-ttu-id="924c6-129">设置为 **==**</span><span class="sxs-lookup"><span data-stu-id="924c6-129">Set to **==**</span></span>             |
   |  <span data-ttu-id="924c6-130">**ReplTest1**</span><span class="sxs-lookup"><span data-stu-id="924c6-130">**Value**</span></span>   | <span data-ttu-id="924c6-131">设置为 `SendPortRESTAzureMarketPlace`</span><span class="sxs-lookup"><span data-stu-id="924c6-131">Set to `SendPortRESTAzureMarketPlace`</span></span> |


5. <span data-ttu-id="924c6-132">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="924c6-132">Click **OK**.</span></span>  

## <a name="see-also"></a><span data-ttu-id="924c6-133">请参阅</span><span class="sxs-lookup"><span data-stu-id="924c6-133">See Also</span></span>  
 [<span data-ttu-id="924c6-134">教程 5:调用 REST 接口使用 BizTalk Server</span><span class="sxs-lookup"><span data-stu-id="924c6-134">Tutorial 5: Invoking a REST Interface Using BizTalk Server</span></span>](../core/tutorial-5-invoking-a-rest-interface-using-biztalk-server.md)