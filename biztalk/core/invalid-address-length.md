---
title: 地址长度无效 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e8e16eb6-e77e-4361-ac91-0730004c4433
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8da5e041ad861557817491695f0d7972a207864a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008470"
---
# <a name="invalid-address-length"></a><span data-ttu-id="3e0d3-102">地址长度无效</span><span class="sxs-lookup"><span data-stu-id="3e0d3-102">Invalid address length</span></span>
## <a name="details"></a><span data-ttu-id="3e0d3-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="3e0d3-103">Details</span></span>  

|                 |                                                                                             |
|-----------------|---------------------------------------------------------------------------------------------|
|  <span data-ttu-id="3e0d3-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="3e0d3-104">Product Name</span></span>   |     [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]      |
| <span data-ttu-id="3e0d3-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="3e0d3-105">Product Version</span></span> |                 [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]                  |
|    <span data-ttu-id="3e0d3-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="3e0d3-106">Event ID</span></span>     |                                              <span data-ttu-id="3e0d3-107">0</span><span class="sxs-lookup"><span data-stu-id="3e0d3-107">0</span></span>                                              |
|  <span data-ttu-id="3e0d3-108">事件源</span><span class="sxs-lookup"><span data-stu-id="3e0d3-108">Event Source</span></span>   |                                              <span data-ttu-id="3e0d3-109">0</span><span class="sxs-lookup"><span data-stu-id="3e0d3-109">0</span></span>                                              |
|    <span data-ttu-id="3e0d3-110">组件</span><span class="sxs-lookup"><span data-stu-id="3e0d3-110">Component</span></span>    |                                              <span data-ttu-id="3e0d3-111">0</span><span class="sxs-lookup"><span data-stu-id="3e0d3-111">0</span></span>                                              |
|  <span data-ttu-id="3e0d3-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="3e0d3-112">Symbolic Name</span></span>  |                                              <span data-ttu-id="3e0d3-113">0</span><span class="sxs-lookup"><span data-stu-id="3e0d3-113">0</span></span>                                              |
|  <span data-ttu-id="3e0d3-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="3e0d3-114">Message Text</span></span>   | <span data-ttu-id="3e0d3-115">地址长度无效;指定的地址长度为{0}字符，限制是{1}字符</span><span class="sxs-lookup"><span data-stu-id="3e0d3-115">Invalid address length; specified address length is {0} characters, limit is {1} characters</span></span> |

## <a name="explanation"></a><span data-ttu-id="3e0d3-116">解释</span><span class="sxs-lookup"><span data-stu-id="3e0d3-116">Explanation</span></span>  
 <span data-ttu-id="3e0d3-117">为 WCF 传输提供的地址超出 255 个字符的最大长度。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-117">You provided an address that exceeds the maximum length of 255 characters for a WCF transport.</span></span> <span data-ttu-id="3e0d3-118">这是 BizTalk Server（而不是 WCF）规定的限制。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-118">This is a limitation imposed by BizTalk Server, not by WCF.</span></span>  

## <a name="user-action"></a><span data-ttu-id="3e0d3-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="3e0d3-119">User Action</span></span>  
 <span data-ttu-id="3e0d3-120">使用以下过程配置有效地址。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-120">Use the following procedure to configure a valid address.</span></span>  

#### <a name="to-configure-a-valid-address"></a><span data-ttu-id="3e0d3-121">配置有效地址</span><span class="sxs-lookup"><span data-stu-id="3e0d3-121">To configure a valid address</span></span>  

1. <span data-ttu-id="3e0d3-122">单击**启动**，单击**所有程序**，单击**Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]** ，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-122">Click **Start**, click **All Programs**, click **Microsoft [!INCLUDE[btsBizTalkServer2006r3ui](../includes/btsbiztalkserver2006r3ui-md.md)]**, and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="3e0d3-123">在控制台根目录中，展开**BizTalk Server 管理**，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-123">In the Console Root, expand  **BizTalk Server Administration**, expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="3e0d3-124">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-124">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="3e0d3-125">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-125">Right-click the transport name.</span></span>  

5. <span data-ttu-id="3e0d3-126">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-126">Click **Properties**.</span></span>  

6. <span data-ttu-id="3e0d3-127">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-127">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="3e0d3-128">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-128">Click **Configure**.</span></span>  

8. <span data-ttu-id="3e0d3-129">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-129">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="3e0d3-130">在中**地址 (URI)** 文字框中，确保地址不超过 255 个字符的最大长度。</span><span class="sxs-lookup"><span data-stu-id="3e0d3-130">In the **Address (URI)** text box, ensure the address does not exceed the maximum length of 255 characters.</span></span>
