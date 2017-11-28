---
title: "冲突的绑定属性 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b08c317e-a617-464b-9ee4-007fb41d99b2
caps.latest.revision: "21"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6202385127a676d1f2714b2c3644d135a3d6a7a1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="conflicting-binding-properties"></a><span data-ttu-id="d75d7-102">绑定属性冲突</span><span class="sxs-lookup"><span data-stu-id="d75d7-102">Conflicting binding properties</span></span>
## <a name="details"></a><span data-ttu-id="d75d7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d75d7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="d75d7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d75d7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="d75d7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d75d7-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="d75d7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d75d7-106">Event ID</span></span>|<span data-ttu-id="d75d7-107">0</span><span class="sxs-lookup"><span data-stu-id="d75d7-107">0</span></span>|  
|<span data-ttu-id="d75d7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="d75d7-108">Event Source</span></span>|<span data-ttu-id="d75d7-109">0</span><span class="sxs-lookup"><span data-stu-id="d75d7-109">0</span></span>|  
|<span data-ttu-id="d75d7-110">组件</span><span class="sxs-lookup"><span data-stu-id="d75d7-110">Component</span></span>|<span data-ttu-id="d75d7-111">0</span><span class="sxs-lookup"><span data-stu-id="d75d7-111">0</span></span>|  
|<span data-ttu-id="d75d7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="d75d7-112">Symbolic Name</span></span>|<span data-ttu-id="d75d7-113">0</span><span class="sxs-lookup"><span data-stu-id="d75d7-113">0</span></span>|  
|<span data-ttu-id="d75d7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="d75d7-114">Message Text</span></span>|<span data-ttu-id="d75d7-115">冲突的绑定属性： MsmqAuthenticationMode = {0} 和而 MsmqProtectionLevel = \ {1 \} 无效。</span><span class="sxs-lookup"><span data-stu-id="d75d7-115">Conflicting binding properties: MsmqAuthenticationMode={0} and MsmqProtectionLevel={1} is invalid.</span></span> <span data-ttu-id="d75d7-116">更改其中一个属性可解决冲突</span><span class="sxs-lookup"><span data-stu-id="d75d7-116">Change one of the properties to resolve the conflict</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="d75d7-117">解释</span><span class="sxs-lookup"><span data-stu-id="d75d7-117">Explanation</span></span>  
 <span data-ttu-id="d75d7-118">WCF NetMsmq 传输的 MSMQ 保护级别属性设置为**登录**或**EncryptAndSign**为无 MSMQ 身份验证模式。</span><span class="sxs-lookup"><span data-stu-id="d75d7-118">The MSMQ protection level property of a WCF-NetMsmq transport was set to **Sign** or **EncryptAndSign** for the None MSMQ authentication mode.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="d75d7-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="d75d7-119">User Action</span></span>  
 <span data-ttu-id="d75d7-120">将“MSMQ 保护级别”或“MSMQ 身份验证模式”属性更改为与“MSMQ 保护级别”属性一致。</span><span class="sxs-lookup"><span data-stu-id="d75d7-120">Change the MSMQ protection level or the MSMQ authentication mode property to be consistent with the MSMQ protection level property.</span></span>  
  
1.  <span data-ttu-id="d75d7-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d75d7-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="d75d7-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d75d7-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  
  
3.  <span data-ttu-id="d75d7-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="d75d7-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="d75d7-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="d75d7-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="d75d7-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="d75d7-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="d75d7-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="d75d7-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="d75d7-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d75d7-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="d75d7-128">在**WCF NetMsmq 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d75d7-128">In the **WCF-NetMsmq Transport Properties** dialog box, click the **Security** tab.</span></span>  
  
9. <span data-ttu-id="d75d7-129">检查 MSMQ 中的值**身份验证模式**列表和**MSMQ 保护级别**列表。</span><span class="sxs-lookup"><span data-stu-id="d75d7-129">Check the values in the MSMQ **authentication mode** list and the **MSMQ protection level** list.</span></span>  
  
 <span data-ttu-id="d75d7-130">有关详细信息，请参阅中的以下资源[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]帮助：</span><span class="sxs-lookup"><span data-stu-id="d75d7-130">For further information, see the following resources in the [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] Help:</span></span>  
  
-   [<span data-ttu-id="d75d7-131">如何配置 WCF NetMsmq 发送端口</span><span class="sxs-lookup"><span data-stu-id="d75d7-131">How to Configure a WCF-NetMsmq Send Port</span></span>](../core/how-to-configure-a-wcf-netmsmq-send-port.md)  
  
-   [<span data-ttu-id="d75d7-132">如何配置 WCF NetMsmq 接收位置</span><span class="sxs-lookup"><span data-stu-id="d75d7-132">How to Configure a WCF-NetMsmq Receive Location</span></span>](../core/how-to-configure-a-wcf-netmsmq-receive-location.md)