---
title: 如何调整配置缓存刷新间隔 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 63c6c998-e9c0-48f1-a36a-f1fcb916321b
caps.latest.revision: 3
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 99cffcba5181f62267ca9eeed9c9c3610ea7ee1b
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65277165"
---
# <a name="how-to-adjust-the-configuration-cache-refresh-interval"></a><span data-ttu-id="97b32-102">如何调整配置缓存刷新间隔</span><span class="sxs-lookup"><span data-stu-id="97b32-102">How to Adjust the Configuration Cache Refresh Interval</span></span>
<span data-ttu-id="97b32-103">配置缓存刷新间隔定义 BizTalk Server 中更新的终结点配置的时间段。</span><span class="sxs-lookup"><span data-stu-id="97b32-103">The configuration cache refresh interval defines the time period in which BizTalk Server updates the configuration of the endpoints.</span></span> <span data-ttu-id="97b32-104">启动 BizTalk Server 时，BizTalk Server 管理，例如 MessageBox 数据库、 服务器属性、 适配器和到跟踪数据库的连接中的所有项都存储在配置缓存。</span><span class="sxs-lookup"><span data-stu-id="97b32-104">When you start BizTalk Server, all items in BizTalk Server administration, such as MessageBox databases, server properties, adapters, and connections to the Tracking database, are stored in the configuration cache.</span></span> <span data-ttu-id="97b32-105">通过配置刷新间隔来刷新其缓存中的所有项。</span><span class="sxs-lookup"><span data-stu-id="97b32-105">All items in the cache are refreshed by the configuration refresh interval.</span></span> <span data-ttu-id="97b32-106">默认情况下，这是每隔 60 秒，除服务器数据库连接和服务器属性。</span><span class="sxs-lookup"><span data-stu-id="97b32-106">By default this is every 60 seconds, except for the server database connections and server properties.</span></span> <span data-ttu-id="97b32-107">这意味着，如果您更改为 BizTalk 组，如 SMTP 主机的常规属性所做的更改将选择 60 秒内。</span><span class="sxs-lookup"><span data-stu-id="97b32-107">This means that if you change the general properties for a BizTalk group, such as the SMTP host, the changes are picked up within 60 seconds.</span></span> <span data-ttu-id="97b32-108">你对其进行刷新之前，不会反映系统实例外部的当前打开的 BizTalk Server 管理控制台所做的更改。</span><span class="sxs-lookup"><span data-stu-id="97b32-108">System changes made outside the currently open instance of the BizTalk Server Administration console are not reflected until you refresh it.</span></span>  
  
 <span data-ttu-id="97b32-109">配置缓存刷新间隔是 BizTalk 组属性的一部分。</span><span class="sxs-lookup"><span data-stu-id="97b32-109">The configuration cache refresh interval is part of the BizTalk group properties.</span></span>  
  
## <a name="prerequisites"></a><span data-ttu-id="97b32-110">先决条件</span><span class="sxs-lookup"><span data-stu-id="97b32-110">Prerequisites</span></span>  
 <span data-ttu-id="97b32-111">若要执行本主题中的过程，必须以 BizTalk Server Administrators 组的成员的身份登录。</span><span class="sxs-lookup"><span data-stu-id="97b32-111">To perform the procedure in this topic, you must be logged on as a member of the BizTalk Server Administrators group.</span></span>  
  
### <a name="to-adjust-the-cache-refresh-interval"></a><span data-ttu-id="97b32-112">若要调整缓存刷新间隔</span><span class="sxs-lookup"><span data-stu-id="97b32-112">To adjust the cache refresh interval</span></span>  
  
1. <span data-ttu-id="97b32-113">单击**启动**，单击**所有程序**，单击**Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="97b32-113">Click **Start**, click **All Programs**, click **Microsoft** [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="97b32-114">在控制台树中，展开[!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**管理**，右键单击**BizTalk 组**，然后单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="97b32-114">In the console tree, expand [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)] **Administration**, right-click **BizTalk Group**, and then click **Settings**.</span></span>  
  
3. <span data-ttu-id="97b32-115">在中**BizTalk 设置仪表板**对话框中，选择**常规**选项卡。有关**配置刷新间隔**属性，键入或选择的时间 （以秒为单位） 中的所有项[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]管理缓存必须配置缓存刷新之间的等待，然后单击**确定**.</span><span class="sxs-lookup"><span data-stu-id="97b32-115">In the **BizTalk Settings Dashboard** dialog box, select the **General** tab. For the **Configuration refresh interval** property, type or select the time (in seconds) that all items in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] administration cache must wait between configuration cache refreshes, and then click **OK**.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="97b32-116">在刷新中所涉及的项包括 MessageBox 数据库、 服务器属性、 适配器和跟踪数据库的连接。</span><span class="sxs-lookup"><span data-stu-id="97b32-116">Items involved in the refresh include the MessageBox databases, server properties, adapters, and connections to the Tracking database.</span></span>  
  
   > [!NOTE]  
   >  <span data-ttu-id="97b32-117">默认情况下，每 60 秒，除服务器数据库连接和服务器属性之外刷新配置缓存中的所有对象。</span><span class="sxs-lookup"><span data-stu-id="97b32-117">By default, all objects in the configuration cache are refreshed every 60 seconds, except for the server database connections and server properties.</span></span>