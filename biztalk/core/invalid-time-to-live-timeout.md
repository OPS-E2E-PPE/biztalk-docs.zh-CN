---
title: 无效生存时间超时 |Microsoft Docs
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
ms.openlocfilehash: 023cf9829d71155fec439f040bb526fd82572ac8
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37011606"
---
# <a name="invalid-time-to-live-timeout"></a><span data-ttu-id="111a5-102">无效生存时间超时</span><span class="sxs-lookup"><span data-stu-id="111a5-102">Invalid time to live timeout</span></span>
## <a name="details"></a><span data-ttu-id="111a5-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="111a5-103">Details</span></span>  

|                 |                                                                                                |
|-----------------|------------------------------------------------------------------------------------------------|
|  <span data-ttu-id="111a5-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="111a5-104">Product Name</span></span>   |       [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]       |
| <span data-ttu-id="111a5-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="111a5-105">Product Version</span></span> |                   [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                   |
|    <span data-ttu-id="111a5-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="111a5-106">Event ID</span></span>     |                                               <span data-ttu-id="111a5-107">0</span><span class="sxs-lookup"><span data-stu-id="111a5-107">0</span></span>                                                |
|  <span data-ttu-id="111a5-108">事件源</span><span class="sxs-lookup"><span data-stu-id="111a5-108">Event Source</span></span>   |                                               <span data-ttu-id="111a5-109">0</span><span class="sxs-lookup"><span data-stu-id="111a5-109">0</span></span>                                                |
|    <span data-ttu-id="111a5-110">组件</span><span class="sxs-lookup"><span data-stu-id="111a5-110">Component</span></span>    |                                               <span data-ttu-id="111a5-111">0</span><span class="sxs-lookup"><span data-stu-id="111a5-111">0</span></span>                                                |
|  <span data-ttu-id="111a5-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="111a5-112">Symbolic Name</span></span>  |                                               <span data-ttu-id="111a5-113">0</span><span class="sxs-lookup"><span data-stu-id="111a5-113">0</span></span>                                                |
|  <span data-ttu-id="111a5-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="111a5-114">Message Text</span></span>   | <span data-ttu-id="111a5-115">无效生存时间超时。</span><span class="sxs-lookup"><span data-stu-id="111a5-115">Invalid time to live timeout.</span></span> <span data-ttu-id="111a5-116">有效范围： 0 至 23 小时，0-59 分钟和 0 到 59 秒</span><span class="sxs-lookup"><span data-stu-id="111a5-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds</span></span> |

## <a name="explanation"></a><span data-ttu-id="111a5-117">解释</span><span class="sxs-lookup"><span data-stu-id="111a5-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="111a5-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="111a5-118">User Action</span></span>  
 <span data-ttu-id="111a5-119">使用以下过程配置超时范围。</span><span class="sxs-lookup"><span data-stu-id="111a5-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="111a5-120">配置超时范围的步骤</span><span class="sxs-lookup"><span data-stu-id="111a5-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="111a5-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="111a5-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="111a5-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="111a5-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="111a5-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="111a5-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="111a5-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="111a5-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="111a5-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="111a5-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="111a5-126">在端口**类型**列表中，选择**Wcf-netmsmq**。</span><span class="sxs-lookup"><span data-stu-id="111a5-126">In the port **Type** list, select **WCF-NetMsmq**.</span></span>  

7. <span data-ttu-id="111a5-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="111a5-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="111a5-128">在中**Wcf-netmsmq 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="111a5-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="111a5-129">在中**队列设置**部分中，确保**消息到实时 (dd:hh:mm:ss) 时间**范围是否有效。</span><span class="sxs-lookup"><span data-stu-id="111a5-129">In the **Queue Settings** section, ensure the **Message time to live (dd:hh:mm:ss)** range is valid.</span></span> <span data-ttu-id="111a5-130">可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="111a5-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
