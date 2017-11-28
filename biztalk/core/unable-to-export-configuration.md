---
title: "无法导出配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 64f09af4-00a0-47cb-889e-d9aeb7266eb2
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 0bd7f27a2779819fff934008cc9924dfe01e6064
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-export-configuration"></a><span data-ttu-id="a9eeb-102">无法导出配置</span><span class="sxs-lookup"><span data-stu-id="a9eeb-102">Unable to export configuration</span></span>
## <a name="details"></a><span data-ttu-id="a9eeb-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="a9eeb-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="a9eeb-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="a9eeb-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="a9eeb-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="a9eeb-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="a9eeb-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="a9eeb-106">Event ID</span></span>|<span data-ttu-id="a9eeb-107">0</span><span class="sxs-lookup"><span data-stu-id="a9eeb-107">0</span></span>|  
|<span data-ttu-id="a9eeb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="a9eeb-108">Event Source</span></span>|<span data-ttu-id="a9eeb-109">0</span><span class="sxs-lookup"><span data-stu-id="a9eeb-109">0</span></span>|  
|<span data-ttu-id="a9eeb-110">组件</span><span class="sxs-lookup"><span data-stu-id="a9eeb-110">Component</span></span>|<span data-ttu-id="a9eeb-111">0</span><span class="sxs-lookup"><span data-stu-id="a9eeb-111">0</span></span>|  
|<span data-ttu-id="a9eeb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="a9eeb-112">Symbolic Name</span></span>|<span data-ttu-id="a9eeb-113">0</span><span class="sxs-lookup"><span data-stu-id="a9eeb-113">0</span></span>|  
|<span data-ttu-id="a9eeb-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="a9eeb-114">Message Text</span></span>|<span data-ttu-id="a9eeb-115">无法将配置导出到文件“{0}”</span><span class="sxs-lookup"><span data-stu-id="a9eeb-115">Unable to export configuration to file "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="a9eeb-116">解释</span><span class="sxs-lookup"><span data-stu-id="a9eeb-116">Explanation</span></span>  
 <span data-ttu-id="a9eeb-117">未正确指定某些所需属性，例如“地址(URI)”和“绑定类型”。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-117">Some required properties were not correctly specified, such as Address (URI) and Binding Type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="a9eeb-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="a9eeb-118">User Action</span></span>  
 <span data-ttu-id="a9eeb-119">使用以下过程验证属性是否正确。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-119">Use the following procedure to verify properties are correct.</span></span>  
  
#### <a name="to-verify-properties"></a><span data-ttu-id="a9eeb-120">验证属性</span><span class="sxs-lookup"><span data-stu-id="a9eeb-120">To verify properties</span></span>  
  
1.  <span data-ttu-id="a9eeb-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="a9eeb-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="a9eeb-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="a9eeb-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="a9eeb-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="a9eeb-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="a9eeb-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="a9eeb-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**导入/导出**选项卡。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  
  
9. <span data-ttu-id="a9eeb-129">单击 **“导出”**。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-129">Click **Export**.</span></span>  
  
10. <span data-ttu-id="a9eeb-130">确保已正确指定所需属性。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-130">Ensure the required properties have been correctly specified.</span></span> <span data-ttu-id="a9eeb-131">“地址(URI)”的方案必须与“绑定类型”中的方案正确匹配。</span><span class="sxs-lookup"><span data-stu-id="a9eeb-131">The scheme of the Address (URI) must correctly match the Binding type.</span></span>