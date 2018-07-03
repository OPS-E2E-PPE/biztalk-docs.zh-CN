---
title: 事务性请求响应接收位置不支持 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6c89b619-280c-4ab5-b6aa-06b14a075f8e
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ddcc173a751fb104e86047f3f2e59be8524f7ab9
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022723"
---
# <a name="transactional-request-response-receive-location-is-not-supported"></a><span data-ttu-id="d452c-102">不支持事务性请求响应接收位置</span><span class="sxs-lookup"><span data-stu-id="d452c-102">Transactional request-response receive location is not supported</span></span>
## <a name="details"></a><span data-ttu-id="d452c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="d452c-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="d452c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="d452c-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="d452c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="d452c-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="d452c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="d452c-106">Event ID</span></span>     |                                         <span data-ttu-id="d452c-107">0</span><span class="sxs-lookup"><span data-stu-id="d452c-107">0</span></span>                                          |
|  <span data-ttu-id="d452c-108">事件源</span><span class="sxs-lookup"><span data-stu-id="d452c-108">Event Source</span></span>   |                                         <span data-ttu-id="d452c-109">0</span><span class="sxs-lookup"><span data-stu-id="d452c-109">0</span></span>                                          |
|    <span data-ttu-id="d452c-110">组件</span><span class="sxs-lookup"><span data-stu-id="d452c-110">Component</span></span>    |                                         <span data-ttu-id="d452c-111">0</span><span class="sxs-lookup"><span data-stu-id="d452c-111">0</span></span>                                          |
|  <span data-ttu-id="d452c-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="d452c-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="d452c-113">0</span><span class="sxs-lookup"><span data-stu-id="d452c-113">0</span></span>                                          |
|  <span data-ttu-id="d452c-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="d452c-114">Message Text</span></span>   |         <span data-ttu-id="d452c-115">事务性请求响应接收位置不受支持。</span><span class="sxs-lookup"><span data-stu-id="d452c-115">Transactional request-response receive location is not supported.</span></span>          |

## <a name="explanation"></a><span data-ttu-id="d452c-116">解释</span><span class="sxs-lookup"><span data-stu-id="d452c-116">Explanation</span></span>  
 <span data-ttu-id="d452c-117">此错误表示已将事务设置为对 WCF 请求响应接收位置启用。</span><span class="sxs-lookup"><span data-stu-id="d452c-117">This error indicates that the transaction was set to be enabled for a WCF request-response receive location.</span></span> <span data-ttu-id="d452c-118">由于 MessageBox 数据库，在 BizTalk 中，请求响应接收位置不支持事务。</span><span class="sxs-lookup"><span data-stu-id="d452c-118">Transactions are not supported in BizTalk for a request-response receive location due to the message box database.</span></span>  

## <a name="user-action"></a><span data-ttu-id="d452c-119">用户操作</span><span class="sxs-lookup"><span data-stu-id="d452c-119">User Action</span></span>  
 <span data-ttu-id="d452c-120">对于标准的 WCF 适配器，请转到配置请求响应接收位置的代码。</span><span class="sxs-lookup"><span data-stu-id="d452c-120">For the standard WCF adapters, go to the code configuring the request-response receive location.</span></span> <span data-ttu-id="d452c-121">絋粄**EnableTransaction**中的 XML 数据元素**TransportTypeData**属性**ITransportInfo**界面被设置为**False**.</span><span class="sxs-lookup"><span data-stu-id="d452c-121">Ensure that the **EnableTransaction** element in the XML data for the **TransportTypeData** property of the **ITransportInfo** interface is set to **False**.</span></span>  

 <span data-ttu-id="d452c-122">对于 WCF-Custom 适配器：</span><span class="sxs-lookup"><span data-stu-id="d452c-122">For the WCF-Custom adapters:</span></span>  

1. <span data-ttu-id="d452c-123">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="d452c-123">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="d452c-124">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="d452c-124">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand **Applications**.</span></span>  

3. <span data-ttu-id="d452c-125">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="d452c-125">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="d452c-126">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="d452c-126">Right-click the transport name.</span></span>  

5. <span data-ttu-id="d452c-127">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="d452c-127">Click **Properties**.</span></span>  

6. <span data-ttu-id="d452c-128">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="d452c-128">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="d452c-129">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="d452c-129">Click **Configure**.</span></span>  

8. <span data-ttu-id="d452c-130">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**绑定**选项卡。</span><span class="sxs-lookup"><span data-stu-id="d452c-130">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **Binding** tab.</span></span>  

9. <span data-ttu-id="d452c-131">确保 transactionFlow 属性设置为**False**。</span><span class="sxs-lookup"><span data-stu-id="d452c-131">Ensure that the transactionFlow property is set to **False**.</span></span>
