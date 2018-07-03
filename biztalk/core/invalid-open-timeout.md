---
title: 打开超时无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0047cf43-fcc3-40b4-abeb-bf1b6e7a422b
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: b32e06d5f26eafe5d5184a995adc7103e659a739
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37023611"
---
# <a name="invalid-open-timeout"></a><span data-ttu-id="30961-102">打开超时无效</span><span class="sxs-lookup"><span data-stu-id="30961-102">Invalid open timeout</span></span>
## <a name="details"></a><span data-ttu-id="30961-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="30961-103">Details</span></span>  

|                 |                                                                                         |
|-----------------|-----------------------------------------------------------------------------------------|
|  <span data-ttu-id="30961-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="30961-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]    |
| <span data-ttu-id="30961-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="30961-105">Product Version</span></span> |               [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                |
|    <span data-ttu-id="30961-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="30961-106">Event ID</span></span>     |                                            <span data-ttu-id="30961-107">0</span><span class="sxs-lookup"><span data-stu-id="30961-107">0</span></span>                                            |
|  <span data-ttu-id="30961-108">事件源</span><span class="sxs-lookup"><span data-stu-id="30961-108">Event Source</span></span>   |                                            <span data-ttu-id="30961-109">0</span><span class="sxs-lookup"><span data-stu-id="30961-109">0</span></span>                                            |
|    <span data-ttu-id="30961-110">组件</span><span class="sxs-lookup"><span data-stu-id="30961-110">Component</span></span>    |                                            <span data-ttu-id="30961-111">0</span><span class="sxs-lookup"><span data-stu-id="30961-111">0</span></span>                                            |
|  <span data-ttu-id="30961-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="30961-112">Symbolic Name</span></span>  |                                            <span data-ttu-id="30961-113">0</span><span class="sxs-lookup"><span data-stu-id="30961-113">0</span></span>                                            |
|  <span data-ttu-id="30961-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="30961-114">Message Text</span></span>   | <span data-ttu-id="30961-115">打开超时无效。</span><span class="sxs-lookup"><span data-stu-id="30961-115">Invalid open timeout.</span></span> <span data-ttu-id="30961-116">有效范围： 0 至 23 小时，0-59 分钟和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="30961-116">Valid range: 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span> |

## <a name="explanation"></a><span data-ttu-id="30961-117">解释</span><span class="sxs-lookup"><span data-stu-id="30961-117">Explanation</span></span>  

## <a name="user-action"></a><span data-ttu-id="30961-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="30961-118">User Action</span></span>  
 <span data-ttu-id="30961-119">使用以下过程配置超时范围。</span><span class="sxs-lookup"><span data-stu-id="30961-119">Use the following procedure to configure the timeout range.</span></span>  

#### <a name="to-configure-the-timeout-range"></a><span data-ttu-id="30961-120">配置超时范围的步骤</span><span class="sxs-lookup"><span data-stu-id="30961-120">To configure the timeout range</span></span>  

1. <span data-ttu-id="30961-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="30961-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="30961-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="30961-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="30961-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="30961-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="30961-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="30961-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="30961-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="30961-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="30961-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="30961-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="30961-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="30961-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="30961-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="30961-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="30961-129">确保超时值范围有效。</span><span class="sxs-lookup"><span data-stu-id="30961-129">Ensure the timeout range is valid.</span></span> <span data-ttu-id="30961-130">可接受的值包括：0 到 23 小时、0 到 59 分钟和 0 到 59 秒。</span><span class="sxs-lookup"><span data-stu-id="30961-130">Acceptable values are 0 to 23 hours, 0 to 59 minutes, and 0 to 59 seconds.</span></span>
