---
title: 无法从 XML 配置创建终结点行为配置元素 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 89d906a4-ea85-42d8-8e9e-0a3a7774bcd8
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b2b294b67f066c0c3ff61232afd1aa81382363c1
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292838"
---
# <a name="unable-to-create-endpoint-behavior-configuration-element-from-xml-configuration"></a><span data-ttu-id="5b668-102">无法从 XML 配置创建终结点行为配置元素</span><span class="sxs-lookup"><span data-stu-id="5b668-102">Unable to create endpoint behavior configuration element from XML configuration</span></span>
## <a name="details"></a><span data-ttu-id="5b668-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5b668-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="5b668-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5b668-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="5b668-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5b668-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="5b668-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5b668-106">Event ID</span></span>     |                                         <span data-ttu-id="5b668-107">0</span><span class="sxs-lookup"><span data-stu-id="5b668-107">0</span></span>                                          |
|  <span data-ttu-id="5b668-108">事件源</span><span class="sxs-lookup"><span data-stu-id="5b668-108">Event Source</span></span>   |                                         <span data-ttu-id="5b668-109">0</span><span class="sxs-lookup"><span data-stu-id="5b668-109">0</span></span>                                          |
|    <span data-ttu-id="5b668-110">组件</span><span class="sxs-lookup"><span data-stu-id="5b668-110">Component</span></span>    |                                         <span data-ttu-id="5b668-111">0</span><span class="sxs-lookup"><span data-stu-id="5b668-111">0</span></span>                                          |
|  <span data-ttu-id="5b668-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="5b668-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="5b668-113">0</span><span class="sxs-lookup"><span data-stu-id="5b668-113">0</span></span>                                          |
|  <span data-ttu-id="5b668-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="5b668-114">Message Text</span></span>   |  <span data-ttu-id="5b668-115">无法从 XML 配置创建终结点行为配置元素</span><span class="sxs-lookup"><span data-stu-id="5b668-115">Unable to create endpoint behavior configuration element from XML configuration</span></span>   |

## <a name="explanation"></a><span data-ttu-id="5b668-116">解释</span><span class="sxs-lookup"><span data-stu-id="5b668-116">Explanation</span></span>  
 <span data-ttu-id="5b668-117">此错误表示适配器未加载终结点行为配置。</span><span class="sxs-lookup"><span data-stu-id="5b668-117">This error indicates the adapter did not load the endpoint behavior configuration.</span></span> <span data-ttu-id="5b668-118">主要与 Wcf-custom 和 Wcf-customisolated 适配器出现这种情况。</span><span class="sxs-lookup"><span data-stu-id="5b668-118">This situation occurs primarily with the WCF-Custom and WCF-CustomIsolated adapters.</span></span>  

## <a name="user-action"></a><span data-ttu-id="5b668-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="5b668-119">User Action</span></span>  
 <span data-ttu-id="5b668-120">使用以下过程配置终结点行为。</span><span class="sxs-lookup"><span data-stu-id="5b668-120">Use the following procedure to configure the endpoint behavior.</span></span>  

#### <a name="to-configure-the-endpoint-behavior"></a><span data-ttu-id="5b668-121">若要配置的终结点行为</span><span class="sxs-lookup"><span data-stu-id="5b668-121">To configure the endpoint behavior</span></span>  

1. <span data-ttu-id="5b668-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5b668-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="5b668-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5b668-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="5b668-124">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="5b668-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="5b668-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="5b668-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="5b668-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="5b668-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="5b668-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="5b668-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="5b668-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5b668-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="5b668-129">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**行为**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5b668-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Behavior** tab.</span></span>  

9. <span data-ttu-id="5b668-130">在中**行为**部分中，选择**EndpointBehavior**配置。</span><span class="sxs-lookup"><span data-stu-id="5b668-130">In the **Behavior** section, check the **EndpointBehavior** configuration.</span></span>
