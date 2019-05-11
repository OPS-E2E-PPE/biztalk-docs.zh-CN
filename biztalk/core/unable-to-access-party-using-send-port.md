---
title: 无法访问方使用发送端口 |Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ffacba77-76e8-4f03-be26-134a9999d6c1
caps.latest.revision: 16
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 64b31650411fcdfdf3aaba70f3e25ee377d442cb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65292842"
---
# <a name="unable-to-access-party-using-send-port"></a><span data-ttu-id="49c5c-102">无法访问方使用发送端口</span><span class="sxs-lookup"><span data-stu-id="49c5c-102">Unable to access party using send port</span></span>
## <a name="details"></a><span data-ttu-id="49c5c-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="49c5c-103">Details</span></span>  

|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="49c5c-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="49c5c-104">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="49c5c-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="49c5c-105">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="49c5c-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="49c5c-106">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="49c5c-107">事件源</span><span class="sxs-lookup"><span data-stu-id="49c5c-107">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="49c5c-108">EDI</span><span class="sxs-lookup"><span data-stu-id="49c5c-108">EDI</span></span> |
|    <span data-ttu-id="49c5c-109">组件</span><span class="sxs-lookup"><span data-stu-id="49c5c-109">Component</span></span>    |                                       <span data-ttu-id="49c5c-110">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="49c5c-110">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="49c5c-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="49c5c-111">Symbolic Name</span></span>  |                       <span data-ttu-id="49c5c-112">UnableToLocateAS2PartyBySendPortNameError</span><span class="sxs-lookup"><span data-stu-id="49c5c-112">UnableToLocateAS2PartyBySendPortNameError</span></span>                        |
|  <span data-ttu-id="49c5c-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="49c5c-113">Message Text</span></span>   |                      <span data-ttu-id="49c5c-114">无法访问方使用发送端口： {0}</span><span class="sxs-lookup"><span data-stu-id="49c5c-114">Unable to access party using send port: {0}</span></span>                       |

## <a name="explanation"></a><span data-ttu-id="49c5c-115">解释</span><span class="sxs-lookup"><span data-stu-id="49c5c-115">Explanation</span></span>  
 <span data-ttu-id="49c5c-116">此错误表明发送管道找不到具有指定关联的参与方发送传出 AS2 消息的端口。</span><span class="sxs-lookup"><span data-stu-id="49c5c-116">This error indicates the send pipeline could not find a party associated with the specified send port for the outgoing AS2 message.</span></span>  

## <a name="user-action"></a><span data-ttu-id="49c5c-117">用户操作</span><span class="sxs-lookup"><span data-stu-id="49c5c-117">User Action</span></span>  
 <span data-ttu-id="49c5c-118">若要解决此错误，将与指定的发送端口关联参与方：</span><span class="sxs-lookup"><span data-stu-id="49c5c-118">To resolve this error, associate a party with the specified send port:</span></span>  

1. <span data-ttu-id="49c5c-119">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="49c5c-119">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  

2. <span data-ttu-id="49c5c-120">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，展开**BizTalk 组**，然后单击**方**。</span><span class="sxs-lookup"><span data-stu-id="49c5c-120">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], expand **BizTalk Group**, and click **Parties**.</span></span>  

3. <span data-ttu-id="49c5c-121">右键单击正确的参与方。</span><span class="sxs-lookup"><span data-stu-id="49c5c-121">Right-click the correct party.</span></span>  

4. <span data-ttu-id="49c5c-122">单击 **“属性”**。</span><span class="sxs-lookup"><span data-stu-id="49c5c-122">Click **Properties**.</span></span>  

5. <span data-ttu-id="49c5c-123">在 [*参与方名称*]**参与方属性**对话框中，在左窗格中，单击**发送端口**。</span><span class="sxs-lookup"><span data-stu-id="49c5c-123">In the [*party name*] **Party Properties** dialog box, in the left pane, click **Send Ports**.</span></span>  

6. <span data-ttu-id="49c5c-124">输入中的发送端口名称**发送端口**列表。</span><span class="sxs-lookup"><span data-stu-id="49c5c-124">Enter the Send port name in the **Send Ports** list.</span></span>  

7. <span data-ttu-id="49c5c-125">单击“确定” 。</span><span class="sxs-lookup"><span data-stu-id="49c5c-125">Click **OK**.</span></span>
