---
title: 受限字符范围 |Microsoft Docs
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
ms.openlocfilehash: add7cfdf529d21c7ed54ae60d1c39c39266af6fb
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65255111"
---
# <a name="restricted-character-ranges"></a><span data-ttu-id="6f9bb-102">受限的字符范围</span><span class="sxs-lookup"><span data-stu-id="6f9bb-102">Restricted Character Ranges</span></span>

## <a name="overview"></a><span data-ttu-id="6f9bb-103">概述</span><span class="sxs-lookup"><span data-stu-id="6f9bb-103">Overview</span></span>
<span data-ttu-id="6f9bb-104">创建平面文件消息架构时，你可以指示[!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]来阻止特定字符或一系列在任何传出消息中包含的字符。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-104">When creating a schema for flat file messages, you can direct [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] to block a particular character or a range of characters from being included in any outgoing message.</span></span> <span data-ttu-id="6f9bb-105">若要执行此操作，请在 BizTalk 编辑器中，打开要用作目标架构的架构。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-105">To do this, in BizTalk Editor, open a schema that is to be used as a destination schema.</span></span> <span data-ttu-id="6f9bb-106">选择**架构**节点，然后使用**受限字符**以打开**受限字符**对话框。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-106">Select the **Schema** node and the use the **Restricted Characters** property to open the **Restricted Characters** dialog box.</span></span> <span data-ttu-id="6f9bb-107">输入范围，你想要防止在 BizTalk Server 发送的任何消息中包含的字符，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-107">Enter the character range(s) that you want to prevent being included in any message sent by BizTalk Server, and then click **OK**.</span></span> <span data-ttu-id="6f9bb-108">只要 BizTalk Server 尝试处理中指定的字符**受限字符**生成的目标架构，处理将停止一条错误消息的对话框。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-108">Whenever BizTalk Server attempts to process a character specified in the **Restricted Characters** dialog box of a destination schema, processing stops and an error message is generated.</span></span>  

> [!NOTE]
>  <span data-ttu-id="6f9bb-109">在 BizTalk Server 中，字符范围限制是平面文件扩展的函数，在这种情况下，不适用于 XML 消息。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-109">In BizTalk Server, character range restriction is a function of the Flat File Extension, and as such, does not apply to XML messages.</span></span> <span data-ttu-id="6f9bb-110">有关不同类型的消息可能在实现字符范围限制为其支持的消息格式的方式不同可能在将来提供的扩展。</span><span class="sxs-lookup"><span data-stu-id="6f9bb-110">Extensions that might be offered in the future for different types of messages might differ in how they implement character range restriction for their supported message formats.</span></span>  

## <a name="see-also"></a><span data-ttu-id="6f9bb-111">请参阅</span><span class="sxs-lookup"><span data-stu-id="6f9bb-111">See Also</span></span>  
- [<span data-ttu-id="6f9bb-112">创建平面文件消息架构时的注意事项</span><span class="sxs-lookup"><span data-stu-id="6f9bb-112">Considerations When Creating Flat File Message Schemas</span></span>](../core/considerations-when-creating-flat-file-message-schemas.md)   
- <span data-ttu-id="6f9bb-113">**受限的字符 （平面文件架构的节点属性** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span><span class="sxs-lookup"><span data-stu-id="6f9bb-113">**Restricted Characters (Node Property of Flat File Schemas** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)]</span></span>
