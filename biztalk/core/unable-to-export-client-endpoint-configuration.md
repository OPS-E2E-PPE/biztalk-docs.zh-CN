---
title: 无法导出客户端终结点配置 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 2d93fe5e-fdb2-49c5-86de-d428b1ecda7f
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1ce781105c96f12705605e7c97f0e5229d2017f4
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292797"
---
# <a name="unable-to-export-client-endpoint-configuration"></a><span data-ttu-id="79250-102">无法导出客户端终结点配置</span><span class="sxs-lookup"><span data-stu-id="79250-102">Unable to export client endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="79250-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="79250-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="79250-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="79250-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="79250-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="79250-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="79250-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="79250-106">Event ID</span></span>     |                                         <span data-ttu-id="79250-107">0</span><span class="sxs-lookup"><span data-stu-id="79250-107">0</span></span>                                          |
|  <span data-ttu-id="79250-108">事件源</span><span class="sxs-lookup"><span data-stu-id="79250-108">Event Source</span></span>   |                                         <span data-ttu-id="79250-109">0</span><span class="sxs-lookup"><span data-stu-id="79250-109">0</span></span>                                          |
|    <span data-ttu-id="79250-110">组件</span><span class="sxs-lookup"><span data-stu-id="79250-110">Component</span></span>    |                                         <span data-ttu-id="79250-111">0</span><span class="sxs-lookup"><span data-stu-id="79250-111">0</span></span>                                          |
|  <span data-ttu-id="79250-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="79250-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="79250-113">0</span><span class="sxs-lookup"><span data-stu-id="79250-113">0</span></span>                                          |
|  <span data-ttu-id="79250-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="79250-114">Message Text</span></span>   |              <span data-ttu-id="79250-115">无法导出客户端终结点配置为"{0}"</span><span class="sxs-lookup"><span data-stu-id="79250-115">Unable to export client endpoint configuration to "{0}"</span></span>               |
  
## <a name="explanation"></a><span data-ttu-id="79250-116">解释</span><span class="sxs-lookup"><span data-stu-id="79250-116">Explanation</span></span>  
 <span data-ttu-id="79250-117">此错误指示以下值之一：</span><span class="sxs-lookup"><span data-stu-id="79250-117">This error indicates one of the following:</span></span>  
  
-   <span data-ttu-id="79250-118">用户可能没有向目标写入的权限。</span><span class="sxs-lookup"><span data-stu-id="79250-118">The user may not have permission to write to the destination.</span></span>  
  
     <span data-ttu-id="79250-119">\- 或 -</span><span class="sxs-lookup"><span data-stu-id="79250-119">\- OR -</span></span>  
  
-   <span data-ttu-id="79250-120">某些所需的属性未正确指定，如**地址 (URI)** 并**绑定类型**。</span><span class="sxs-lookup"><span data-stu-id="79250-120">Some of the required properties were not correctly specified, such as **Address (URI)** and **Binding Type**.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="79250-121">用户操作</span><span class="sxs-lookup"><span data-stu-id="79250-121">User Action</span></span>  
 <span data-ttu-id="79250-122">使用以下过程来验证用户权限并确认**地址 (URI)** 并**绑定类型**设置是否有效。</span><span class="sxs-lookup"><span data-stu-id="79250-122">Use the following procedure to verify user permissions and confirm **Address (URI)** and **Binding Type** settings are valid.</span></span>  
  
#### <a name="to-verify-user-permissions-and-confirm-settings"></a><span data-ttu-id="79250-123">若要验证用户权限并确认设置</span><span class="sxs-lookup"><span data-stu-id="79250-123">To verify user permissions and confirm settings</span></span>  
  
1. <span data-ttu-id="79250-124">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="79250-124">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="79250-125">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="79250-125">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="79250-126">找到应用程序，并找到你传输。</span><span class="sxs-lookup"><span data-stu-id="79250-126">Locate your application, and then locate your transport.</span></span>  
  
4. <span data-ttu-id="79250-127">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="79250-127">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="79250-128">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="79250-128">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="79250-129">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="79250-129">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="79250-130">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="79250-130">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="79250-131">在 WCF **[**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="79250-131">In the WCF **[**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="79250-132">请确保允许写入到目标文件夹。</span><span class="sxs-lookup"><span data-stu-id="79250-132">Ensure writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="79250-133">检查**行为**选项卡和**终结点标识**中的设置**常规**选项卡，以确保它们有效。</span><span class="sxs-lookup"><span data-stu-id="79250-133">Check the **Behavior** tab and the **Endpoint Identity** settings in **General** tab to ensure they are valid.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="79250-134">必须为的目标文件夹具有写入权限。</span><span class="sxs-lookup"><span data-stu-id="79250-134">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="79250-135">与计算机的管理员联系以获取这些权限。</span><span class="sxs-lookup"><span data-stu-id="79250-135">Contact the administrator of the machine to get these permissions.</span></span>