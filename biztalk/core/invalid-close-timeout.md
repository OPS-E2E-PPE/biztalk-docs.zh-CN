---
title: 无效的关闭超时 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b4510329-9fd9-428f-91a3-d72723e9a5e4
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b86a75ab524a91ddf7fab7b6e764557150d55606
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257541"
---
# <a name="invalid-close-timeout"></a><span data-ttu-id="994eb-102">关闭超时无效</span><span class="sxs-lookup"><span data-stu-id="994eb-102">Invalid close timeout</span></span>
## <a name="details"></a><span data-ttu-id="994eb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="994eb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="994eb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="994eb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="994eb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="994eb-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="994eb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="994eb-106">Event ID</span></span>|<span data-ttu-id="994eb-107">0</span><span class="sxs-lookup"><span data-stu-id="994eb-107">0</span></span>|  
|<span data-ttu-id="994eb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="994eb-108">Event Source</span></span>|<span data-ttu-id="994eb-109">0</span><span class="sxs-lookup"><span data-stu-id="994eb-109">0</span></span>|  
|<span data-ttu-id="994eb-110">组件</span><span class="sxs-lookup"><span data-stu-id="994eb-110">Component</span></span>|<span data-ttu-id="994eb-111">0</span><span class="sxs-lookup"><span data-stu-id="994eb-111">0</span></span>|  
|<span data-ttu-id="994eb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="994eb-112">Symbolic Name</span></span>|<span data-ttu-id="994eb-113">0</span><span class="sxs-lookup"><span data-stu-id="994eb-113">0</span></span>|  
|<span data-ttu-id="994eb-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="994eb-114">Message Text</span></span>|<span data-ttu-id="994eb-115">关闭超时值无效。</span><span class="sxs-lookup"><span data-stu-id="994eb-115">Invalid close timeout.</span></span> <span data-ttu-id="994eb-116">有效范围： 0 到 23 小时、 介于 0 和 59 分钟、 和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="994eb-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="994eb-117">解释</span><span class="sxs-lookup"><span data-stu-id="994eb-117">Explanation</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="994eb-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="994eb-118">User Action</span></span>  
 <span data-ttu-id="994eb-119">使用以下过程配置超时范围。</span><span class="sxs-lookup"><span data-stu-id="994eb-119">Use the following procedure to configure the timeout range.</span></span>  
  
#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="994eb-120">配置超时范围的步骤</span><span class="sxs-lookup"><span data-stu-id="994eb-120">To configure the timeout range</span></span>  
  
1.  <span data-ttu-id="994eb-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="994eb-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="994eb-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="994eb-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="994eb-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="994eb-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="994eb-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="994eb-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="994eb-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="994eb-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="994eb-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="994eb-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="994eb-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="994eb-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="994eb-128">在**WCF [***传输类型***] 属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="994eb-128">In the **WCF [***transport type***] Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="994eb-129">确保超时值范围有效。</span><span class="sxs-lookup"><span data-stu-id="994eb-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="994eb-130">可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="994eb-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>