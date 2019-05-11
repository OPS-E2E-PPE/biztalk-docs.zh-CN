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
ms.openlocfilehash: 77a883a4d506d3ee65a5ef0edc7ab5dc6495f039
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65267979"
---
# <a name="global-settings-tab"></a><span data-ttu-id="b6934-102">全局设置选项卡</span><span class="sxs-lookup"><span data-stu-id="b6934-102">Global Settings Tab</span></span>
<span data-ttu-id="b6934-103">您使用**全局设置**选项卡可配置使用的日志记录存储区[!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)]。</span><span class="sxs-lookup"><span data-stu-id="b6934-103">You use the **Global Settings** tab to configure the logging store used by [!INCLUDE[HL7_CurrentVersion_FirstRef](../../includes/hl7-currentversion-firstref-md.md)].</span></span>  

 <span data-ttu-id="b6934-104">在中**BTAHL7 配置资源管理器**对话框中，在**全局设置**选项卡上，执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="b6934-104">In the **BTAHL7 Configuration Explorer** dialog box, on the **Global Settings** tab, do the following:</span></span>  


|     <span data-ttu-id="b6934-105">使用此选项</span><span class="sxs-lookup"><span data-stu-id="b6934-105">Use this</span></span>      |                                                                                                                                                <span data-ttu-id="b6934-106">执行的操作</span><span class="sxs-lookup"><span data-stu-id="b6934-106">To do this</span></span>                                                                                                                                                |
|-------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|      <span data-ttu-id="b6934-107">**WMI**</span><span class="sxs-lookup"><span data-stu-id="b6934-107">**WMI**</span></span>      |                                                                 <span data-ttu-id="b6934-108">选择此选项，如果你想要生成[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]BTAHL7 的 Management Instrumentation (WMI) 通知。</span><span class="sxs-lookup"><span data-stu-id="b6934-108">Select this option if you want to generate [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Management Instrumentation (WMI) notifications for BTAHL7.</span></span>                                                                  |
|      <span data-ttu-id="b6934-109">**SQL**</span><span class="sxs-lookup"><span data-stu-id="b6934-109">**SQL**</span></span>      | <span data-ttu-id="b6934-110">选择此选项，如果你想要使用 Microsoft[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]作为 BTAHL7 的日志记录存储。</span><span class="sxs-lookup"><span data-stu-id="b6934-110">Select this option if you want to use Microsoft [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] as your logging store for BTAHL7.</span></span> <span data-ttu-id="b6934-111">**注意：** BTAHL7 将自动创建所需的日志记录，如果不存在的表。</span><span class="sxs-lookup"><span data-stu-id="b6934-111">**Note:**  BTAHL7 automatically creates the tables required for logging if they do not exist.</span></span> |
|  <span data-ttu-id="b6934-112">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="b6934-112">**SQL Server**</span></span>   |            <span data-ttu-id="b6934-113">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]名称。</span><span class="sxs-lookup"><span data-stu-id="b6934-113">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] name.</span></span> <span data-ttu-id="b6934-114">这是必需的当您选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="b6934-114">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="b6934-115">允许的最大长度为 64 个字符。</span><span class="sxs-lookup"><span data-stu-id="b6934-115">The maximum allowed length is 64 characters.</span></span><br /><br /> <span data-ttu-id="b6934-116">默认服务器和数据库名称为配置的 BTAHL7 数据库。</span><span class="sxs-lookup"><span data-stu-id="b6934-116">The default server and database name is the configured BTAHL7 database.</span></span>            |
| <span data-ttu-id="b6934-117">**数据库名称**</span><span class="sxs-lookup"><span data-stu-id="b6934-117">**Database name**</span></span> |                                                 <span data-ttu-id="b6934-118">类型[!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)]数据库名称。</span><span class="sxs-lookup"><span data-stu-id="b6934-118">Type the [!INCLUDE[btsSQLServerNoVersion](../../includes/btssqlservernoversion-md.md)] database name.</span></span> <span data-ttu-id="b6934-119">这是必需的当您选择**SQL**选项。</span><span class="sxs-lookup"><span data-stu-id="b6934-119">This is required when you select the **SQL** option.</span></span> <span data-ttu-id="b6934-120">允许的最大长度为 128 个字符。</span><span class="sxs-lookup"><span data-stu-id="b6934-120">The maximum allowed length is 128 characters.</span></span>                                                 |
|   <span data-ttu-id="b6934-121">**事件日志**</span><span class="sxs-lookup"><span data-stu-id="b6934-121">**Event Log**</span></span>   |                <span data-ttu-id="b6934-122">选择此选项，如果你想要使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]作为 BTAHL7 的日志记录存储的事件日志。</span><span class="sxs-lookup"><span data-stu-id="b6934-122">Select this option if you want to use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Log as the logging store for BTAHL7.</span></span> <span data-ttu-id="b6934-123">您使用[!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)]事件查看器查看事件消息。</span><span class="sxs-lookup"><span data-stu-id="b6934-123">You use the [!INCLUDE[btsWinNoVersion](../../includes/btswinnoversion-md.md)] Event Viewer to view event messages.</span></span>                 |

