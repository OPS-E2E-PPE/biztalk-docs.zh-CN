---
title: 全局设置选项卡 |Microsoft Docs
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
ms.openlocfilehash: 5c19cfb387ba3cce61d21c467c1c91674204d4c4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998678"
---
# <a name="global-settings-tab"></a><span data-ttu-id="ad361-102">全局设置选项卡</span><span class="sxs-lookup"><span data-stu-id="ad361-102">Global Settings Tab</span></span>
<span data-ttu-id="ad361-103">您使用**全局设置**选项卡可配置使用的日志记录存储区[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="ad361-103">You use the **Global Settings** tab to configure the logging store used by [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  

 <span data-ttu-id="ad361-104">在中**BTAHL7 配置资源管理器**对话框中，在**全局设置**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ad361-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Global Settings** tab, do the following:</span></span>  


|     <span data-ttu-id="ad361-105">使用此选项</span><span class="sxs-lookup"><span data-stu-id="ad361-105">Use this</span></span>      |                                                                                                                                                <span data-ttu-id="ad361-106">执行的操作</span><span class="sxs-lookup"><span data-stu-id="ad361-106">To do this</span></span>                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="ad361-107">**WMI**</span><span class="sxs-lookup"><span data-stu-id="ad361-107">**WMI**</span></span>      |                                                                 <span data-ttu-id="ad361-108">选择此选项，如果你想要生成[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 的 Management Instrumentation (WMI) 通知。</span><span class="sxs-lookup"><span data-stu-id="ad361-108">Select this option if you want to generate [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) notifications for BTAHL7.</span></span>                                                                  |
|      <span data-ttu-id="ad361-109">**SQL**</span><span class="sxs-lookup"><span data-stu-id="ad361-109">**SQL**</span></span>      | <span data-ttu-id="ad361-110">选择此选项，如果你想要使用 Microsoft[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为 BTAHL7 的日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="ad361-110">Select this option if you want to use Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your logging store for BTAHL7.</span></span> <span data-ttu-id="ad361-111">**注意：** BTAHL7 将自动创建所需的日志记录，如果不存在的表。</span><span class="sxs-lookup"><span data-stu-id="ad361-111">**Note:**  BTAHL7 automatically creates the tables required for logging if they do not exist.</span></span> |
|  <span data-ttu-id="ad361-112">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="ad361-112">**SQL Server**</span></span>   |            <span data-ttu-id="ad361-113">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。</span><span class="sxs-lookup"><span data-stu-id="ad361-113">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="ad361-114">这是必需的当您选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="ad361-114">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="ad361-115">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="ad361-115">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="ad361-116">默认服务器和数据库名称为配置的 BTAHL7 数据库。</span><span class="sxs-lookup"><span data-stu-id="ad361-116">The default server and database name is the configured BTAHL7 database.</span></span>            |
| <span data-ttu-id="ad361-117">**数据库名称**</span><span class="sxs-lookup"><span data-stu-id="ad361-117">**Database name**</span></span> |                                                 <span data-ttu-id="ad361-118">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。</span><span class="sxs-lookup"><span data-stu-id="ad361-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="ad361-119">这是必需的当您选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="ad361-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="ad361-120">允许的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="ad361-120">The maximum allowed length is 128 characters.</span></span>                                                 |
|   <span data-ttu-id="ad361-121">**事件日志**</span><span class="sxs-lookup"><span data-stu-id="ad361-121">**Event Log**</span></span>   |                <span data-ttu-id="ad361-122">选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为 BTAHL7 的日志记录存储的事件日志。</span><span class="sxs-lookup"><span data-stu-id="ad361-122">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as the logging store for BTAHL7.</span></span> <span data-ttu-id="ad361-123">您使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器查看事件消息。</span><span class="sxs-lookup"><span data-stu-id="ad361-123">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>                 |

