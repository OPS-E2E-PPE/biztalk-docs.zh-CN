---
title: 无法创建绑定 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: fbe1bd54-6031-4f90-a445-c1647b382a1a
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 567b3d88ced85f427fde492cd3e68cefaaf47394
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36999200"
---
# <a name="cannot-create-binding"></a><span data-ttu-id="79da6-102">无法创建绑定</span><span class="sxs-lookup"><span data-stu-id="79da6-102">Cannot create binding</span></span>
## <a name="details"></a><span data-ttu-id="79da6-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="79da6-103">Details</span></span>  
  
|                 |                                                                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="79da6-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="79da6-104">Product Name</span></span>   |                               [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]                               |
| <span data-ttu-id="79da6-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="79da6-105">Product Version</span></span> |                                           [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                                           |
|    <span data-ttu-id="79da6-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="79da6-106">Event ID</span></span>     |                                                                       <span data-ttu-id="79da6-107">0</span><span class="sxs-lookup"><span data-stu-id="79da6-107">0</span></span>                                                                        |
|  <span data-ttu-id="79da6-108">事件源</span><span class="sxs-lookup"><span data-stu-id="79da6-108">Event Source</span></span>   |                                                                       <span data-ttu-id="79da6-109">0</span><span class="sxs-lookup"><span data-stu-id="79da6-109">0</span></span>                                                                        |
|    <span data-ttu-id="79da6-110">组件</span><span class="sxs-lookup"><span data-stu-id="79da6-110">Component</span></span>    |                                                                       <span data-ttu-id="79da6-111">0</span><span class="sxs-lookup"><span data-stu-id="79da6-111">0</span></span>                                                                        |
|  <span data-ttu-id="79da6-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="79da6-112">Symbolic Name</span></span>  |                                                                       <span data-ttu-id="79da6-113">0</span><span class="sxs-lookup"><span data-stu-id="79da6-113">0</span></span>                                                                        |
|  <span data-ttu-id="79da6-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="79da6-114">Message Text</span></span>   | <span data-ttu-id="79da6-115">由于未指定绑定类型，因此无法创建绑定。</span><span class="sxs-lookup"><span data-stu-id="79da6-115">Cannot create binding since binding type was not specified.</span></span> <span data-ttu-id="79da6-116">指定绑定类型，例如“basicHttpBinding”、“wsHttpBinding”或“customBinding”</span><span class="sxs-lookup"><span data-stu-id="79da6-116">Specify a binding type like "basicHttpBinding", "wsHttpBinding", or "customBinding</span></span> |
  
## <a name="explanation"></a><span data-ttu-id="79da6-117">解释</span><span class="sxs-lookup"><span data-stu-id="79da6-117">Explanation</span></span>  
 <span data-ttu-id="79da6-118">配置 WCF-Custom 或 WCF-CustomIsolated 传输之后，未设置代码中的 BindingType 属性。</span><span class="sxs-lookup"><span data-stu-id="79da6-118">You did not set the BindingType property in the code after configuring a WCF-Custom or a WCF-CustomIsolated transport.</span></span> <span data-ttu-id="79da6-119">或者问题可能存在于其他代码路径中。</span><span class="sxs-lookup"><span data-stu-id="79da6-119">Or the problem could be in other code paths.</span></span> <span data-ttu-id="79da6-120">必须将用户界面中的值作为绑定设置。</span><span class="sxs-lookup"><span data-stu-id="79da6-120">You must have a value in the user interface for binding setting.</span></span> <span data-ttu-id="79da6-121">在接收位置“属性”区域中查看您的配置，并确保已从下拉列表中选择绑定类型。</span><span class="sxs-lookup"><span data-stu-id="79da6-121">Review your configuration and ensure that a binding type was chosen from the drop-down list in the receive location Properties area.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79da6-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="79da6-122">User Action</span></span>  
 <span data-ttu-id="79da6-123">要解决此问题，请查看用于配置 WCF-Custom 或 WCF-CustomIsolated 传输的代码。</span><span class="sxs-lookup"><span data-stu-id="79da6-123">To resolve this error, review the code configuring the WCF-Custom or WCF-CustomIsolated transport.</span></span> <span data-ttu-id="79da6-124">絋粄**BindingType**中的 XML 数据的属性**TransportTypeData** ITransportInfo 接口的属性已正确设置。</span><span class="sxs-lookup"><span data-stu-id="79da6-124">Ensure that the **BindingType** property in the XML data for the **TransportTypeData** property of the ITransportInfo interface is set properly.</span></span>  
  
 <span data-ttu-id="79da6-125">此外，指定绑定类型，例如**basicHttpBinding**， **wsHttpBinding**，或**customBinding**。</span><span class="sxs-lookup"><span data-stu-id="79da6-125">Also, specify a binding type like **basicHttpBinding**, **wsHttpBinding**, or **customBinding**.</span></span>  
  
1. <span data-ttu-id="79da6-126">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="79da6-126">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="79da6-127">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="79da6-127">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="79da6-128">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="79da6-128">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="79da6-129">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="79da6-129">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="79da6-130">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="79da6-130">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="79da6-131">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="79da6-131">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="79da6-132">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="79da6-132">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="79da6-133">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79da6-133">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="79da6-134">确保在指定了值**绑定类型**列表。</span><span class="sxs-lookup"><span data-stu-id="79da6-134">Ensure that a value is specified in the **Binding Type** list.</span></span>  
  
   <span data-ttu-id="79da6-135">有关配置绑定的其他信息，请参阅 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 帮助中的以下资源：</span><span class="sxs-lookup"><span data-stu-id="79da6-135">For additional information on configuring binding, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="79da6-136">如何配置 Wcf-customisolated 接收位置</span><span class="sxs-lookup"><span data-stu-id="79da6-136">How to Configure a WCF-CustomIsolated Receive Location</span></span>](../core/how-to-configure-a-wcf-customisolated-receive-location.md)  
  
-   [<span data-ttu-id="79da6-137">如何配置 WCF 自定义接收位置</span><span class="sxs-lookup"><span data-stu-id="79da6-137">How to Configure a WCF-Custom Receive Location</span></span>](../core/how-to-configure-a-wcf-custom-receive-location.md)  
  
-   [<span data-ttu-id="79da6-138">如何配置 Wcf-custom 发送端口</span><span class="sxs-lookup"><span data-stu-id="79da6-138">How to Configure a WCF-Custom Send Port</span></span>](../core/how-to-configure-a-wcf-custom-send-port.md)