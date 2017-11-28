---
title: "选择日志记录存储 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- auditing, configuring
ms.assetid: 6ba64c59-3a15-4c10-b44f-18e0e432c6d3
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e15bc1f9004c79b8d87375d9fe9f6cb805e12e94
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="selecting-the-logging-store"></a><span data-ttu-id="6d3aa-102">选择日志记录存储</span><span class="sxs-lookup"><span data-stu-id="6d3aa-102">Selecting the Logging Store</span></span>
[!INCLUDE[btsCoName](../../includes/btsconame-md.md)]<span data-ttu-id="6d3aa-103">[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]你提供的选项来选择不同的日志记录存储的组合，如[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]Management Instrumentation (WMI) [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]，和[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件日志。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-103"> [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)] provides you with the option to select a combination of different logging stores, such as [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI), [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)], and [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log.</span></span>  
  
 <span data-ttu-id="6d3aa-104">你使用[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器来配置日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-104">You use the [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer to configure the logging store.</span></span>  
  
 <span data-ttu-id="6d3aa-105">使用以下过程来打开[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器和选择日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-105">Use the following procedures to open [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer and select the logging store.</span></span>  
  
### <a name="to-open-btahl7-configuration-explorer"></a><span data-ttu-id="6d3aa-106">若要打开 BTAHL7 配置资源管理器</span><span class="sxs-lookup"><span data-stu-id="6d3aa-106">To open BTAHL7 Configuration Explorer</span></span>  
  
-   <span data-ttu-id="6d3aa-107">单击**启动**，单击**程序**，单击**Microsoft BizTalk\<版本 > Accelerator for HL7**，然后单击**BTAHL7配置资源管理器**。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-107">Click **Start**, click **Programs**, click **Microsoft BizTalk \<version> Accelerator for HL7**, and then click **BTAHL7 Configuration Explorer**.</span></span>  
  
### <a name="to-select-the--logging-store"></a><span data-ttu-id="6d3aa-108">若要选择的日志记录存储</span><span class="sxs-lookup"><span data-stu-id="6d3aa-108">To select the  logging store</span></span>  
  
1.  <span data-ttu-id="6d3aa-109">在[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]配置资源管理器，请在**全局设置**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6d3aa-109">In [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Configuration Explorer, on the **Global Settings** tab, do the following:</span></span>  
  
    |<span data-ttu-id="6d3aa-110">使用此选项</span><span class="sxs-lookup"><span data-stu-id="6d3aa-110">Use this</span></span>|<span data-ttu-id="6d3aa-111">执行的操作</span><span class="sxs-lookup"><span data-stu-id="6d3aa-111">To do this</span></span>|  
    |--------------|----------------|  
    |<span data-ttu-id="6d3aa-112">**WMI**</span><span class="sxs-lookup"><span data-stu-id="6d3aa-112">**WMI**</span></span>|<span data-ttu-id="6d3aa-113">如果你想要生成 BTAHL7 的 WMI 通知，请选择此选项。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-113">Select this option if you want to generate WMI notifications for BTAHL7.</span></span>|  
    |<span data-ttu-id="6d3aa-114">**SQL**</span><span class="sxs-lookup"><span data-stu-id="6d3aa-114">**SQL**</span></span>|<span data-ttu-id="6d3aa-115">选择此选项，如果你想要使用[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-115">Select this option if you want to use [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your  logging store.</span></span> <span data-ttu-id="6d3aa-116">**注意：** BTAHL7 自动创建所需的日志记录如果它们尚不存在的表。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-116">**Note:**  BTAHL7 automatically creates the tables required for  logging if they do not exist.</span></span>|  
    |<span data-ttu-id="6d3aa-117">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6d3aa-117">**SQL Server**</span></span>|<span data-ttu-id="6d3aa-118">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="6d3aa-119">这是必需的当你选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="6d3aa-120">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-120">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="6d3aa-121">默认服务器和数据库名称为配置的 BTAHL7 数据库。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-121">The default server and database name is the configured BTAHL7 database.</span></span>|  
    |<span data-ttu-id="6d3aa-122">**数据库名称**</span><span class="sxs-lookup"><span data-stu-id="6d3aa-122">**Database name**</span></span>|<span data-ttu-id="6d3aa-123">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-123">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="6d3aa-124">这是必需的当你选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-124">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="6d3aa-125">允许的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-125">The maximum allowed length is 128 characters.</span></span>|  
    |<span data-ttu-id="6d3aa-126">**事件日志**</span><span class="sxs-lookup"><span data-stu-id="6d3aa-126">**Event  Log**</span></span>|<span data-ttu-id="6d3aa-127">选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为日志记录存储的事件日志。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-127">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as your  logging store.</span></span> <span data-ttu-id="6d3aa-128">你使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器以查看事件消息。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-128">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>|  
  
2.  <span data-ttu-id="6d3aa-129">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-129">Click **Save**.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d3aa-130">事件所记录的日志记录的事件代理的区域设置依赖于日志记录服务帐户的区域设置。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-130">The locale of the events logged by the  Logging event broker depend on the locale of the  Logging Service account.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="6d3aa-131">当更改日志记录服务帐户密码，则应首先更改中的密码[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)]目录服务和日志记录服务运行它的每个服务器上的日志记录服务密码更改后的然后重新启动。</span><span class="sxs-lookup"><span data-stu-id="6d3aa-131">When changing the  Logging Service account password, you should first change the password in [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsAD](../../includes/btsad-md.md)] directory service, and then restart the  Logging Service after changing the  Logging Service password on every server running it.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d3aa-132">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6d3aa-132">See Also</span></span>  
 <span data-ttu-id="6d3aa-133">[消息批处理](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span><span class="sxs-lookup"><span data-stu-id="6d3aa-133">[Message Batching](../../adapters-and-accelerators/accelerator-hl7/message-batching.md) </span></span>  
 [<span data-ttu-id="6d3aa-134">日志记录配置</span><span class="sxs-lookup"><span data-stu-id="6d3aa-134">Logging Configuration</span></span>](../../adapters-and-accelerators/accelerator-hl7/logging-configuration.md)