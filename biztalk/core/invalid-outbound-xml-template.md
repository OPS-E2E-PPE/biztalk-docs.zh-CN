---
title: 出站 XML 模板无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0f29bb60-8c04-4921-84bf-c629540a1c83
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1b0978c88e1392c506970b11bac9774c1f48eb5a
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65330769"
---
# <a name="invalid-outbound-xml-template"></a><span data-ttu-id="66905-102">出站 XML 模板无效</span><span class="sxs-lookup"><span data-stu-id="66905-102">Invalid outbound XML template</span></span>
## <a name="details"></a><span data-ttu-id="66905-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="66905-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="66905-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="66905-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="66905-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="66905-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="66905-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="66905-106">Event ID</span></span>     |                                         <span data-ttu-id="66905-107">0</span><span class="sxs-lookup"><span data-stu-id="66905-107">0</span></span>                                          |
|  <span data-ttu-id="66905-108">事件源</span><span class="sxs-lookup"><span data-stu-id="66905-108">Event Source</span></span>   |                                         <span data-ttu-id="66905-109">0</span><span class="sxs-lookup"><span data-stu-id="66905-109">0</span></span>                                          |
|    <span data-ttu-id="66905-110">组件</span><span class="sxs-lookup"><span data-stu-id="66905-110">Component</span></span>    |                                         <span data-ttu-id="66905-111">0</span><span class="sxs-lookup"><span data-stu-id="66905-111">0</span></span>                                          |
|  <span data-ttu-id="66905-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="66905-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="66905-113">0</span><span class="sxs-lookup"><span data-stu-id="66905-113">0</span></span>                                          |
|  <span data-ttu-id="66905-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="66905-114">Message Text</span></span>   |                           <span data-ttu-id="66905-115">出站 XML 模板无效</span><span class="sxs-lookup"><span data-stu-id="66905-115">Invalid outbound XML template</span></span>                            |
  
## <a name="explanation"></a><span data-ttu-id="66905-116">解释</span><span class="sxs-lookup"><span data-stu-id="66905-116">Explanation</span></span>  
 <span data-ttu-id="66905-117">可能有多个原因。</span><span class="sxs-lookup"><span data-stu-id="66905-117">There could be multiple reasons.</span></span> <span data-ttu-id="66905-118">出站 WCF 消息正文模板可能不是有效的 XML。</span><span class="sxs-lookup"><span data-stu-id="66905-118">The outbound WCF message body template may not be valid XML.</span></span> <span data-ttu-id="66905-119">它可能包含给定编码中的无效字符。</span><span class="sxs-lookup"><span data-stu-id="66905-119">It may contain invalid characters in the given encoding.</span></span> <span data-ttu-id="66905-120">可能缺少根元素。</span><span class="sxs-lookup"><span data-stu-id="66905-120">The root element may be missing.</span></span> <span data-ttu-id="66905-121">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="66905-121">The data at the root level may be invalid.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="66905-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="66905-122">User Action</span></span>  
 <span data-ttu-id="66905-123">请确保模板表达式具有有效的 XML 代码。</span><span class="sxs-lookup"><span data-stu-id="66905-123">Ensure that template expression has valid XML code.</span></span> <span data-ttu-id="66905-124">请确保它不包含任何无效字符，并且没有只有一个根元素。</span><span class="sxs-lookup"><span data-stu-id="66905-124">Ensure that It doesn’t contain any invalid characters and that there is only one root element.</span></span>  
  
1. <span data-ttu-id="66905-125">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="66905-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="66905-126">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="66905-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="66905-127">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="66905-127">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="66905-128">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="66905-128">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="66905-129">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="66905-129">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="66905-130">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="66905-130">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="66905-131">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="66905-131">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="66905-132">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="66905-132">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Messages** tab.</span></span>  
  
9. <span data-ttu-id="66905-133">在中**出站 WCF 消息正文**部分中，选择**模板-由模板指定的内容**。</span><span class="sxs-lookup"><span data-stu-id="66905-133">In the **Outbound WCF message body** section, select **Template--content specified by template**.</span></span>  
  
10. <span data-ttu-id="66905-134">在中**XML**文字框中，确保 XML 代码有效。</span><span class="sxs-lookup"><span data-stu-id="66905-134">In the **XML** text box, ensure that the XML code is valid.</span></span>  
  
    <span data-ttu-id="66905-135">有关模板的其他信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="66905-135">For additional information on templates, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="66905-136">指定 WCF 适配器的消息正文</span><span class="sxs-lookup"><span data-stu-id="66905-136">Specifying the Message Body for the WCF Adapters</span></span>](../core/specifying-the-message-body-for-the-wcf-adapters.md)