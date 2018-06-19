---
title: 所需的未指定属性绑定类型 (R2) |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c8e45783-6454-44e2-867e-e30092725f51
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3a34de62453bd252e110edd0caf8a71996f25ae3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268805"
---
# <a name="required-property-binding-type-not-specified-r2"></a><span data-ttu-id="d65c5-102">未指定必需的属性绑定类型 (R2)</span><span class="sxs-lookup"><span data-stu-id="d65c5-102">Required property binding type not specified (R2)</span></span>
## <a name="details"></a><span data-ttu-id="d65c5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d65c5-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d65c5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d65c5-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d65c5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d65c5-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d65c5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d65c5-106">Event ID</span></span>|<span data-ttu-id="d65c5-107">0</span><span class="sxs-lookup"><span data-stu-id="d65c5-107">0</span></span>|  
|<span data-ttu-id="d65c5-108">事件源</span><span class="sxs-lookup"><span data-stu-id="d65c5-108">Event Source</span></span>|<span data-ttu-id="d65c5-109">0</span><span class="sxs-lookup"><span data-stu-id="d65c5-109">0</span></span>|  
|<span data-ttu-id="d65c5-110">组件</span><span class="sxs-lookup"><span data-stu-id="d65c5-110">Component</span></span>|<span data-ttu-id="d65c5-111">0</span><span class="sxs-lookup"><span data-stu-id="d65c5-111">0</span></span>|  
|<span data-ttu-id="d65c5-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="d65c5-112">Symbolic Name</span></span>|<span data-ttu-id="d65c5-113">0</span><span class="sxs-lookup"><span data-stu-id="d65c5-113">0</span></span>|  
|<span data-ttu-id="d65c5-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="d65c5-114">Message Text</span></span>|<span data-ttu-id="d65c5-115">未指定所需的属性绑定类型</span><span class="sxs-lookup"><span data-stu-id="d65c5-115">Required property Binding Type not specified</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d65c5-116">解释</span><span class="sxs-lookup"><span data-stu-id="d65c5-116">Explanation</span></span>  
 <span data-ttu-id="d65c5-117">配置 WCF-Custom 或 WCF-CustomIsolated 传输时，未设置“绑定类型”属性。</span><span class="sxs-lookup"><span data-stu-id="d65c5-117">You did not set the Binding Type property when configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d65c5-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="d65c5-118">User Action</span></span>  
 <span data-ttu-id="d65c5-119">使用以下过程配置绑定类型属性。</span><span class="sxs-lookup"><span data-stu-id="d65c5-119">Use the following procedure to configure the binding type property.</span></span>  
  
#### <a name="to-configure-the-binding-type-property"></a><span data-ttu-id="d65c5-120">配置绑定类型属性的步骤</span><span class="sxs-lookup"><span data-stu-id="d65c5-120">To configure the binding type property</span></span>  
  
1.  <span data-ttu-id="d65c5-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d65c5-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d65c5-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d65c5-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="d65c5-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="d65c5-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="d65c5-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="d65c5-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="d65c5-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="d65c5-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="d65c5-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="d65c5-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="d65c5-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d65c5-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="d65c5-128">在**WCF-[***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d65c5-128">In the **WCF--[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="d65c5-129">中指定一个值**绑定类型**列表。</span><span class="sxs-lookup"><span data-stu-id="d65c5-129">Specify a value in the **Binding Type** list.</span></span>  
  
 <span data-ttu-id="d65c5-130">有关配置绑定的详细信息，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="d65c5-130">For additional information on configuring binding, see the following resources:</span></span>  
  
-   [<span data-ttu-id="d65c5-131">如何配置 WCF CustomIsolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="d65c5-131">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="d65c5-132">如何配置 WCF 自定义接收位置</span><span class="sxs-lookup"><span data-stu-id="d65c5-132">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="d65c5-133">如何配置 WCF 自定义发送端口</span><span class="sxs-lookup"><span data-stu-id="d65c5-133">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)