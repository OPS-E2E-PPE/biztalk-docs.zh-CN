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
ms.openlocfilehash: 424dded28973b2e113c959eacd9141fbaf2fb95d
ms.sourcegitcommit: 381e83d43796a345488d54b3f7413e11d56ad7be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2019
ms.locfileid: "65390297"
---
# <a name="decompression-failed-while-processing-a-compressed-as2-message"></a><span data-ttu-id="ce2cb-103">处理压缩的 AS2 消息时解压缩失败。</span><span class="sxs-lookup"><span data-stu-id="ce2cb-103">Decompression failed while processing a compressed AS2 message.</span></span>
## <a name="details"></a><span data-ttu-id="ce2cb-104">详细信息</span><span class="sxs-lookup"><span data-stu-id="ce2cb-104">Details</span></span>  
  
|                 |                                                                                        |
|-----------------|----------------------------------------------------------------------------------------|
|  <span data-ttu-id="ce2cb-105">产品名称</span><span class="sxs-lookup"><span data-stu-id="ce2cb-105">Product Name</span></span>   |   [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]   |
| <span data-ttu-id="ce2cb-106">产品版本</span><span class="sxs-lookup"><span data-stu-id="ce2cb-106">Product Version</span></span> |               [!INCLUDE[btsEDIVersion](../includes/btsediversion-md.md)]               |
|    <span data-ttu-id="ce2cb-107">事件 ID</span><span class="sxs-lookup"><span data-stu-id="ce2cb-107">Event ID</span></span>     |                                           -                                            |
|  <span data-ttu-id="ce2cb-108">事件源</span><span class="sxs-lookup"><span data-stu-id="ce2cb-108">Event Source</span></span>   | [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] <span data-ttu-id="ce2cb-109">EDI</span><span class="sxs-lookup"><span data-stu-id="ce2cb-109">EDI</span></span> |
|    <span data-ttu-id="ce2cb-110">组件</span><span class="sxs-lookup"><span data-stu-id="ce2cb-110">Component</span></span>    |                                       <span data-ttu-id="ce2cb-111">AS2 引擎</span><span class="sxs-lookup"><span data-stu-id="ce2cb-111">AS2 Engine</span></span>                                       |
|  <span data-ttu-id="ce2cb-112">符号名称</span><span class="sxs-lookup"><span data-stu-id="ce2cb-112">Symbolic Name</span></span>  |                                           -                                            |
|  <span data-ttu-id="ce2cb-113">消息正文</span><span class="sxs-lookup"><span data-stu-id="ce2cb-113">Message Text</span></span>   |       <span data-ttu-id="ce2cb-114">处理压缩的 AS2 消息时解压缩失败。</span><span class="sxs-lookup"><span data-stu-id="ce2cb-114">Decompression failed while processing a compressed AS2 message.</span></span> <span data-ttu-id="ce2cb-115">错误： {0}</span><span class="sxs-lookup"><span data-stu-id="ce2cb-115">Error: {0}</span></span>       |
  
## <a name="explanation"></a><span data-ttu-id="ce2cb-116">解释</span><span class="sxs-lookup"><span data-stu-id="ce2cb-116">Explanation</span></span>  
 <span data-ttu-id="ce2cb-117">此错误/警告/信息事件表明接收管道的 AS2 解码器组件无法解压缩 AS2 消息。</span><span class="sxs-lookup"><span data-stu-id="ce2cb-117">This Error/Warning/Information event indicates that the AS2 Decoder component of the receive pipeline could not decompress the AS2 message.</span></span>  
  
## <a name="user-action"></a><span data-ttu-id="ce2cb-118">用户操作</span><span class="sxs-lookup"><span data-stu-id="ce2cb-118">User Action</span></span>  
 <span data-ttu-id="ce2cb-119">若要解决此错误，请执行以下操作之一：</span><span class="sxs-lookup"><span data-stu-id="ce2cb-119">To resolve this error, do one of the following:</span></span>  
  
-   <span data-ttu-id="ce2cb-120">验证 AS2 消息中的压缩包装有效。</span><span class="sxs-lookup"><span data-stu-id="ce2cb-120">Verify that the compression wrapper in the AS2 message is valid.</span></span>  
  
-   <span data-ttu-id="ce2cb-121">验证解压缩为 BizTalk Server 启用通过验证，"应对消息进行压缩"属性处于选中状态的参与方作为 AS2 消息发送方的 AS2 属性对话框的页 （是否替代入站消息属性属性处于选中状态）.</span><span class="sxs-lookup"><span data-stu-id="ce2cb-121">Verify that decompression is enabled for BizTalk Server by verifying that the "Message should be compressed" property is checked on the Party as AS2 Message Sender page of the AS2 Properties dialog box (if the Override inbound message properties property is checked).</span></span>  
  
-   <span data-ttu-id="ce2cb-122">使用错误消息文本中提供的错误说明来标识特定的问题。</span><span class="sxs-lookup"><span data-stu-id="ce2cb-122">Use the error description provided in the error message text to identify the specific issue.</span></span>