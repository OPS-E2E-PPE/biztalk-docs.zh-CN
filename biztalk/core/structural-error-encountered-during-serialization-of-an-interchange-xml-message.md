---
title: 在交换 XML 消息的序列化过程中遇到的结构化错误 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 97939bfd-d1ee-455a-9952-4f25db020e7c
caps.latest.revision: 15
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 44b56cce9fdd3704f7e6ddc2ba5b5bebb62d36e0
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22278589"
---
# <a name="structural-error-encountered-during-serialization-of-an-interchange-xml-message"></a><span data-ttu-id="01034-102">结构化的交换 XML 消息的序列化期间遇到的错误</span><span class="sxs-lookup"><span data-stu-id="01034-102">Structural error encountered during serialization of an interchange XML message</span></span>
## <a name="details"></a><span data-ttu-id="01034-103">详细信息</span><span class="sxs-lookup"><span data-stu-id="01034-103">Details</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="01034-104">产品名称</span><span class="sxs-lookup"><span data-stu-id="01034-104">Product Name</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]|  
|<span data-ttu-id="01034-105">产品版本</span><span class="sxs-lookup"><span data-stu-id="01034-105">Product Version</span></span>|[!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]|  
|<span data-ttu-id="01034-106">事件 ID</span><span class="sxs-lookup"><span data-stu-id="01034-106">Event ID</span></span>|-|  
|<span data-ttu-id="01034-107">事件源</span><span class="sxs-lookup"><span data-stu-id="01034-107">Event Source</span></span>|[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="01034-108"> EDI</span><span class="sxs-lookup"><span data-stu-id="01034-108"> EDI</span></span>|  
|<span data-ttu-id="01034-109">组件</span><span class="sxs-lookup"><span data-stu-id="01034-109">Component</span></span>|<span data-ttu-id="01034-110">EDI 引擎</span><span class="sxs-lookup"><span data-stu-id="01034-110">EDI Engine</span></span>|  
|<span data-ttu-id="01034-111">符号名称</span><span class="sxs-lookup"><span data-stu-id="01034-111">Symbolic Name</span></span>|<span data-ttu-id="01034-112">InvalidXmlNodeFound</span><span class="sxs-lookup"><span data-stu-id="01034-112">InvalidXmlNodeFound</span></span>|  
|<span data-ttu-id="01034-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="01034-113">Message Text</span></span>|<span data-ttu-id="01034-114">交换 XML 消息序列化期间遇到结构错误</span><span class="sxs-lookup"><span data-stu-id="01034-114">Structural error encountered during serialization of an Interchange Xml message</span></span>|  
  
## <a name="explanation"></a><span data-ttu-id="01034-115">解释</span><span class="sxs-lookup"><span data-stu-id="01034-115">Explanation</span></span>  
 <span data-ttu-id="01034-116">此错误表明在交换 XML 消息的序列化期间遇到结构错误。</span><span class="sxs-lookup"><span data-stu-id="01034-116">This error indicates that a structural error was encountered during serialization of an interchange XML message.</span></span> <span data-ttu-id="01034-117">BTS 查找 XML StartElement 或 EndElement，但遇到另一个 XML 节点类型。</span><span class="sxs-lookup"><span data-stu-id="01034-117">BTS was looking for an XML StartElement or EndElement but instead a different XML node type was encountered.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="01034-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="01034-118">User Action</span></span>  
 <span data-ttu-id="01034-119">若要解决此错误，请确保消息结构正确，然后重试：</span><span class="sxs-lookup"><span data-stu-id="01034-119">To resolve this error, make sure the message structure is correct, and try again:</span></span>  
  
1.  <span data-ttu-id="01034-120">单击**启动**，单击**所有程序**，单击[!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)]，然后单击**BizTalk Server 管理**。</span><span class="sxs-lookup"><span data-stu-id="01034-120">Click **Start**, click **All Programs**, click [!INCLUDE[btsBizTalkServerStartMenuItemui](../includes/btsbiztalkserverstartmenuitemui-md.md)], and then click **BizTalk Server Administration**.</span></span>  
  
2.  <span data-ttu-id="01034-121">在控制台根目录中，展开[!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)]，然后单击**BizTalk 组**。</span><span class="sxs-lookup"><span data-stu-id="01034-121">In the Console Root, expand [!INCLUDE[btsBizTalkServerAdminConsoleui](../includes/btsbiztalkserveradminconsoleui-md.md)], and click **BizTalk Group**.</span></span>  
  
3.  <span data-ttu-id="01034-122">在右窗格中，单击**组中心数据库**选项卡。</span><span class="sxs-lookup"><span data-stu-id="01034-122">In the right pane, click the **Group Hub** tab.</span></span>  
  
4.  <span data-ttu-id="01034-123">单击**挂起的服务实例**。</span><span class="sxs-lookup"><span data-stu-id="01034-123">Click **Suspended Service instances**.</span></span>  
  
5.  <span data-ttu-id="01034-124">双击该消息。</span><span class="sxs-lookup"><span data-stu-id="01034-124">Double-click the message.</span></span>  
  
6.  <span data-ttu-id="01034-125">在**服务详细信息**窗口中，单击**消息**选项卡。</span><span class="sxs-lookup"><span data-stu-id="01034-125">In the **Service Details** window, click the **Messages** tab.</span></span>  
  
7.  <span data-ttu-id="01034-126">再次双击该消息。</span><span class="sxs-lookup"><span data-stu-id="01034-126">Double-click the message again.</span></span>  
  
8.  <span data-ttu-id="01034-127">在左窗格中，单击**消息部分 / b o**。</span><span class="sxs-lookup"><span data-stu-id="01034-127">In the left pane, click **Message Parts / Body**.</span></span>  
  
9. <span data-ttu-id="01034-128">确定消息结构是否正确。</span><span class="sxs-lookup"><span data-stu-id="01034-128">Determine if the message structure is correct.</span></span>