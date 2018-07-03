---
title: 不支持的安全算法套件 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 11696fed-c3a8-4b11-8249-9f99f7abc8f2
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 32b00fea76b95a76cbb6b88f18056bba798e1381
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "36990982"
---
# <a name="unsupported-security-algorithm-suite"></a><span data-ttu-id="9ebf0-102">不支持的安全算法套件</span><span class="sxs-lookup"><span data-stu-id="9ebf0-102">Unsupported security algorithm suite</span></span>
## <a name="details"></a><span data-ttu-id="9ebf0-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="9ebf0-103">Details</span></span>  

|                 |                                                                                    |
|-----------------|------------------------------------------------------------------------------------|
|  <span data-ttu-id="9ebf0-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="9ebf0-104">Product Name</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] |
| <span data-ttu-id="9ebf0-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="9ebf0-105">Product Version</span></span> |             [!INCLUDE[btsWCFVersion](../includes/btswcfversion-md.md)]             |
|    <span data-ttu-id="9ebf0-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="9ebf0-106">Event ID</span></span>     |                                         <span data-ttu-id="9ebf0-107">0</span><span class="sxs-lookup"><span data-stu-id="9ebf0-107">0</span></span>                                          |
|  <span data-ttu-id="9ebf0-108">事件源</span><span class="sxs-lookup"><span data-stu-id="9ebf0-108">Event Source</span></span>   |                                         <span data-ttu-id="9ebf0-109">0</span><span class="sxs-lookup"><span data-stu-id="9ebf0-109">0</span></span>                                          |
|    <span data-ttu-id="9ebf0-110">组件</span><span class="sxs-lookup"><span data-stu-id="9ebf0-110">Component</span></span>    |                                         <span data-ttu-id="9ebf0-111">0</span><span class="sxs-lookup"><span data-stu-id="9ebf0-111">0</span></span>                                          |
|  <span data-ttu-id="9ebf0-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="9ebf0-112">Symbolic Name</span></span>  |                                         <span data-ttu-id="9ebf0-113">0</span><span class="sxs-lookup"><span data-stu-id="9ebf0-113">0</span></span>                                          |
|  <span data-ttu-id="9ebf0-114">消息正文</span><span class="sxs-lookup"><span data-stu-id="9ebf0-114">Message Text</span></span>   |                     <span data-ttu-id="9ebf0-115">不支持的安全算法套件： {0}</span><span class="sxs-lookup"><span data-stu-id="9ebf0-115">Unsupported security algorithm suite: {0}</span></span>                      |

## <a name="explanation"></a><span data-ttu-id="9ebf0-116">解释</span><span class="sxs-lookup"><span data-stu-id="9ebf0-116">Explanation</span></span>  
 <span data-ttu-id="9ebf0-117">如果接收位置或发送端口的安全算法套件属性设置为不正确的值，则发生此错误。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-117">This error occurs when the security algorithm suite property of a receive location or send port is set to an incorrect value.</span></span>  

## <a name="user-action"></a><span data-ttu-id="9ebf0-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="9ebf0-118">User Action</span></span>  
 <span data-ttu-id="9ebf0-119">确保事务协议属性设置为有效值。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-119">Ensure that transaction protocol property is set to a valid value.</span></span>  

1. <span data-ttu-id="9ebf0-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="9ebf0-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后展开**应用程序**。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and expand  **Applications**.</span></span>  

3. <span data-ttu-id="9ebf0-122">找到你的应用程序，然后找到您的传输。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-122">Locate your application and then locate your transport.</span></span>  

4. <span data-ttu-id="9ebf0-123">右键单击传输名称。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-123">Right-click the transport name.</span></span>  

5. <span data-ttu-id="9ebf0-124">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-124">Click **Properties**.</span></span>  

6. <span data-ttu-id="9ebf0-125">在端口**类型**列表中，选择**WCF NetTcp**。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-125">In the port **Type** list, select **WCF-NetTcp**.</span></span>  

7. <span data-ttu-id="9ebf0-126">单击**配置**。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-126">Click **Configure**.</span></span>  

8. <span data-ttu-id="9ebf0-127">在中**Wcf-nettcp 传输属性**对话框中，单击**安全**选项卡。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-127">In the **WCF-NetTcp Transport Properties** dialog box, click the **Security** tab.</span></span>  

9. <span data-ttu-id="9ebf0-128">在中**消息安全**部分中，确保为值**算法套件**正确无误。</span><span class="sxs-lookup"><span data-stu-id="9ebf0-128">In the **Message security** section, ensure that the values for **Algorithm suite** are correct.</span></span>
