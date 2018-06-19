---
title: 全局设置选项卡 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
f1_keywords:
- btahl7.configurationexplorer.tab.globalsettings
helpviewer_keywords:
- configuring, auditing
- configuring, logging
- logging, configuring
- Global Settings tab [Configuration Explorer]
- auditing, configuring
ms.assetid: 057189f7-9072-4841-950f-371ba1f73a15
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 022ad14cc93b55c7ad928c06358f2714531b40b8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22204893"
---
# <a name="global-settings-tab"></a><span data-ttu-id="09131-102">全局设置选项卡</span><span class="sxs-lookup"><span data-stu-id="09131-102">Global Settings Tab</span></span>
<span data-ttu-id="09131-103">你使用**全局设置**选项卡来配置使用的日志记录存储区[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="09131-103">You use the **Global Settings** tab to configure the logging store used by [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  
  
 <span data-ttu-id="09131-104">在**BTAHL7 配置资源管理器**对话框中，在**全局设置**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="09131-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Global Settings** tab, do the following:</span></span>  
  
|<span data-ttu-id="09131-105">使用此选项</span><span class="sxs-lookup"><span data-stu-id="09131-105">Use this</span></span>|<span data-ttu-id="09131-106">执行的操作</span><span class="sxs-lookup"><span data-stu-id="09131-106">To do this</span></span>|  
|--------------|----------------|  
|<span data-ttu-id="09131-107">**WMI**</span><span class="sxs-lookup"><span data-stu-id="09131-107">**WMI**</span></span>|<span data-ttu-id="09131-108">选择此选项，如果你想要生成[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 Management Instrumentation (WMI) 通知。</span><span class="sxs-lookup"><span data-stu-id="09131-108">Select this option if you want to generate [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) notifications for BTAHL7.</span></span>|  
|<span data-ttu-id="09131-109">**SQL**</span><span class="sxs-lookup"><span data-stu-id="09131-109">**SQL**</span></span>|<span data-ttu-id="09131-110">选择此选项，如果你想要使用[!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为 BTAHL7 你日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="09131-110">Select this option if you want to use [!INCLUDE[btsCoName](../../includes/btsconame-md.md)][!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your logging store for BTAHL7.</span></span> <span data-ttu-id="09131-111">**注意：** BTAHL7 自动创建所需的日志记录如果它们尚不存在的表。</span><span class="sxs-lookup"><span data-stu-id="09131-111">**Note:**  BTAHL7 automatically creates the tables required for logging if they do not exist.</span></span>|  
|<span data-ttu-id="09131-112">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="09131-112">**SQL Server**</span></span>|<span data-ttu-id="09131-113">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。</span><span class="sxs-lookup"><span data-stu-id="09131-113">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="09131-114">这是必需的当你选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="09131-114">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="09131-115">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="09131-115">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="09131-116">默认服务器和数据库名称为配置的 BTAHL7 数据库。</span><span class="sxs-lookup"><span data-stu-id="09131-116">The default server and database name is the configured BTAHL7 database.</span></span>|  
|<span data-ttu-id="09131-117">**数据库名称**</span><span class="sxs-lookup"><span data-stu-id="09131-117">**Database name**</span></span>|<span data-ttu-id="09131-118">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。</span><span class="sxs-lookup"><span data-stu-id="09131-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="09131-119">这是必需的当你选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="09131-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="09131-120">允许的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="09131-120">The maximum allowed length is 128 characters.</span></span>|  
|<span data-ttu-id="09131-121">**事件日志**</span><span class="sxs-lookup"><span data-stu-id="09131-121">**Event Log**</span></span>|<span data-ttu-id="09131-122">选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为 BTAHL7 的日志记录存储的事件日志。</span><span class="sxs-lookup"><span data-stu-id="09131-122">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as the logging store for BTAHL7.</span></span> <span data-ttu-id="09131-123">你使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器以查看事件消息。</span><span class="sxs-lookup"><span data-stu-id="09131-123">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>|