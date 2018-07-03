---
title: 将适配器安装到 BizTalk Server |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 1164468d-75a9-4116-87a6-6055948c198b
caps.latest.revision: 19
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 13e810a14fec9b51c0d6b0ef1d7b55db234d0a0b
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37005622"
---
# <a name="install-the-adapter-into-biztalk-server"></a><span data-ttu-id="58618-102">将适配器安装到 BizTalk Server 中</span><span class="sxs-lookup"><span data-stu-id="58618-102">Install the Adapter into BizTalk Server</span></span>
<span data-ttu-id="58618-103">在向注册表写入了正确的 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 注册表项后，必须将适配器添加到 BizTalk 管理数据库中。</span><span class="sxs-lookup"><span data-stu-id="58618-103">After the proper [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] entries have been written to the registry the adapter must be added to the BizTalk Management database.</span></span> <span data-ttu-id="58618-104">将适配器添加到此数据库之后，它将成为当前可配置的适配器，在正确配置后即可处理消息。</span><span class="sxs-lookup"><span data-stu-id="58618-104">After the adapter is added to this database it is an actively configured adapter and can process messages when it is properly configured.</span></span> <span data-ttu-id="58618-105">通过使用的适配器安装到数据库[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台。</span><span class="sxs-lookup"><span data-stu-id="58618-105">You install the adapter into the database by using the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span> <span data-ttu-id="58618-106">将适配器安装到数据库之后，请重新启动主机实例。</span><span class="sxs-lookup"><span data-stu-id="58618-106">After installing the adapter in the database, restart the host instance.</span></span>  

> [!NOTE]
>  <span data-ttu-id="58618-107">若要在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台中看到添加的适配器，必须在 HKLM 注册表中正确注册该适配器并实现必要的适配器接口。</span><span class="sxs-lookup"><span data-stu-id="58618-107">To be visible for addition in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, an adapter must be properly registered in the HKLM registry and must implement the necessary adapter interfaces.</span></span>  

### <a name="to-install-the-static-sample-adapter"></a><span data-ttu-id="58618-108">安装示例静态适配器</span><span class="sxs-lookup"><span data-stu-id="58618-108">To install the static sample adapter</span></span>  

1. <span data-ttu-id="58618-109">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="58618-109">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="58618-110">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="58618-110">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="58618-111">展开**平台设置**，然后选择**适配器**。</span><span class="sxs-lookup"><span data-stu-id="58618-111">Expand **Platform Settings** and select **Adapters**.</span></span>  

4. <span data-ttu-id="58618-112">右键单击**适配器**，单击**新建**，然后单击**适配器**。</span><span class="sxs-lookup"><span data-stu-id="58618-112">Right-click **Adapters**, click **New**, and then click **Adapter**.</span></span>  

5. <span data-ttu-id="58618-113">在中**适配器属性**对话框框中，执行以下操作。</span><span class="sxs-lookup"><span data-stu-id="58618-113">In the **Adapter Properties** dialog box, do the following.</span></span>  


   |  <span data-ttu-id="58618-114">使用此选项</span><span class="sxs-lookup"><span data-stu-id="58618-114">Use this</span></span>   |                      <span data-ttu-id="58618-115">执行的操作</span><span class="sxs-lookup"><span data-stu-id="58618-115">To do this</span></span>                       |
   |-------------|-------------------------------------------------------|
   |    <span data-ttu-id="58618-116">“属性”</span><span class="sxs-lookup"><span data-stu-id="58618-116">Name</span></span>     |                   <span data-ttu-id="58618-117">类型**静态**。</span><span class="sxs-lookup"><span data-stu-id="58618-117">Type **Static**.</span></span>                    |
   |   <span data-ttu-id="58618-118">适配器</span><span class="sxs-lookup"><span data-stu-id="58618-118">Adapter</span></span>   | <span data-ttu-id="58618-119">选择**Static DotNetFile**从下拉列表。</span><span class="sxs-lookup"><span data-stu-id="58618-119">Select **Static DotNetFile** from the drop-down list.</span></span> |
   | <span data-ttu-id="58618-120">Description</span><span class="sxs-lookup"><span data-stu-id="58618-120">Description</span></span> |            <span data-ttu-id="58618-121">类型**示例静态适配器**。</span><span class="sxs-lookup"><span data-stu-id="58618-121">Type **Sample Static Adapter**.</span></span>            |


6. <span data-ttu-id="58618-122">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="58618-122">Click **OK**.</span></span>  

    <span data-ttu-id="58618-123">此时，该静态适配器将显示在 [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] 管理控制台右侧窗口的适配器列表中。</span><span class="sxs-lookup"><span data-stu-id="58618-123">The static adapter now appears in the list of adapters in the right window of the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console.</span></span>  

### <a name="to-stop-and-restart-the-host-instance"></a><span data-ttu-id="58618-124">若要停止并重新启动主机实例</span><span class="sxs-lookup"><span data-stu-id="58618-124">To stop and restart the host instance</span></span>  

1. <span data-ttu-id="58618-125">单击**启动**，依次指向**所有程序**，指向[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**。</span><span class="sxs-lookup"><span data-stu-id="58618-125">Click **Start**, point to **All Programs**, point to [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**.</span></span>  

2. <span data-ttu-id="58618-126">在中[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理控制台中，双击**BizTalk 组**节点。</span><span class="sxs-lookup"><span data-stu-id="58618-126">In the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Administration console, double-click the  **BizTalk Group** node.</span></span>  

3. <span data-ttu-id="58618-127">展开**平台设置**，选择**主机**，然后选择**BizTalkServerApplication**在结果窗格中。</span><span class="sxs-lookup"><span data-stu-id="58618-127">Expand **Platform Settings**, select **Hosts**, and then select **BizTalkServerApplication** in the results pane.</span></span>  

4. <span data-ttu-id="58618-128">右键单击主机实例 （通常情况下，计算机名称），然后依次**停止**。</span><span class="sxs-lookup"><span data-stu-id="58618-128">Right-click the host instance (typically, the computer name), and then click **Stop**.</span></span>  

    <span data-ttu-id="58618-129">主机实例的状态将变为**已停止**。</span><span class="sxs-lookup"><span data-stu-id="58618-129">The status of the host instance changes to **Stopped**.</span></span>  

5. <span data-ttu-id="58618-130">在结果窗格中，右键单击该主机实例，然后依次**启动**。</span><span class="sxs-lookup"><span data-stu-id="58618-130">In the results pane, right-click the host instance, and then click **Start**.</span></span>  

    <span data-ttu-id="58618-131">主机实例的状态将变为**启动挂起**。</span><span class="sxs-lookup"><span data-stu-id="58618-131">The status of the host instance changes to **Start pending**.</span></span> <span data-ttu-id="58618-132">您必须单击**刷新**，或右键单击主机实例，然后单击**刷新**，以将状态更改为**运行**。</span><span class="sxs-lookup"><span data-stu-id="58618-132">You must click **Refresh**, or right-click the host instance and then click **Refresh**, to change the status to **Running**.</span></span>