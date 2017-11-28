---
title: "无法导入配置 |Microsoft 文档"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2887da50-4f74-4259-a7d6-c87bc9b9fc58
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8e565b466e4f9ce8af3745948952b4318a029ff2
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
---
# <a name="unable-to-import-configuration"></a><span data-ttu-id="491f7-102">无法导入配置</span><span class="sxs-lookup"><span data-stu-id="491f7-102">Unable to import configuration</span></span>
## <a name="details"></a><span data-ttu-id="491f7-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="491f7-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="491f7-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="491f7-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="491f7-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="491f7-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="491f7-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="491f7-106">Event ID</span></span>|<span data-ttu-id="491f7-107">0</span><span class="sxs-lookup"><span data-stu-id="491f7-107">0</span></span>|  
|<span data-ttu-id="491f7-108">事件源</span><span class="sxs-lookup"><span data-stu-id="491f7-108">Event Source</span></span>|<span data-ttu-id="491f7-109">0</span><span class="sxs-lookup"><span data-stu-id="491f7-109">0</span></span>|  
|<span data-ttu-id="491f7-110">组件</span><span class="sxs-lookup"><span data-stu-id="491f7-110">Component</span></span>|<span data-ttu-id="491f7-111">0</span><span class="sxs-lookup"><span data-stu-id="491f7-111">0</span></span>|  
|<span data-ttu-id="491f7-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="491f7-112">Symbolic Name</span></span>|<span data-ttu-id="491f7-113">0</span><span class="sxs-lookup"><span data-stu-id="491f7-113">0</span></span>|  
|<span data-ttu-id="491f7-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="491f7-114">Message Text</span></span>|<span data-ttu-id="491f7-115">无法从文件“{0}”导入配置</span><span class="sxs-lookup"><span data-stu-id="491f7-115">Unable to import configuration from file "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="491f7-116">解释</span><span class="sxs-lookup"><span data-stu-id="491f7-116">Explanation</span></span>  
 <span data-ttu-id="491f7-117">此错误可能由多个原因所致：</span><span class="sxs-lookup"><span data-stu-id="491f7-117">There could be multiple reasons for this error:</span></span>  
  
-   <span data-ttu-id="491f7-118">配置文件可能在给定编码中包含无效字符。</span><span class="sxs-lookup"><span data-stu-id="491f7-118">The configuration file may contain invalid character in the given encoding.</span></span>  
  
-   <span data-ttu-id="491f7-119">根元素可能丢失。</span><span class="sxs-lookup"><span data-stu-id="491f7-119">The root element may be missing.</span></span>  
  
-   <span data-ttu-id="491f7-120">根级别的数据可能无效。</span><span class="sxs-lookup"><span data-stu-id="491f7-120">The data at the root level may be invalid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="491f7-121">在这种情况下，用户操作仅适用于 WCF-Custom 和 WCF-CustomIsolate 适配器。</span><span class="sxs-lookup"><span data-stu-id="491f7-121">This situation, and the user action, applies only to WCF-Custom and WCF-CustomIsolate adapters.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="491f7-122">用户操作</span><span class="sxs-lookup"><span data-stu-id="491f7-122">User Action</span></span>  
 <span data-ttu-id="491f7-123">使用以下过程导入有效的配置文件。</span><span class="sxs-lookup"><span data-stu-id="491f7-123">Use the following procedure to import a valid configuration file.</span></span>  
  
#### <a name="to-import-a-valid-configuration-file"></a><span data-ttu-id="491f7-124">导入有效的配置文件</span><span class="sxs-lookup"><span data-stu-id="491f7-124">To import a valid configuration file</span></span>  
  
1.  <span data-ttu-id="491f7-125">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="491f7-125">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="491f7-126">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="491f7-126">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="491f7-127">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="491f7-127">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="491f7-128">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="491f7-128">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="491f7-129">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="491f7-129">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="491f7-130">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="491f7-130">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="491f7-131">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="491f7-131">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="491f7-132">在**WCF [***传输类型***] 传输属性**对话框中，单击**导入/导出**选项卡。</span><span class="sxs-lookup"><span data-stu-id="491f7-132">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Import/Export** tab.</span></span>  
  
9. <span data-ttu-id="491f7-133">单击“导入” 。</span><span class="sxs-lookup"><span data-stu-id="491f7-133">Click **Import**.</span></span> <span data-ttu-id="491f7-134">导入有效且完整的配置文件。</span><span class="sxs-lookup"><span data-stu-id="491f7-134">Import a valid and complete configuration file.</span></span>  
  
 <span data-ttu-id="491f7-135">你还可以通过使用服务配置编辑器中打开它来验证配置文件的有效性**(启动 > 所有程序 > Windows SDK)** （此步骤假定你安装的 Windows SDK。）打开**svcConfigEditor.exe**并验证配置文件的每个属性。</span><span class="sxs-lookup"><span data-stu-id="491f7-135">You can also verify the validity of the configuration file by opening it with the Service Configuration Editor **(Start > All Programs > Windows SDK)** (this step assumes you have the Windows SDK installed.) Open **svcConfigEditor.exe** and verify each property of the configuration file.</span></span>