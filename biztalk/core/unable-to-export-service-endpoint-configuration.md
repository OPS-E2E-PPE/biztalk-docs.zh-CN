---
title: 无法导出服务终结点配置 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 795145fa-0ce4-498f-a82e-eb752a5f4764
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c3b36fa47d9302f3f88f65575bfa8f74c6469e9e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22286877"
---
# <a name="unable-to-export-service-endpoint-configuration"></a><span data-ttu-id="82597-102">无法导出服务终结点配置</span><span class="sxs-lookup"><span data-stu-id="82597-102">Unable to export service endpoint configuration</span></span>
## <a name="details"></a><span data-ttu-id="82597-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="82597-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="82597-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="82597-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="82597-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="82597-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="82597-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="82597-106">Event ID</span></span>|<span data-ttu-id="82597-107">0</span><span class="sxs-lookup"><span data-stu-id="82597-107">0</span></span>|  
|<span data-ttu-id="82597-108">事件源</span><span class="sxs-lookup"><span data-stu-id="82597-108">Event Source</span></span>|<span data-ttu-id="82597-109">0</span><span class="sxs-lookup"><span data-stu-id="82597-109">0</span></span>|  
|<span data-ttu-id="82597-110">组件</span><span class="sxs-lookup"><span data-stu-id="82597-110">Component</span></span>|<span data-ttu-id="82597-111">0</span><span class="sxs-lookup"><span data-stu-id="82597-111">0</span></span>|  
|<span data-ttu-id="82597-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="82597-112">Symbolic Name</span></span>|<span data-ttu-id="82597-113">0</span><span class="sxs-lookup"><span data-stu-id="82597-113">0</span></span>|  
|<span data-ttu-id="82597-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="82597-114">Message Text</span></span>|<span data-ttu-id="82597-115">无法将服务终结点配置导出到“{0}”</span><span class="sxs-lookup"><span data-stu-id="82597-115">Unable to export service endpoint configuration to "{0}"</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="82597-116">解释</span><span class="sxs-lookup"><span data-stu-id="82597-116">Explanation</span></span>  
 <span data-ttu-id="82597-117">此错误表示用户可能没有向目标写入数据的权限。</span><span class="sxs-lookup"><span data-stu-id="82597-117">This error indicates the user may not have permission to write to the destination.</span></span> <span data-ttu-id="82597-118">或者，未正确指定某些所需的属性，例如“地址(URI)”和“绑定类型”。</span><span class="sxs-lookup"><span data-stu-id="82597-118">Or some of the required properties were not correctly specified, such as Address (URI), and Binding Type.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="82597-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="82597-119">User Action</span></span>  
 <span data-ttu-id="82597-120">使用以下过程配置终结点标识。</span><span class="sxs-lookup"><span data-stu-id="82597-120">Use the following procedure to configure the endpoint identity.</span></span>  
  
#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="82597-121">配置终结点标识的步骤</span><span class="sxs-lookup"><span data-stu-id="82597-121">To configure the endpoint identity</span></span>  
  
1.  <span data-ttu-id="82597-122">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="82597-122">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="82597-123">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="82597-123">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="82597-124">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="82597-124">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="82597-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="82597-125">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="82597-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="82597-126">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="82597-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="82597-127">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="82597-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="82597-128">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="82597-129">在 WCF **[***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="82597-129">In the WCF **[***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="82597-130">确保允许向目标文件夹写入数据。</span><span class="sxs-lookup"><span data-stu-id="82597-130">Ensure that writing to the destination folder is permitted.</span></span>  
  
10. <span data-ttu-id="82597-131">检查**行为**选项卡和**终结点标识**中的设置**常规**选项卡，以确保它们都有效。</span><span class="sxs-lookup"><span data-stu-id="82597-131">Check the **Behavior** tab and the **Endpoint Identity** settings in the **General** tab to ensure they are valid.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="82597-132">您必须对目标文件夹拥有写入权限。</span><span class="sxs-lookup"><span data-stu-id="82597-132">You must have write permissions to the destination folder.</span></span> <span data-ttu-id="82597-133">联系计算机管理员获取这些权限。</span><span class="sxs-lookup"><span data-stu-id="82597-133">Contact the administrator of the machine to get these permissions.</span></span>