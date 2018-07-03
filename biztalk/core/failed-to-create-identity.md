---
title: 未能创建标识 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 531f1057-1b6d-40ae-bf2f-a36baf4e0341
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 203257b261bba176b0a768da8242dad45366a923
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36998110"
---
# <a name="failed-to-create-identity"></a><span data-ttu-id="f176d-102">未能创建标识</span><span class="sxs-lookup"><span data-stu-id="f176d-102">Failed to create identity</span></span>
## <a name="details"></a><span data-ttu-id="f176d-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="f176d-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="f176d-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="f176d-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="f176d-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="f176d-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="f176d-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="f176d-106">Event ID</span></span>     |                                         <span data-ttu-id="f176d-107">0</span><span class="sxs-lookup"><span data-stu-id="f176d-107">0</span></span>                                          |
|  <span data-ttu-id="f176d-108">事件源</span><span class="sxs-lookup"><span data-stu-id="f176d-108">Event Source</span></span>   |                                         <span data-ttu-id="f176d-109">0</span><span class="sxs-lookup"><span data-stu-id="f176d-109">0</span></span>                                          |
|    <span data-ttu-id="f176d-110">组件</span><span class="sxs-lookup"><span data-stu-id="f176d-110">Component</span></span>    |                                         <span data-ttu-id="f176d-111">0</span><span class="sxs-lookup"><span data-stu-id="f176d-111">0</span></span>                                          |
|  <span data-ttu-id="f176d-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="f176d-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="f176d-113">0</span><span class="sxs-lookup"><span data-stu-id="f176d-113">0</span></span>                                          |
|  <span data-ttu-id="f176d-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="f176d-114">Message Text</span></span>   |      <span data-ttu-id="f176d-115">此错误表明适配器无法创建终结点标识。</span><span class="sxs-lookup"><span data-stu-id="f176d-115">This error indicates the adapter failed to create the endpoint identity.</span></span>      |

## <a name="explanation"></a><span data-ttu-id="f176d-116">解释</span><span class="sxs-lookup"><span data-stu-id="f176d-116">Explanation</span></span>  
 <span data-ttu-id="f176d-117">此错误表明适配器无法创建终结点标识。</span><span class="sxs-lookup"><span data-stu-id="f176d-117">This error indicates the adapter failed to create the endpoint identity.</span></span>  

## <a name="user-action"></a><span data-ttu-id="f176d-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="f176d-118">User Action</span></span>  
 <span data-ttu-id="f176d-119">使用以下过程配置终结点标识。</span><span class="sxs-lookup"><span data-stu-id="f176d-119">Use the following procedure to configure the endpoint identity.</span></span>  

#### <a name="to-configure-the-endpoint-identity"></a><span data-ttu-id="f176d-120">配置终结点标识的步骤</span><span class="sxs-lookup"><span data-stu-id="f176d-120">To configure the endpoint identity</span></span>  

1. <span data-ttu-id="f176d-121">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="f176d-121">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="f176d-122">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="f176d-122">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="f176d-123">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="f176d-123">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="f176d-124">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="f176d-124">Right-click the transport name.</span></span>  

5. <span data-ttu-id="f176d-125">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="f176d-125">Click **Properties**.</span></span>  

6. <span data-ttu-id="f176d-126">在端口**类型**列表中，选择正确的端口。</span><span class="sxs-lookup"><span data-stu-id="f176d-126">In the port **Type** list, select the correct port.</span></span>  

7. <span data-ttu-id="f176d-127">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="f176d-127">Click **Configure**.</span></span>  

8. <span data-ttu-id="f176d-128">在中**WCF [**<em>传输类型</em>**] 传输属性**对话框中，单击**常规**选项卡。</span><span class="sxs-lookup"><span data-stu-id="f176d-128">In the **WCF [**<em>transport type</em>**] Transport Properties** dialog box, click the **General** tab.</span></span>  

9. <span data-ttu-id="f176d-129">在中**终结点标识**部分中，单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="f176d-129">In the **Endpoint Identity** section, click **Edit**.</span></span>  

10. <span data-ttu-id="f176d-130">在中**标识编辑器**对话框框中，确保设置是否有效。</span><span class="sxs-lookup"><span data-stu-id="f176d-130">In the **Identity Editor** dialog box, ensure that the settings are valid.</span></span>
