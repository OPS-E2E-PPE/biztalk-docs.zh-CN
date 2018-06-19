---
title: 无效的绑定 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 3e851f7f-ffc8-4f55-b06e-501a7f41b32a
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2e5733df4d4d7d6ef9e70e6a2a16302cc19ac5d9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257517"
---
# <a name="invalid-binding"></a><span data-ttu-id="5105d-102">绑定无效</span><span class="sxs-lookup"><span data-stu-id="5105d-102">Invalid binding</span></span>
## <a name="details"></a><span data-ttu-id="5105d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="5105d-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="5105d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="5105d-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="5105d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="5105d-105">Product Version</span></span>|[!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]|  
|<span data-ttu-id="5105d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="5105d-106">Event ID</span></span>|<span data-ttu-id="5105d-107">0</span><span class="sxs-lookup"><span data-stu-id="5105d-107">0</span></span>|  
|<span data-ttu-id="5105d-108">事件源</span><span class="sxs-lookup"><span data-stu-id="5105d-108">Event Source</span></span>|<span data-ttu-id="5105d-109">0</span><span class="sxs-lookup"><span data-stu-id="5105d-109">0</span></span>|  
|<span data-ttu-id="5105d-110">组件</span><span class="sxs-lookup"><span data-stu-id="5105d-110">Component</span></span>|<span data-ttu-id="5105d-111">0</span><span class="sxs-lookup"><span data-stu-id="5105d-111">0</span></span>|  
|<span data-ttu-id="5105d-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="5105d-112">Symbolic Name</span></span>|<span data-ttu-id="5105d-113">0</span><span class="sxs-lookup"><span data-stu-id="5105d-113">0</span></span>|  
|<span data-ttu-id="5105d-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="5105d-114">Message Text</span></span>|<span data-ttu-id="5105d-115">绑定无效</span><span class="sxs-lookup"><span data-stu-id="5105d-115">Invalid binding</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="5105d-116">解释</span><span class="sxs-lookup"><span data-stu-id="5105d-116">Explanation</span></span>  
 <span data-ttu-id="5105d-117">此错误表示适配器无法创建接收位置的绑定配置中指定的绑定或发送端口。</span><span class="sxs-lookup"><span data-stu-id="5105d-117">This error indicates the adapter cannot create the binding specified in the binding configuration of the receive location or send port.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="5105d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="5105d-118">User Action</span></span>  
 <span data-ttu-id="5105d-119">使用以下过程验证绑定元素。</span><span class="sxs-lookup"><span data-stu-id="5105d-119">Use the following procedure to verify binding elements.</span></span>  
  
#### <a name="to-verify-binding-elements"></a><span data-ttu-id="5105d-120">若要验证绑定元素</span><span class="sxs-lookup"><span data-stu-id="5105d-120">To verify binding elements</span></span>  
  
1.  <span data-ttu-id="5105d-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="5105d-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="5105d-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="5105d-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3.  <span data-ttu-id="5105d-123">找到应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="5105d-123">Locate your application and then locate your transport.</span></span>  
  
4.  <span data-ttu-id="5105d-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="5105d-124">Right-click the transport name.</span></span>  
  
5.  <span data-ttu-id="5105d-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="5105d-125">Click **Properties**.</span></span>  
  
6.  <span data-ttu-id="5105d-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="5105d-126">In the port **Type** list, select the correct port.</span></span>  
  
7.  <span data-ttu-id="5105d-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="5105d-127">Click **Configure**.</span></span>  
  
8.  <span data-ttu-id="5105d-128">在**WCF [***传输类型***] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="5105d-128">In the **WCF [***transport type***] Transport Properties** dialog box, click the **Binding** tab.</span></span>  
  
9. <span data-ttu-id="5105d-129">确保配置中指定的绑定元素都有效。</span><span class="sxs-lookup"><span data-stu-id="5105d-129">Ensure the binding elements specified in the configuration are valid.</span></span>