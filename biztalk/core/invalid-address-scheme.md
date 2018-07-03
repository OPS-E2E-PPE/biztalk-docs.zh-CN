---
title: 无效的地址方案 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 0b059289-654e-40d6-a092-2a685e6e10f7
caps.latest.revision: 17
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 5c9a0e7a9c200d2efc7d0e6e81158379200d55af
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36980998"
---
# <a name="invalid-address-scheme"></a><span data-ttu-id="221bc-102">地址方案无效</span><span class="sxs-lookup"><span data-stu-id="221bc-102">Invalid address scheme</span></span>
## <a name="details"></a><span data-ttu-id="221bc-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="221bc-103">Details</span></span>  
  
|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="221bc-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="221bc-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="221bc-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="221bc-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="221bc-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="221bc-106">Event ID</span></span>     |                                        <span data-ttu-id="221bc-107">000</span><span class="sxs-lookup"><span data-stu-id="221bc-107">000</span></span>                                         |
|  <span data-ttu-id="221bc-108">事件源</span><span class="sxs-lookup"><span data-stu-id="221bc-108">Event Source</span></span>   |                                         <span data-ttu-id="221bc-109">0</span><span class="sxs-lookup"><span data-stu-id="221bc-109">0</span></span>                                          |
|    <span data-ttu-id="221bc-110">组件</span><span class="sxs-lookup"><span data-stu-id="221bc-110">Component</span></span>    |                                         <span data-ttu-id="221bc-111">0</span><span class="sxs-lookup"><span data-stu-id="221bc-111">0</span></span>                                          |
|  <span data-ttu-id="221bc-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="221bc-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="221bc-113">0</span><span class="sxs-lookup"><span data-stu-id="221bc-113">0</span></span>                                          |
|  <span data-ttu-id="221bc-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="221bc-114">Message Text</span></span>   |                  <span data-ttu-id="221bc-115">无效的地址方案;应为"{0}"方案。</span><span class="sxs-lookup"><span data-stu-id="221bc-115">Invalid address scheme; expecting "{0}" scheme.</span></span>                   |
  
## <a name="explanation"></a><span data-ttu-id="221bc-116">解释</span><span class="sxs-lookup"><span data-stu-id="221bc-116">Explanation</span></span>  
 <span data-ttu-id="221bc-117">您提供的协议纲要与传输绑定定义的类型不匹配。</span><span class="sxs-lookup"><span data-stu-id="221bc-117">You provided a protocol scheme that does not match the type defined by your transport binding.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="221bc-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="221bc-118">User Action</span></span>  
 <span data-ttu-id="221bc-119">若要解决此错误，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="221bc-119">To resolve this error, do the following:</span></span>  
  
1. <span data-ttu-id="221bc-120">单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="221bc-120">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  
  
2. <span data-ttu-id="221bc-121">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="221bc-121">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  
  
3. <span data-ttu-id="221bc-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="221bc-122">Locate your application and then locate your transport.</span></span>  
  
4. <span data-ttu-id="221bc-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="221bc-123">Right-click the transport name.</span></span>  
  
5. <span data-ttu-id="221bc-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="221bc-124">Click **Properties**.</span></span>  
  
6. <span data-ttu-id="221bc-125">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="221bc-125">In the port **Type** list, select the correct port.</span></span>  
  
7. <span data-ttu-id="221bc-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="221bc-126">Click **Configure**.</span></span>  
  
8. <span data-ttu-id="221bc-127">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="221bc-127">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  
  
9. <span data-ttu-id="221bc-128">在中**地址 (URI)** 文字框中，确保地址值与正在使用的 WCF 适配器的类型相匹配。</span><span class="sxs-lookup"><span data-stu-id="221bc-128">In the **Address (URI)** text box, ensure that address value matches the type of the WCF adapter that is being used.</span></span>  
  
   <span data-ttu-id="221bc-129">此外，如果使用系统提供的绑定类型使用 Wcf-custom 适配器，检查的值**绑定类型**上列出**绑定**选项卡。如果**绑定类型**配置为**customBinding**，地址应与传输绑定元素中列出匹配**绑定类型**上列表**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="221bc-129">Also, if you use the WCF-Custom adapter with a system-provided binding type, check the value of the **Binding Type** list on the **Binding** tab. If the **Binding Type** is configured to **customBinding**, the address should match the transport binding element listed in the **Binding Type** list on the **Binding** tab.</span></span>