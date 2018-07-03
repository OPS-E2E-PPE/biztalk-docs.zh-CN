---
title: 处理压缩的 AS2 消息时解压缩失败。 | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 5246ee97-cc60-4878-9447-de870c0f4c34
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: c77bead00b97bf6fa072223485f2d1cc422053b7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/27/2018
ms.locfileid: "37001886"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a><span data-ttu-id="8935a-103">处理压缩的 AS2 消息时解压缩失败。</span><span class="sxs-lookup"><span data-stu-id="8935a-103">Decompression failed while processing a compressed AS2 message.</span></span>
## <a name="details"></a><span data-ttu-id="8935a-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="8935a-104">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="8935a-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="8935a-105">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="8935a-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="8935a-106">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="8935a-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="8935a-107">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="8935a-108">事件源</span><span class="sxs-lookup"><span data-stu-id="8935a-108">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]<span data-ttu-id="8935a-109"> EDI</span><span class="sxs-lookup"><span data-stu-id="8935a-109"> EDI</span></span> |
|    <span data-ttu-id="8935a-110">组件</span><span class="sxs-lookup"><span data-stu-id="8935a-110">Component</span></span>    |                                       <span data-ttu-id="8935a-111">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="8935a-111">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="8935a-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="8935a-112">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="8935a-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="8935a-113">Message Text</span></span>   |       <span data-ttu-id="8935a-114">处理压缩的 AS2 消息时解压缩失败。</span><span class="sxs-lookup"><span data-stu-id="8935a-114">Decompression failed while processing a compressed AS2 message.</span></span> <span data-ttu-id="8935a-115">错误：{0}</span><span class="sxs-lookup"><span data-stu-id="8935a-115">Error: {0}</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="8935a-116">解释</span><span class="sxs-lookup"><span data-stu-id="8935a-116">Explanation</span></span>  
 <span data-ttu-id="8935a-117">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解压缩 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="8935a-117">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decompress the AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="8935a-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="8935a-118">User Action</span></span>  
 <span data-ttu-id="8935a-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="8935a-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="8935a-120">验证 AS2 消息中的压缩包装是否有效。</span><span class="sxs-lookup"><span data-stu-id="8935a-120">Verify that the compression wrapper in the AS2 message is valid.</span></span>  
  
-   <span data-ttu-id="8935a-121">验证是否为 BizTalk Server 启用了解压缩，方法是验证“AS2 属性”对话框的“作为 AS2 消息发送方的参与方”页上是否选中了“应对消息进行压缩”属性（如果选中了“替代入站消息属性”属性）。</span><span class="sxs-lookup"><span data-stu-id="8935a-121">Verify that decompression is enabled for BizTalk Server by verifying that the "Message should be compressed" property is checked on the Party as AS2 Message Sender page of the AS2 Properties dialog box (if the Override inbound message properties property is checked).</span></span>  
  
-   <span data-ttu-id="8935a-122">使用错误消息文本中提供的错误说明来确定具体问题。</span><span class="sxs-lookup"><span data-stu-id="8935a-122">Use the error description provided in the error message text to identify the specific issue.</span></span>