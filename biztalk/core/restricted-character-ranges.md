---
title: 受限制的字符范围 |Microsoft 文档
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: e12213bf-750e-43a2-998a-949fa4255b73
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 74f1399aaa828d5c23c2600ebabeb7063a982447
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/20/2017
ms.locfileid: "22268285"
---
# <a name="restricted-character-ranges"></a><span data-ttu-id="f225b-102">有限的字符范围内</span><span class="sxs-lookup"><span data-stu-id="f225b-102">Restricted Character Ranges</span></span>

## <a name="overview"></a><span data-ttu-id="f225b-103">概述</span><span class="sxs-lookup"><span data-stu-id="f225b-103">Overview</span></span>
<span data-ttu-id="f225b-104">在创建用于平面文件消息的架构时，你可以指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]以阻止特定字符或一系列来自任何传出消息中包含的字符。</span><span class="sxs-lookup"><span data-stu-id="f225b-104">When creating a schema for flat file messages, you can direct [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to block a particular character or a range of characters from being included in any outgoing message.</span></span> <span data-ttu-id="f225b-105">为此，在 BizTalk 编辑器中，打开要用作目标架构的架构。</span><span class="sxs-lookup"><span data-stu-id="f225b-105">To do this, in BizTalk Editor, open a schema that is to be used as a destination schema.</span></span> <span data-ttu-id="f225b-106">选择**架构**节点并使用**受限字符**以打开**受限字符**对话框。</span><span class="sxs-lookup"><span data-stu-id="f225b-106">Select the **Schema** node and the use the **Restricted Characters** property to open the **Restricted Characters** dialog box.</span></span> <span data-ttu-id="f225b-107">输入范围你想要防止在 BizTalk Server 发送的任何消息中包含的字符，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="f225b-107">Enter the character range(s) that you want to prevent being included in any message sent by BizTalk Server, and then click **OK**.</span></span> <span data-ttu-id="f225b-108">每当 BizTalk Server 尝试处理中指定的字符**受限字符**则会生成的目标架构，处理停止点和一条错误消息的对话框。</span><span class="sxs-lookup"><span data-stu-id="f225b-108">Whenever BizTalk Server attempts to process a character specified in the **Restricted Characters** dialog box of a destination schema, processing stops and an error message is generated.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f225b-109">在 BizTalk Server 中，字符范围限制是平面文件扩展的一个功能，因此不适用于 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="f225b-109">In BizTalk Server, character range restriction is a function of the Flat File Extension, and as such, does not apply to XML messages.</span></span> <span data-ttu-id="f225b-110">将来可能为不同类型的消息提供扩展，这些扩展在如何为其支持的消息格式实现字符范围限制方面可能有所不同。</span><span class="sxs-lookup"><span data-stu-id="f225b-110">Extensions that might be offered in the future for different types of messages might differ in how they implement character range restriction for their supported message formats.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f225b-111">另请参阅</span><span class="sxs-lookup"><span data-stu-id="f225b-111">See Also</span></span>  
-  [<span data-ttu-id="f225b-112">注意事项时创建平面文件消息架构</span><span class="sxs-lookup"><span data-stu-id="f225b-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)   
-  <span data-ttu-id="f225b-113">**受限制的字符 (的平面文件架构的节点属性**[!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="f225b-113">**Restricted Characters (Node Property of Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>