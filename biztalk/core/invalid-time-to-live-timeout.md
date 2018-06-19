---
title: 对实时超时的时间无效 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c2ddb6de-8c3b-4dee-a984-980e1caea95e
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 9171fd311a07317c0480e6e4d1ef35742e0e8bcd
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262093"
---
# <a name="invalid-time-to-live-timeout"></a><span data-ttu-id="866e3-102">对实时超时的时间无效</span><span class="sxs-lookup"><span data-stu-id="866e3-102">Invalid time to live timeout</span></span>
## <a name="details"></a><span data-ttu-id="866e3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="866e3-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="866e3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="866e3-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="866e3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="866e3-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="866e3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="866e3-106">Event ID</span></span>|<span data-ttu-id="866e3-107">0</span><span class="sxs-lookup"><span data-stu-id="866e3-107">0</span></span>|  
|<span data-ttu-id="866e3-108">事件源</span><span class="sxs-lookup"><span data-stu-id="866e3-108">Event Source</span></span>|<span data-ttu-id="866e3-109">0</span><span class="sxs-lookup"><span data-stu-id="866e3-109">0</span></span>|  
|<span data-ttu-id="866e3-110">组件</span><span class="sxs-lookup"><span data-stu-id="866e3-110">Component</span></span>|<span data-ttu-id="866e3-111">0</span><span class="sxs-lookup"><span data-stu-id="866e3-111">0</span></span>|  
|<span data-ttu-id="866e3-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="866e3-112">Symbolic Name</span></span>|<span data-ttu-id="866e3-113">0</span><span class="sxs-lookup"><span data-stu-id="866e3-113">0</span></span>|  
|<span data-ttu-id="866e3-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="866e3-114">Message Text</span></span>|<span data-ttu-id="866e3-115">对实时超时的时间无效。</span><span class="sxs-lookup"><span data-stu-id="866e3-115">Invalid time to live timeout.</span></span> <span data-ttu-id="866e3-116">有效范围： 0 到 23 小时、 介于 0 和 59 分钟、 和 0 到 59 秒</span><span class="sxs-lookup"><span data-stu-id="866e3-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="866e3-117">解释</span><span class="sxs-lookup"><span data-stu-id="866e3-117">Explanation</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="866e3-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="866e3-118">User Action</span></span>  
 <span data-ttu-id="866e3-119">使用以下过程配置超时范围。</span><span class="sxs-lookup"><span data-stu-id="866e3-119">Use the following procedure to configure the timeout range.</span></span>  
  
#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="866e3-120">配置超时范围的步骤</span><span class="sxs-lookup"><span data-stu-id="866e3-120">To configure the timeout range</span></span>  
  
1.  <span data-ttu-id="866e3-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="866e3-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="866e3-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="866e3-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="866e3-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="866e3-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="866e3-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="866e3-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="866e3-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="866e3-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="866e3-126">在端口**类型**列表中，选择**WCF NetMsmq**。</span><span class="sxs-lookup"><span data-stu-id="866e3-126">In the port **Type** list, select **WCF-NetMsmq**.</span></span>  
  
7.  <span data-ttu-id="866e3-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="866e3-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="866e3-128">在**WCF NetMsmq 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="866e3-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="866e3-129">在**队列设置**部分中，确保**消息到实时的 (dd:hh:mm:ss) 的时间**范围是否有效。</span><span class="sxs-lookup"><span data-stu-id="866e3-129">In the **Queue Settings** section, ensure the **Message time to live (dd:hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="866e3-130">可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="866e3-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>