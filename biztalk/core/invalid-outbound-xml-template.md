---
title: "无效的出站 XML 模板 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0f29bb60-8c04-4921-84bf-c629540a1c83
caps.latest.revision: "13"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f58d230b481e611879637ff1b6ae08c2eed0313f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="invalid-outbound-xml-template"></a><span data-ttu-id="62833-102">出站 XML 模板无效</span><span class="sxs-lookup"><span data-stu-id="62833-102">Invalid outbound XML template</span></span>
## <a name="details"></a><span data-ttu-id="62833-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="62833-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="62833-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="62833-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="62833-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="62833-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="62833-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="62833-106">Event ID</span></span>|<span data-ttu-id="62833-107">0</span><span class="sxs-lookup"><span data-stu-id="62833-107">0</span></span>|  
|<span data-ttu-id="62833-108">事件源</span><span class="sxs-lookup"><span data-stu-id="62833-108">Event Source</span></span>|<span data-ttu-id="62833-109">0</span><span class="sxs-lookup"><span data-stu-id="62833-109">0</span></span>|  
|<span data-ttu-id="62833-110">组件</span><span class="sxs-lookup"><span data-stu-id="62833-110">Component</span></span>|<span data-ttu-id="62833-111">0</span><span class="sxs-lookup"><span data-stu-id="62833-111">0</span></span>|  
|<span data-ttu-id="62833-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="62833-112">Symbolic Name</span></span>|<span data-ttu-id="62833-113">0</span><span class="sxs-lookup"><span data-stu-id="62833-113">0</span></span>|  
|<span data-ttu-id="62833-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="62833-114">Message Text</span></span>|<span data-ttu-id="62833-115">出站 XML 模板无效</span><span class="sxs-lookup"><span data-stu-id="62833-115">Invalid outbound XML template</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="62833-116">解释</span><span class="sxs-lookup"><span data-stu-id="62833-116">Explanation</span></span>  
 <span data-ttu-id="62833-117">可能存在多个原因。</span><span class="sxs-lookup"><span data-stu-id="62833-117">There could be multiple reasons.</span></span> <span data-ttu-id="62833-118">出站 WCF 消息正文模板可能不是有效的 XML。</span><span class="sxs-lookup"><span data-stu-id="62833-118">The outbound WCF message body template may not be valid XML.</span></span> <span data-ttu-id="62833-119">给定的编码中可能包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="62833-119">It may contain invalid characters in the given encoding.</span></span> <span data-ttu-id="62833-120">根元素可能丢失。</span><span class="sxs-lookup"><span data-stu-id="62833-120">The root element may be missing.</span></span> <span data-ttu-id="62833-121">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="62833-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="62833-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="62833-122">User Action</span></span>  
 <span data-ttu-id="62833-123">确保模板表达式具有有效的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="62833-123">Ensure that template expression has valid XML code.</span></span> <span data-ttu-id="62833-124">确保其中不包含任何无效字符，并且只有一个根元素。</span><span class="sxs-lookup"><span data-stu-id="62833-124">Ensure that It doesn’t contain any invalid characters and that there is only one root element.</span></span>  
  
1.  <span data-ttu-id="62833-125">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="62833-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="62833-126">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="62833-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="62833-127">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="62833-127">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="62833-128">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="62833-128">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="62833-129">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="62833-129">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="62833-130">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="62833-130">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="62833-131">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="62833-131">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="62833-132">在**WCF [***传输类型***] 传输属性**对话框中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="62833-132">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="62833-133">在**出站 WCF 消息正文**部分中，选择**模板--由模板指定内容**。</span><span class="sxs-lookup"><span data-stu-id="62833-133">In the **Outbound WCF message body** section, select **Template--content specified by template**.</span></span>  
  
10. <span data-ttu-id="62833-134">在**XML**文本框中，确保有效的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="62833-134">In the **XML** text box, ensure that the XML code is valid.</span></span>  
  
 <span data-ttu-id="62833-135">有关模板的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="62833-135">For additional information on templates, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="62833-136">为 WCF 适配器指定消息正文</span><span class="sxs-lookup"><span data-stu-id="62833-136">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)